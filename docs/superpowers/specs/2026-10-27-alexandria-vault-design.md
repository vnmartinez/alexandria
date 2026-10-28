# Alexandria — desenho do vault (revisão 2)

Data: 2026-10-27 · Status: aprovado pelo usuário (decisões 1–14 do handoff)
Substitui a revisão 1 (curso multiarquivo, notas de livro, verificação por script).

## Objetivo

Vault Obsidian público e clonável com trilhas de estudo autodidata por área de
conhecimento. O aluno clona, abre no Obsidian e navega: nó central → área → curso.
O mesmo repositório serve de contexto para agentes de IA (Claude Code, Codex,
OpenCode, Gemini CLI, Copilot), que atuam como tutores seguindo `AGENTS.md`.

V1: curso completo de Psicologia em 12 meses, derivado do plano de estudos do
usuário, com a regra de estudar método científico antes de Freud e psicopatologia.

## Restrições

- Só Markdown. Nenhum script, binário, `.ps1`, caminho absoluto de máquina nem
  comando específico de sistema operacional. Abre igual em Windows, macOS e Linux.
- Zero plugin da comunidade. `<details>` é permitido para recolher gabarito.
- Nenhum PDF, EPUB, MOBI ou DJVU. O catálogo guarda metadados, licença e link legal;
  obra paga é `compra` ou `biblioteca`, nunca link de cópia.
- Nomes de pasta e arquivo em `kebab-case` ASCII minúsculo, únicos no vault.
- Português do Brasil; H1 legível.
- Texto próprio sob CC BY-SA 4.0.
- `pessoal/` é do aluno e fica fora do git (só `pessoal/README.md` é versionado).

## Estrutura

```
alexandria/
├── README.md                 entrada no GitHub (links por URL, sem aresta no grafo)
├── INICIO.md                 nó central
├── AGENTS.md                 regras canônicas dos agentes
├── CLAUDE.md, GEMINI.md, .github/copilot-instructions.md   adaptadores
├── LICENSE, .gitignore
├── areas/<area>.md           7 hubs
├── cursos/humanas/psicologia.md   curso em nota única
├── biblioteca/catalogo.md    catálogo em nota única
├── _templates/               area.md, curso.md, anotacao.md
├── _meta/                    COMO-CONTRIBUIR, CONVENCOES, FONTES, VERIFICACAO, agentes/
├── pessoal/README.md
└── docs/superpowers/         spec, plano, handoff
```

As 7 áreas: `humanas`, `exatas`, `natureza`, `saude`, `aplicadas`, `engenharias`,
`artes-e-letras`. Psicologia fica em `humanas`.

## Grafo e regras de link

O grafo do Obsidian tem de ser uma árvore esparsa, sem ciclos nem emaranhado.

| De | Para | Tipo |
|---|---|---|
| `INICIO.md` | 7 `areas/*` e `biblioteca/catalogo` | filhos |
| `areas/<area>.md` | `INICIO` (pai) e cursos da área (filhos) | hub |
| `cursos/<area>/<curso>.md` | área (pai); âncoras internas `[[#Mês N — …]]` | hub + seções |
| `biblioteca/catalogo.md` | `INICIO` (pai); só links externos de acesso | folha |

Proibido: link lateral entre áreas, curso cruzado, link de livro para curso, link de
curso para o catálogo (o curso cita livros em texto e indica o catálogo em código),
wikilink em `_templates/`, `_meta/`, `AGENTS.md`, adaptadores e `README.md`. Esses
arquivos citam caminhos entre crases e ficam órfãos no grafo; com o filtro "Órfãos"
desligado, o grafo mostra só a árvore: 1 central, 7 áreas, 1 curso, 1 catálogo.

O `README.md` usa URLs absolutas do GitHub (`https://github.com/vnmartinez/alexandria/blob/main/...`)
para navegar no site sem criar arestas no grafo.

## Contrato do curso (nota única)

1. Frontmatter: `area`, `curso`, `nivel`, `carga-semanal`, `duracao`, `atualizado`.
2. Link para a área (pai), H1, para quem é, aviso de que não equivale a graduação nem
   habilita ao exercício profissional.
3. Carga e ritmo, rotina semanal, índice dos 12 meses por âncora.
4. Bibliografia: obrigatórias e opcionais com capítulos por mês, em texto.
5. Para cada mês, `## Mês N — Tema` com, nesta ordem: `### Objetivo`,
   `### Tópicos` (checkboxes `- [ ] N.`, ao menos 10), `### Leituras`,
   `### Conceitos-chave`, `### Exercícios` (8–10: 3 múltipla escolha, 3 discursivas,
   2–4 de aplicação; gabarito único por mês em `<details><summary>Gabarito</summary>`),
   `### Resultado esperado`, `### Anotações` (aponta `pessoal/<area>/<curso>/`),
   e a linha de navegação para o mês seguinte por âncora.
6. `## Conclusão`: critério de conclusão do curso.

## Contrato do catálogo (nota única)

Uma seção `## <Área>` por área com obras e uma seção `### <Título>` por obra, com
lista de campos: autor, ano, idioma, nível, licença, obtenção
(`gratuito|compra|biblioteca`), acesso (URL verificada ou instrução de compra),
verificado (`AAAA-MM`) e "Por que ler" em 1–3 linhas. Nunca inventar URL: link que
não abre é trocado por outra obra aberta.

## Camada de agentes

- `AGENTS.md`: fonte única. Papel de tutor, mapa do vault, regras de navegação,
  limites (não diagnosticar, não prescrever, não substituir atendimento, citar só o
  catálogo ou fonte verificável, não inventar referência, não sugerir pirataria),
  escrita apenas em `pessoal/`, como verificar.
- `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md`: apontam para
  `AGENTS.md` sem repetir regras.
- `_meta/agentes/tutor.md`, `avaliador.md`, `plano.md`: playbooks por tarefa.

## Verificação

Checklist manual em `_meta/VERIFICACAO.md`, executável por pessoa ou agente, sem
script. Cobre links internos, links do README, contrato do curso, contrato do
catálogo, áreas, higiene do repositório e conferência de leitura no Obsidian.

## Fora do escopo da v1

Cursos das outras 6 áreas; tradução; site estático; plugins; arquivos de
configuração do Obsidian versionados.
