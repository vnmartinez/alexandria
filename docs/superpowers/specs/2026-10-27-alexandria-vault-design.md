# Alexandria — design do vault público de estudos

Data: 2026-10-27
Status: aprovado para implementação

## 1. Objetivo

`alexandria` é um vault Obsidian público, clonável, que organiza trilhas de estudo
autodidata por área de conhecimento. O usuário clona o repositório, abre no Obsidian
(ou lê no GitHub) e navega de um nó central até o curso, os módulos, as leituras e os
exercícios. Também pode abrir o vault no diretório onde roda um agente de código
(Claude Code, Codex, OpenCode, Gemini CLI, Copilot) e usar o agente como tutor.

Primeira entrega: curso completo de **Psicologia** (12 módulos), com catálogo de
livros, exercícios e camada de agentes. A estrutura suporta novas áreas e cursos sem
mudança de arquitetura.

## 2. Não-objetivos

- Não emite certificado nem substitui graduação; todo curso traz aviso explícito.
- Não hospeda PDF ou cópia de obra protegida. Só links para fontes legais.
- Não depende de plugin da comunidade do Obsidian.
- Não implementa aplicativo, site ou backend. É repositório de arquivos Markdown.
- Não inclui diagnóstico, prescrição ou orientação clínica, nem pelo conteúdo nem
  pelos agentes.

## 3. Decisões

| Decisão | Escolha | Motivo |
|---|---|---|
| Profundidade do curso | Trilha completa: hub, módulos, leituras, exercícios | É o caso de uso principal |
| PDFs | Nenhum no repositório; apenas links legais | Repo público: risco de takedown e de conta |
| Anotações do aluno | `pessoal/`, fora do git | `git pull` limpo para leigos |
| Plugins | Markdown puro + plugins nativos; índices escritos à mão | Funciona no Obsidian, no GitHub e em qualquer editor |
| Biblioteca | Catálogo central com uma nota por livro; cursos referenciam por wikilink | Livro usado em dois cursos não duplica |
| Hierarquia | Nó central → 7 áreas → cursos → módulos | Pedido do usuário |
| Áreas | Humanas, Exatas, Natureza, Saúde, Aplicadas, Engenharias, Artes e Letras | Cobre o espectro sem nós demais |
| Posição da Psicologia | `humanas`, com link cruzado em `saude` | Ciência humana com interface de saúde |
| Exercícios | Seção no módulo, gabarito recolhido em `<details>` | Aluno se testa antes de ver a resposta |
| Agentes | `AGENTS.md` canônico + adaptadores curtos + playbooks | Sem duplicação de regra |
| Licença do texto próprio | CC BY-SA 4.0 | Vault aberto, cópia permitida com atribuição |

## 4. Estrutura de pastas

```
alexandria/
├── README.md                      # entrada no GitHub; links relativos
├── INICIO.md                      # nó central do vault
├── AGENTS.md                      # regras canônicas para agentes de IA
├── CLAUDE.md                      # adaptador → AGENTS.md
├── GEMINI.md                      # adaptador → AGENTS.md
├── LICENSE                        # CC BY-SA 4.0 (texto próprio)
├── .gitignore
├── .github/
│   └── copilot-instructions.md    # adaptador → AGENTS.md
├── areas/
│   ├── humanas.md
│   ├── exatas.md
│   ├── natureza.md
│   ├── saude.md
│   ├── aplicadas.md
│   ├── engenharias.md
│   └── artes-e-letras.md
├── cursos/
│   └── humanas/
│       └── psicologia/
│           ├── 00-comece-aqui.md
│           ├── 01-fundamentos-e-historia.md
│           ├── 02-metodo-cientifico-e-neurociencia.md
│           ├── 03-aprendizagem-e-comportamento.md
│           ├── 04-cognicao-memoria-e-inteligencia.md
│           ├── 05-emocoes-e-motivacao.md
│           ├── 06-desenvolvimento-humano.md
│           ├── 07-personalidade-e-diferencas-individuais.md
│           ├── 08-psicologia-social.md
│           ├── 09-psicopatologia.md
│           ├── 10-abordagens-da-psicoterapia.md
│           ├── 11-psicanalise-e-teorias-aprofundadas.md
│           └── 12-psicologia-aplicada-e-integracao.md
├── biblioteca/
│   ├── catalogo.md                # todos os livros, agrupados por área
│   └── humanas/
│       ├── openstax-psychology-2e.md
│       ├── noba-project.md
│       ├── introduction-to-psychology-umn.md
│       ├── research-methods-in-psychology-wsu.md
│       ├── james-principles-of-psychology.md
│       ├── freud-conferencias-introdutorias.md
│       ├── myers-psicologia.md
│       ├── kahneman-rapido-e-devagar.md
│       ├── dsm-5-tr.md
│       └── manual-de-publicacao-apa.md
├── _templates/
│   ├── area.md
│   ├── curso.md
│   ├── modulo.md
│   ├── livro.md
│   └── anotacao.md
├── _meta/
│   ├── COMO-CONTRIBUIR.md
│   ├── CONVENCOES.md
│   ├── FONTES.md
│   ├── agentes/
│   │   ├── tutor.md
│   │   ├── avaliador.md
│   │   └── plano.md
│   └── scripts/
│       └── verificar-links.ps1
├── pessoal/
│   └── README.md                  # único arquivo versionado da pasta
└── docs/
    └── superpowers/
        └── specs/
            └── 2026-10-27-alexandria-vault-design.md
```

## 5. Convenções

- Pastas e arquivos: `kebab-case`, ASCII, minúsculas. Acentos e `ç` ficam no conteúdo,
  nunca no nome do arquivo.
- Nome de arquivo é único no vault inteiro (exigência de `[[wikilink]]`).
- Módulos ordenados por prefixo numérico de dois dígitos.
- H1 em português, com o nome legível (`# Mês 1 — Fundamentos e História`).
- Um assunto por nota; nota acima de ~150 linhas deve ser dividida.
- Idioma do conteúdo: português. Títulos de obras estrangeiras mantêm o original.
- Pasta é a fonte de verdade da hierarquia. Tags existem só como apoio:
  `#tipo/livro`, `#tipo/exercicio`, `#area/humanas`, `#curso/psicologia`.

## 6. Frontmatter

Mínimo e estável, para não quebrar quando o vault ganhar automação.

**Área**
```yaml
---
area: humanas
---
```

**Curso**
```yaml
---
area: humanas
curso: psicologia
nivel: introdutorio
carga-semanal: 5-7h
duracao: 12 meses
atualizado: 2026-10-27
---
```

**Módulo**
```yaml
---
curso: psicologia
area: humanas
ordem: 1
duracao: 4 semanas
atualizado: 2026-10-27
---
```

**Livro**
```yaml
---
titulo: Psychology 2e
autor: OpenStax
ano: 2020
idioma: en
nivel: introdutorio
licenca: CC BY 4.0
obtencao: gratuito
acesso: https://openstax.org/details/books/psychology-2e
verificado: 2026-10
---
```

`obtencao` aceita `gratuito`, `compra` ou `biblioteca`. Quando não for `gratuito`, a
nota explica onde comprar ou pegar emprestado, sem link para cópia irregular.

## 7. Anatomia das notas

### 7.1 `INICIO.md` — nó central

Título, uma frase sobre o projeto, tabela das 7 áreas com link e contagem de cursos,
seção "Como estudar" (clonar → abrir no Obsidian → escolher área → curso → módulo),
seção "Como estudar com um agente de IA" (abrir o vault no agente; o agente lê
`AGENTS.md`), aviso legal e link para `README.md`, `_meta/COMO-CONTRIBUIR.md`,
`_meta/FONTES.md`.

### 7.2 `areas/<area>.md` — hub de área

O que a área cobre, tabela de cursos (nome, nível, duração, link), seção "Cursos
cruzados" quando houver (ex.: `saude` aponta para psicologia), e "Nenhum curso ainda"
seguido de instrução curta de como adicionar um.

### 7.3 `cursos/<area>/<curso>/00-comece-aqui.md` — hub do curso

Frontmatter de curso; o que é o curso e para quem; aviso de que não equivale a
graduação nem habilita ao exercício profissional; carga semanal; tabela dos módulos
(mês, tema, link); leituras obrigatórias e opcionais (wikilink para `biblioteca/`);
rotina semanal sugerida; critério de conclusão ("explicar, comparar teorias,
identificar evidências contrárias, aplicar sem extrapolar"); link para
`pessoal/<area>/<curso>/progresso.md`.

### 7.4 Módulo

Ordem fixa:

1. `## Objetivo` — uma a três frases.
2. `## Tópicos` — lista numerada com checkbox (`- [ ]`), 8–14 itens.
3. `## Leituras` — wikilink para cada livro com capítulos ou seções específicas.
4. `## Conceitos-chave` — 5–10 termos com definição de uma linha.
5. `## Exercícios` — ver seção 8.
6. `## Resultado esperado` — o que o aluno deve conseguir fazer.
7. `## Anotações` — instrução curta: anotar em `pessoal/<area>/<curso>/<slug>.md`.
8. `## Próximo` — link para o módulo seguinte (ou "fim do curso" no 12).

### 7.5 `biblioteca/<area>/<livro>.md` — livro

Tabela de metadados espelhando o frontmatter, "Por que ler" (2–4 linhas), "Como
acessar" (link direto, ou instrução de compra/empréstimo), "Capítulos por módulo"
(tabela módulo → capítulo), "Limitações ou vieses" quando relevante, e `## Relacionado`
com cursos que usam o livro.

### 7.6 `biblioteca/catalogo.md`

Tabela única, agrupada por área, com colunas: título, autor, nível, licença, acesso,
cursos. É o índice que o aluno folheia quando não sabe o que ler.

### 7.7 `pessoal/` — área do aluno

`pessoal/README.md` (versionado) explica: a pasta é local, não vai para o git; crie
`pessoal/<area>/<curso>/`; use `_templates/anotacao.md`; o progresso fica em
`progresso.md` com checkboxes espelhando os tópicos do módulo. O restante de
`pessoal/` é ignorado pelo git.

## 8. Exercícios

Cada módulo traz `## Exercícios` com 8–10 itens:

- 3 de múltipla escolha (4 alternativas, uma correta);
- 3 discursivas curtas (resposta de 3 a 6 linhas);
- 2 de aplicação a um caso concreto descrito no enunciado.

Formato: enunciado numerado; alternativas em lista `a)`–`d)`; gabarito em bloco
`<details><summary>Gabarito</summary>` com resposta, explicação de 2–4 linhas e o
tópico ou leitura de referência. `<details>` fica recolhido no Obsidian e no GitHub,
então o aluno se testa antes de ler a resposta.

Exercícios não copiam questão de livro protegido: são autorais, sobre conceitos do
módulo.

## 9. Camada de agentes de IA

### 9.1 `AGENTS.md` (canônico)

Seções: papel de tutor; como navegar (ler `INICIO.md` → hub de área → hub do curso →
módulo atual, nunca varrer o vault inteiro); limites (não diagnosticar, não prescrever,
não simular sessão clínica, não afirmar competência profissional); fontes (usar o
catálogo, citar livro e capítulo, nunca inventar referência, respeitar licença, não
sugerir pirataria); exercícios (corrigir por rubrica, apontar lacuna, indicar revisão);
anotações (escrever só em `pessoal/`; nunca alterar conteúdo versionado sem pedido
explícito); idioma (pt-BR, termos técnicos no original quando necessário); formato de
resposta (curto, direto, com links do vault).

### 9.2 Adaptadores

`CLAUDE.md`, `GEMINI.md` e `.github/copilot-instructions.md` têm 5–10 linhas: apontam
para `AGENTS.md`, registram que ele é a fonte única e não repetem regra.

### 9.3 `_meta/agentes/`

- `tutor.md` — explicar em camadas (intuição → definição → exemplo → exceção),
  checar entendimento com uma pergunta antes de avançar, usar analogia só quando
  levar de volta ao conceito.
- `avaliador.md` — rubrica de correção, o que conta como lacuna, como registrar
  resultado em `pessoal/`, quando mandar revisar o módulo.
- `plano.md` — montar plano de N semanas a partir de um curso do vault, redistribuindo
  módulos e leituras sem alterar o conteúdo original.

## 10. Navegação e compatibilidade

- No Obsidian: tudo por `[[wikilink]]`.
- No GitHub: `README.md` repete o caminho com links relativos (`cursos/humanas/...`),
  porque wikilink não renderiza.
- Nenhum recurso depende de plugin da comunidade. `_templates/` é lido pelo plugin
  nativo Templates; quem não o usa copia o arquivo à mão.
- `<details>` é HTML aceito nos dois ambientes.

## 11. Conteúdo da v1

- 12 módulos de Psicologia derivados de `plano_estudos_psicologia_12_meses.md`,
  preservando tópicos, objetivos, resultados esperados, rotina de 6 h/semana e o
  princípio orientador (método científico antes de Freud e psicopatologia).
- Catálogo com 10 livros: prioridade para acesso aberto e legal (OpenStax, Noba,
  Open Textbook Library, Project Gutenberg) e marcação explícita de obra paga
  (Myers, Kahneman, DSM-5-TR, manual APA). Todo link é verificado na implementação e
  recebe `verificado:` com o mês.
- 6 áreas começam vazias, com hub e instrução; apenas `humanas` tem curso.

## 12. Licença e uso de terceiros

Texto próprio do vault: CC BY-SA 4.0. Obras citadas mantêm seus direitos; o vault
publica metadados e links, nunca o conteúdo protegido. `_meta/FONTES.md` registra a
política e o contato para remoção caso algum link seja contestado.

## 13. Verificação

`_meta/scripts/verificar-links.ps1` (PowerShell, sem dependência):

1. Varre todos os `.md` versionados.
2. Extrai `[[alvo]]` e `[[alvo|alias]]`, compara com nomes de arquivo sem extensão
   (case-insensitive) e lista alvos inexistentes.
3. Verifica links markdown relativos (`](caminho.md)`) e lista arquivos ausentes.
4. Falha com código de saída 1 quando houver quebra.

Checklist manual antes de cada entrega: abrir `INICIO.md` no Obsidian e chegar até
um livro em 3 cliques; rodar o script sem erro; conferir que `pessoal/` não aparece
no `git status`; conferir que nenhum arquivo de PDF foi adicionado.

## 14. Critérios de aceitação

- `git clone` + abrir no Obsidian mostra `INICIO.md` e a navegação completa até os 12
  módulos e os 10 livros, sem plugin instalado.
- Cada módulo tem as 8 seções e 8–10 exercícios com gabarito recolhido.
- Nenhum PDF ou cópia de obra protegida no repositório.
- `AGENTS.md` + adaptadores presentes; um agente aberto no vault encontra as regras
  sem instrução extra do usuário.
- `verificar-links.ps1` termina com código 0.
- `pessoal/` ignorado, exceto `pessoal/README.md`.
- Conteúdo em português, nomes de arquivo em ASCII.

## 15. Riscos e mitigação

| Risco | Mitigação |
|---|---|
| Link externo morre | Campo `verificado:` por livro + script só cobre links internos; revisão periódica documentada em `FONTES.md` |
| Nome de arquivo repetido quebra wikilink | Convenção de unicidade + script aponta ambiguidade |
| Aluno edita conteúdo versionado e cria conflito | Progresso e anotações em `pessoal/`; aviso no `pessoal/README.md` |
| Agente inventa referência | `AGENTS.md` exige citar só o catálogo; `avaliador.md` e `tutor.md` repetem a regra |
| Vault vira depósito de link pirata | `FONTES.md` define critério e `COMO-CONTRIBUIR.md` exige licença no frontmatter |
| Escopo cresce para 7 áreas completas | Só `humanas/psicologia` na v1; demais áreas são hubs |
```
