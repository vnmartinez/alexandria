# Alexandria — Plano de Implementação do Vault

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Construir o vault Obsidian público `alexandria` com nó central, 7 áreas, curso completo de Psicologia (12 módulos com exercícios), catálogo de 10 livros legais e camada de agentes tutores.

**Architecture:** Repositório de arquivos Markdown puros, sem plugin e sem código. A hierarquia é materializada em pastas (`areas/` → `cursos/<area>/<curso>/` → módulos; `biblioteca/<area>/<livro>.md`) e a navegação em `[[wikilink]]`, com `README.md` espelhando o caminho por links relativos para o GitHub. A verificação é uma checklist em Markdown (`_meta/VERIFICACAO.md`), que uma pessoa ou um agente executa com as ferramentas que já tem.

**Tech Stack:** Markdown, Obsidian (plugins nativos apenas), Git. Nenhum script, binário ou dependência de sistema operacional — o vault abre igual no Windows, no macOS e no Linux.

**Spec:** `docs/superpowers/specs/2026-10-27-alexandria-vault-design.md`

## Global Constraints

- Nomes de pasta e arquivo em `kebab-case` ASCII, minúsculos, únicos no vault.
- Conteúdo em português do Brasil; H1 legível (`# Mês 1 — Fundamentos e História`).
- Nenhum PDF, EPUB ou cópia de trecho protegido no repositório: só metadados e links.
- Nenhuma dependência de plugin da comunidade do Obsidian; `<details>` é HTML permitido.
- Nenhum script, binário, caminho absoluto de máquina ou comando específico de sistema operacional no repositório.
- Frontmatter exatamente com as chaves da spec §6; sem chave inventada.
- Todo link externo só entra depois de aberto e conferido; o campo `verificado:` recebe `AAAA-MM` da conferência.
- `pessoal/` é ignorado pelo git, exceto `pessoal/README.md`.
- Commits em português, um por tarefa.
- Conteúdo de Psicologia deriva de `C:\Users\Vinicius\Downloads\plano_estudos_psicologia_12_meses.md`; não inventar tópico que não esteja lá nem em fonte citada.
- A verificação de cada tarefa é a checklist de `_meta/VERIFICACAO.md`; "verde" significa zero pendência nos itens indicados.

## Mapa de arquivos

| Arquivo | Responsabilidade |
|---|---|
| `.gitignore` | Ignorar `pessoal/` e lixo do Obsidian |
| `LICENSE` | CC BY-SA 4.0 do texto próprio |
| `_meta/VERIFICACAO.md` | Checklist única de conformidade (links, contrato das notas, higiene) |
| `README.md` | Entrada no GitHub, com links relativos |
| `INICIO.md` | Nó central do vault |
| `areas/<7 áreas>.md` | Hub de área: lista cursos e cursos cruzados |
| `cursos/humanas/psicologia/00-comece-aqui.md` | Hub do curso: aviso legal, carga, tabela dos 12 meses, leituras |
| `cursos/humanas/psicologia/01-…12-….md` | Módulo: 8 seções + 8–10 exercícios |
| `biblioteca/catalogo.md` | Catálogo único por área |
| `biblioteca/humanas/<livro>.md` | Nota de livro: metadados, licença, acesso, capítulos por módulo |
| `_templates/*.md` | Modelos de área, curso, módulo, livro, anotação |
| `AGENTS.md` | Regras canônicas dos agentes |
| `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md` | Adaptadores que apontam para `AGENTS.md` |
| `_meta/agentes/*.md` | Playbooks: tutor, avaliador, plano |
| `_meta/COMO-CONTRIBUIR.md`, `CONVENCOES.md`, `FONTES.md` | Regras de contribuição, convenções e política de fontes |
| `pessoal/README.md` | Explica a área local do aluno |

---

### Task 1: Fundação — gitignore, licença, área pessoal e checklist

**Files:**
- Create: `.gitignore`, `LICENSE`, `pessoal/README.md`
- Create: `_meta/VERIFICACAO.md`

**Interfaces:**
- Produces: a checklist que todas as tarefas seguintes executam, com os itens numerados 1 a 7. `pessoal/README.md` é o único arquivo versionado da pasta pessoal.

- [ ] **Step 1: Criar `.gitignore`**

```gitignore
# Área pessoal do aluno: só o README é versionado
pessoal/*
!pessoal/README.md

# Estado local do Obsidian
.obsidian/workspace*.json
.obsidian/workspace-mobile*.json
.obsidian/cache
.obsidian/plugins/
.obsidian/themes/

# Sistema e editor
.DS_Store
Thumbs.db
desktop.ini
*.tmp
```

- [ ] **Step 2: Criar `LICENSE`**

```text
Alexandria — vault público de trilhas de estudo
Copyright (C) 2026 Vinicius Martinez

O texto original deste repositório (notas, trilhas, exercícios, playbooks de
agentes) está licenciado sob Creative Commons Atribuição-CompartilhaIgual 4.0
Internacional (CC BY-SA 4.0).

Resumo da licença: https://creativecommons.org/licenses/by-sa/4.0/deed.pt-br
Texto legal completo: https://creativecommons.org/licenses/by-sa/4.0/legalcode.pt

Obras de terceiros citadas ou linkadas (livros, capítulos, manuais) NÃO são
licenciadas por este arquivo e permanecem com seus titulares. Este repositório
publica apenas metadados e links; nenhum conteúdo protegido é hospedado aqui.
```

- [ ] **Step 3: Criar `pessoal/README.md`**

```markdown
# Sua área pessoal

Esta pasta é sua e **não vai para o git**. Tudo aqui fica só no seu computador,
então você pode anotar, marcar progresso e errar à vontade sem criar conflito
quando rodar `git pull`.

## Como organizar

Espelhe a estrutura dos cursos:

```
pessoal/
└── humanas/
    └── psicologia/
        ├── progresso.md
        ├── 01-fundamentos-e-historia.md
        └── 02-metodo-cientifico-e-neurociencia.md
```

- `progresso.md`: copie o modelo de `_templates/anotacao.md`, com os checkboxes
  dos tópicos do módulo. Marque conforme avança.
- Uma nota por módulo, com resumo próprio, dúvidas e links para o que consultou.

## Regras

- Não edite os arquivos de `cursos/`, `areas/` ou `biblioteca/`: eles são
  atualizados pelo autor e suas mudanças podem se perder no `git pull`.
- Quer sugerir correção ou novo curso? Veja `_meta/COMO-CONTRIBUIR.md`.
- Se você usa um agente de IA, ele escreve apenas aqui (regra em `AGENTS.md`).
```

- [ ] **Step 4: Criar `_meta/VERIFICACAO.md`**

```markdown
# Checklist de verificação

Percorra esta lista antes de cada commit. Não há script: qualquer pessoa ou agente
consegue executar as conferências no Obsidian, no GitHub ou num editor de texto, em
Windows, macOS ou Linux. "Verde" significa zero pendência.

## 1. Links internos

- [ ] Liste os arquivos `.md` do vault e guarde os nomes, sem extensão e sem pasta.
- [ ] Procure todas as ocorrências de `[[` e confira se cada alvo existe.
      Em `[[caminho/arquivo|texto]]`, o alvo é o caminho, não o texto.
- [ ] Confirme que nenhum nome de arquivo aparece duas vezes no vault: wikilink
      resolve por nome, e duplicata torna o destino imprevisível.

## 2. Links relativos do README

- [ ] Todo `](...)` sem `http` aponta para um arquivo que existe no repositório.

## 3. Contrato de módulo

Vale para cada arquivo em `cursos/<area>/<curso>/` que não seja `00-comece-aqui.md`.

- [ ] Frontmatter com `curso`, `area`, `ordem`, `duracao`, `atualizado`.
- [ ] As 8 seções, nesta ordem: Objetivo, Tópicos, Leituras, Conceitos-chave,
      Exercícios, Resultado esperado, Anotações, Próximo.
- [ ] Pelo menos 8 tópicos no formato `- [ ] N. …`.
- [ ] Entre 8 e 10 exercícios numerados, com `N. ` no início da linha.
- [ ] Gabarito em `<details>` com `<summary>Gabarito</summary>`.
- [ ] Instrução de anotações apontando para `pessoal/`.

## 4. Contrato de livro

Vale para cada arquivo em `biblioteca/<area>/`, exceto `catalogo.md`.

- [ ] Frontmatter com `titulo`, `autor`, `ano`, `idioma`, `nivel`, `licenca`,
      `obtencao`, `acesso`, `verificado`.
- [ ] Seções "Por que ler", "Como acessar" e "Capítulos por módulo".
- [ ] O link de `acesso` termina em página oficial do titular, repositório
      institucional ou loja; nenhuma cópia irregular.

## 5. Curso e área

- [ ] Hub do curso: frontmatter com `area`, `curso`, `nivel`, `carga-semanal`,
      `duracao`, `atualizado`.
- [ ] Hub do curso: 12 links de módulo e aviso de que o percurso não equivale a
      graduação nem habilita ao exercício profissional.
- [ ] Cada arquivo em `areas/` tem `area:` no frontmatter e lista os cursos da área.

## 6. Higiene do repositório

- [ ] Nenhum `.pdf`, `.epub`, `.mobi` ou `.djvu` versionado.
- [ ] `pessoal/` fora do git, exceto `pessoal/README.md`.
- [ ] Arquivos obrigatórios presentes: `README.md`, `INICIO.md`, `AGENTS.md`,
      `LICENSE`, `_meta/COMO-CONTRIBUIR.md`, `_meta/CONVENCOES.md`,
      `_meta/FONTES.md`.
- [ ] Nenhum script, binário ou caminho absoluto de máquina no repositório.

## 7. Conferência de leitura

- [ ] Abrir `INICIO.md` no Obsidian e chegar a um livro em três cliques, sem link
      em vermelho.
```

- [ ] **Step 5: Conferir o estado do repositório**

Run: `git status --short`
Expected: `?? .gitignore`, `?? LICENSE`, `?? _meta/`, `?? pessoal/`.

Run: `git add -A` seguido de `git status --short`
Expected: `pessoal/README.md` presente; nenhum outro arquivo dentro de `pessoal/`.

- [ ] **Step 6: Commit**

```bash
git add .gitignore LICENSE pessoal/README.md _meta/VERIFICACAO.md
git commit -m "chore: fundacao do vault, licenca e checklist de verificacao"
```

---

### Task 2: Nó central e hubs das 7 áreas

**Files:**
- Create: `INICIO.md`, `README.md`
- Create: `areas/humanas.md`, `areas/exatas.md`, `areas/natureza.md`, `areas/saude.md`, `areas/aplicadas.md`, `areas/engenharias.md`, `areas/artes-e-letras.md`

**Interfaces:**
- Consumes: a checklist da Task 1.
- Produces: os alvos `[[cursos/humanas/psicologia/00-comece-aqui]]` e `[[biblioteca/catalogo]]`, usados pelo hub de `humanas`, por `saude` e pelo `INICIO.md`. Esses links ficam sem destino até as Tasks 4 e 5 — é esperado e a checklist acusa.

- [ ] **Step 1: Criar `areas/humanas.md`**

```markdown
---
area: humanas
---

# Ciências Humanas

Estudo do comportamento, da cultura, das instituições e das formas de produzir
sentido: como pessoas e sociedades pensam, organizam-se e mudam.

## Cursos

| Curso | Nível | Duração | Carga semanal |
|---|---|---|---|
| [[cursos/humanas/psicologia/00-comece-aqui\|Psicologia]] | Introdutório | 12 meses | 5–7 h |

## Como adicionar um curso

1. Copie `_templates/curso.md` para `cursos/humanas/<curso>/00-comece-aqui.md`.
2. Copie `_templates/modulo.md` para cada módulo, com prefixo numérico.
3. Inclua o curso na tabela acima e as leituras no catálogo.
4. Percorra `_meta/VERIFICACAO.md` antes do commit.

Detalhes em `_meta/COMO-CONTRIBUIR.md`.
```

- [ ] **Step 2: Criar os hubs das outras 6 áreas**

Cada um repete a estrutura de `humanas.md` trocando frontmatter, título, parágrafo de abertura e a tabela de cursos por:

```markdown
Nenhum curso publicado ainda.
```

Textos de abertura a usar, um por arquivo:

| Arquivo | `area:` | Título | Abertura |
|---|---|---|---|
| `areas/exatas.md` | `exatas` | Ciências Exatas | Matemática, lógica, computação e os fundamentos formais que sustentam a modelagem do mundo. |
| `areas/natureza.md` | `natureza` | Ciências da Natureza | Física, química, biologia e ciências da Terra: como o mundo material funciona e como o testamos. |
| `areas/saude.md` | `saude` | Ciências da Saúde | Anatomia, fisiologia, clínica e cuidado: formação para compreender saúde, doença e intervenção. |
| `areas/aplicadas.md` | `aplicadas` | Ciências Sociais Aplicadas | Direito, economia, administração e políticas públicas: como sociedades organizam recursos e normas. |
| `areas/engenharias.md` | `engenharias` | Engenharias e Tecnologia | Projeto, construção e operação de sistemas físicos e digitais, com métodos de engenharia. |
| `areas/artes-e-letras.md` | `artes-e-letras` | Artes e Letras | Literatura, línguas, artes visuais, música e história da cultura: formas de expressão e interpretação. |

Em `areas/saude.md`, a tabela de cursos fica assim (curso cruzado, não hospedado na área):

```markdown
## Cursos cruzados

| Curso | Área de origem | Por que aparece aqui |
|---|---|---|
| [[cursos/humanas/psicologia/00-comece-aqui\|Psicologia]] | [[areas/humanas\|Humanas]] | Base para saúde mental, psicopatologia e relação com pacientes |
```

- [ ] **Step 3: Criar `INICIO.md`**

```markdown
# Alexandria

Vault público de trilhas de estudo por área de conhecimento. Escolha uma área,
entre em um curso e siga os módulos na ordem. Tudo aqui é gratuito para ler,
clonar e compartilhar; os livros permanecem com seus autores e editoras.

## Áreas

| Área | O que cobre |
|---|---|
| [[areas/humanas\|Ciências Humanas]] | Comportamento, cultura, instituições e sentido — **1 curso** |
| [[areas/exatas\|Ciências Exatas]] | Matemática, lógica, computação |
| [[areas/natureza\|Ciências da Natureza]] | Física, química, biologia, Terra |
| [[areas/saude\|Ciências da Saúde]] | Corpo, clínica e cuidado |
| [[areas/aplicadas\|Sociais Aplicadas]] | Direito, economia, gestão, políticas |
| [[areas/engenharias\|Engenharias e Tecnologia]] | Projeto e operação de sistemas |
| [[areas/artes-e-letras\|Artes e Letras]] | Línguas, literatura, artes, música |

## Como estudar

1. Clone o repositório e abra a pasta como vault no Obsidian (sem plugin nenhum,
   em Windows, macOS ou Linux).
2. Copie `_templates/anotacao.md` para `pessoal/<area>/<curso>/` e registre ali o
   seu progresso — essa pasta não vai para o git e não gera conflito no `git pull`.
3. Siga os módulos na ordem, marcando os tópicos conforme lê.
4. Faça os exercícios de cada módulo antes de abrir o gabarito.
5. Ao fim do módulo, confira o "Resultado esperado": se não conseguir explicar,
   refaça as leituras indicadas.

## Como estudar com um agente de IA

Abra esta pasta no Claude Code, Codex, OpenCode, Gemini CLI ou Copilot. O agente lê
`AGENTS.md` sozinho e assume o papel de tutor: explica, pergunta, corrige exercício
e monta plano de estudo. Nenhum segredo nem configuração extra é necessária.

- Playbooks: `_meta/agentes/tutor.md`, `_meta/agentes/avaliador.md`, `_meta/agentes/plano.md`
- Regras que o agente segue: `AGENTS.md`

## Catálogo de livros

[[biblioteca/catalogo|Catálogo completo]] — metadados, licença e link de acesso de
cada obra, com a indicação do que é gratuito e do que é comprado ou emprestado.

## Aviso

Este vault é material de estudo autodidata. Não é graduação, não inclui prática
supervisionada e não habilita ao exercício profissional de nenhuma área. Nenhum
conteúdo aqui serve para diagnóstico ou tratamento.

Política de links e licenças: `_meta/FONTES.md`. Nenhum arquivo de livro é
hospedado neste repositório.

## Contribuir

Leia `_meta/COMO-CONTRIBUIR.md` e as convenções em `_meta/CONVENCOES.md`.
```

- [ ] **Step 4: Criar `README.md`**

```markdown
# Alexandria

Vault público de trilhas de estudo por área de conhecimento. Clone, abra no Obsidian
e estude — sem plugin, sem conta, sem custo.

## Comece por aqui

- [Nó central do vault](INICIO.md)
- [Ciências Humanas](areas/humanas.md) → [Psicologia](cursos/humanas/psicologia/00-comece-aqui.md)
- [Catálogo de livros](biblioteca/catalogo.md)

## Áreas

| Área | Cursos |
|---|---|
| [Ciências Humanas](areas/humanas.md) | Psicologia (12 meses) |
| [Ciências Exatas](areas/exatas.md) | — |
| [Ciências da Natureza](areas/natureza.md) | — |
| [Ciências da Saúde](areas/saude.md) | — (curso cruzado: Psicologia) |
| [Sociais Aplicadas](areas/aplicadas.md) | — |
| [Engenharias e Tecnologia](areas/engenharias.md) | — |
| [Artes e Letras](areas/artes-e-letras.md) | — |

## Como usar

```bash
git clone https://github.com/vnmartinez/alexandria.git
```

Abra a pasta no [Obsidian](https://obsidian.md) como vault. Suas anotações vão em
`pessoal/`, que fica fora do controle de versão.

Funciona igual no Windows, no macOS e no Linux: o repositório é só Markdown, sem
script nem plugin.

Também funciona como contexto para agentes de IA: abra a pasta no Claude Code,
Codex, OpenCode, Gemini CLI ou Copilot e o agente segue [AGENTS.md](AGENTS.md).

## O que tem dentro

- Trilhas completas: objetivos, tópicos, leituras, exercícios com gabarito.
- Catálogo de livros com licença e link legal de acesso (nada de PDF pirata).
- Playbooks de estudo para agentes: tutor, avaliador e montagem de plano.
- Checklist de verificação em `_meta/VERIFICACAO.md`, para quem quiser contribuir.

## Aviso

Material de estudo autodidata. Não substitui graduação, não inclui prática
supervisionada e não habilita ao exercício profissional.

## Licença

Texto original sob [CC BY-SA 4.0](LICENSE). Obras citadas permanecem com seus
titulares.
```

- [ ] **Step 5: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` itens 1, 2, 5 e 6.
Expected: item 2 verde (links do README resolvem); item 5 verde nas áreas e no hub do curso inexistente (nada a conferir ainda); itens 1 e 6 acusam exatamente três pendências conhecidas — `[[biblioteca/catalogo]]`, `[[cursos/humanas/psicologia/00-comece-aqui]]` e os arquivos obrigatórios das tarefas seguintes. Nenhuma outra quebra.

- [ ] **Step 6: Commit**

```bash
git add INICIO.md README.md areas
git commit -m "feat: no central e hubs das 7 areas"
```

---

### Task 3: Templates

**Files:**
- Create: `_templates/area.md`, `_templates/curso.md`, `_templates/modulo.md`, `_templates/livro.md`, `_templates/anotacao.md`

**Interfaces:**
- Consumes: as convenções de frontmatter e a ordem de seções definidas na checklist (itens 3 e 4).
- Produces: modelos que as Tasks 4–7 copiam; `_templates/anotacao.md` é citado em `pessoal/README.md` e em `INICIO.md`.

- [ ] **Step 1: Criar `_templates/area.md`**

```markdown
---
area: <slug-da-area>
---

# <Nome da área>

<Uma ou duas frases: o que a área cobre e para quem estuda.>

## Cursos

| Curso | Nível | Duração | Carga semanal |
|---|---|---|---|
| [[cursos/<area>/<curso>/00-comece-aqui\|<Curso>]] | <nível> | <duração> | <carga> |

## Como adicionar um curso

1. Copie `_templates/curso.md` para `cursos/<area>/<curso>/00-comece-aqui.md`.
2. Copie `_templates/modulo.md` para cada módulo, com prefixo numérico.
3. Inclua o curso na tabela acima e as leituras no catálogo.
4. Percorra `_meta/VERIFICACAO.md` antes do commit.
```

- [ ] **Step 2: Criar `_templates/curso.md`**

```markdown
---
area: <area>
curso: <curso>
nivel: <introdutorio|intermediario|avancado>
carga-semanal: <ex.: 5-7h>
duracao: <ex.: 12 meses>
atualizado: <AAAA-MM-DD>
---

# <Curso>

<O que é o curso e para quem.>

> Este percurso não equivale a uma graduação, não inclui prática supervisionada e
> não habilita ao exercício profissional.

## Carga e ritmo

<Carga semanal, número de módulos e tempo sugerido por módulo.>

## Módulos

| Mês | Tema |
|---|---|
| 1 | [[cursos/<area>/<curso>/01-<slug>\|Mês 1 — <Tema>]] |

## Leituras

**Obrigatórias**

- [[biblioteca/<area>/<livro>\|<Título>]] — <capítulos ou seções>

**Opcionais**

- [[biblioteca/<area>/<livro>\|<Título>]]

## Rotina semanal sugerida

| Atividade | Horas/semana |
|---|---:|
| Leitura | <n> |
| Exercícios | <n> |

## Conclusão

Você conclui o curso quando consegue explicar os conceitos, comparar teorias
concorrentes, identificar evidências favoráveis e contrárias e aplicar os conceitos
a exemplos sem extrapolar os dados.

Progresso e anotações: `pessoal/<area>/<curso>/progresso.md`.
```

- [ ] **Step 3: Criar `_templates/modulo.md`**

```markdown
---
curso: <curso>
area: <area>
ordem: <n>
duracao: <ex.: 4 semanas>
atualizado: <AAAA-MM-DD>
---

# Mês <n> — <Tema>

## Objetivo

<Uma a três frases: o que o aluno deve compreender ao fim do módulo.>

## Tópicos

- [ ] 1. <tópico>
- [ ] 2. <tópico>
- [ ] 3. <tópico>
- [ ] 4. <tópico>
- [ ] 5. <tópico>
- [ ] 6. <tópico>
- [ ] 7. <tópico>
- [ ] 8. <tópico>

## Leituras

- [[biblioteca/<area>/<livro>\|<Título>]] — <capítulos/seções>
- Leitura complementar: [[biblioteca/<area>/<livro>\|<Título>]]

## Conceitos-chave

- **<termo>:** <definição de uma linha>.

## Exercícios

1. <enunciado de múltipla escolha>

   a) <alternativa>
   b) <alternativa>
   c) <alternativa>
   d) <alternativa>

   <details>
   <summary>Gabarito</summary>

   **1.** <alternativa correta> — <explicação de 2 a 4 linhas, com o tópico ou a leitura de referência>.

   </details>

## Resultado esperado

<O que o aluno deve conseguir fazer, em uma ou duas frases.>

## Anotações

Suas anotações deste módulo vão em `pessoal/<area>/<curso>/<slug-do-modulo>.md`
(copie `_templates/anotacao.md`). Marque o progresso ali, não nesta nota.

## Próximo

[[cursos/<area>/<curso>/<próximo-slug>\|Mês <n+1> — <Tema>]]
```

- [ ] **Step 4: Criar `_templates/livro.md`**

```markdown
---
titulo: <Título>
autor: <Autor>
ano: <AAAA>
idioma: <pt|en>
nivel: <introdutorio|intermediario|avancado>
licenca: <ex.: CC BY 4.0 | dominio publico | todos os direitos reservados>
obtencao: <gratuito|compra|biblioteca>
acesso: <URL de leitura, compra ou catálogo>
verificado: <AAAA-MM>
---

# <Título>

**Autor:** <Autor> · **Ano:** <AAAA> · **Idioma:** <idioma> · **Nível:** <nível>
**Licença:** <licença> · **Como obter:** <gratuito/compra/biblioteca>

## Por que ler

<Duas a quatro linhas: o que este livro entrega e em que ele é melhor que os
outros do catálogo.>

## Como acessar

<Link de leitura gratuita, ou instrução de compra/empréstimo com o nome da
editora ou biblioteca. Nunca linkar cópia irregular.>

## Capítulos por módulo

| Módulo | Ler |
|---|---|
| [[cursos/<area>/<curso>/01-<slug>\|Mês 1 — <Tema>]] | <capítulo/seção> |

## Limitações ou vieses

<Quando relevante: data, recorte teórico, crítica conhecida. Se não houver, omitir
a seção.>

## Relacionado

- Curso: [[cursos/<area>/<curso>/00-comece-aqui\|<Curso>]]
```

- [ ] **Step 5: Criar `_templates/anotacao.md`**

```markdown
---
curso: <curso>
modulo: <n>
iniciado: <AAAA-MM-DD>
---

# Anotações — Mês <n> — <Tema>

## Progresso

- [ ] 1. <tópico>
- [ ] 2. <tópico>
- [ ] 3. <tópico>

## Resumo com minhas palavras

<Escreva sem consultar. Depois confira e corrija.>

## Dúvidas em aberto

- <pergunta>

## Relações com o que já sei

- <conexão>

## Exercícios: o que errei e por quê

- <exercício> → <motivo do erro> → <o que revisar>

## Próxima ação

- <ação concreta com data>
```

- [ ] **Step 6: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` item 1.
Expected: nenhuma quebra nova; os `<placeholders>` dos templates não são links e não aparecem como pendência. As pendências conhecidas das Tasks 2 e 4–5 continuam iguais.

- [ ] **Step 7: Commit**

```bash
git add _templates
git commit -m "feat: templates de area, curso, modulo, livro e anotacao"
```

---

### Task 4: Catálogo de livros (10 obras)

**Files:**
- Create: `biblioteca/catalogo.md`
- Create: `biblioteca/humanas/openstax-psychology-2e.md`, `noba-project.md`, `research-methods-in-psychology-wsu.md`, `introduction-to-psychology-open-text.md`, `james-principles-of-psychology.md`, `freud-conferencias-introdutorias.md`, `myers-psicologia.md`, `kahneman-rapido-e-devagar.md`, `dsm-5-tr.md`, `manual-de-publicacao-apa.md`

**Interfaces:**
- Consumes: `_templates/livro.md` (Task 3) e as chaves de frontmatter do item 4 da checklist.
- Produces: os alvos de wikilink usados pelos módulos (Tasks 5–7) e pelo hub do curso: `openstax-psychology-2e`, `noba-project`, `research-methods-in-psychology-wsu`, `introduction-to-psychology-open-text`, `james-principles-of-psychology`, `freud-conferencias-introdutorias`, `myers-psicologia`, `kahneman-rapido-e-devagar`, `dsm-5-tr`, `manual-de-publicacao-apa`.

- [ ] **Step 1: Abrir e conferir cada link candidato antes de escrever**

Para cada obra da tabela abaixo, abra a URL no navegador e confirme que a página existe, é do titular/editora correto e mostra a licença declarada. Se a URL mudou, localize a oficial pelo site do titular e registre a URL final. Se não for possível confirmar, **não crie a nota**: substitua por outra obra aberta equivalente e registre a troca no commit. Nunca deixe `acesso:` sem conferência.

| Nota | Obra | Licença esperada | `obtencao` | URL candidata |
|---|---|---|---|---|
| `openstax-psychology-2e` | OpenStax, *Psychology 2e* (2020) | CC BY 4.0 | `gratuito` | https://openstax.org/details/books/psychology-2e |
| `noba-project` | Noba Project, módulos de psicologia | CC BY-NC-SA 4.0 | `gratuito` | https://nobaproject.com |
| `research-methods-in-psychology-wsu` | Cuttler, Jhangiani & Leighton, *Research Methods in Psychology* (4ª ed., Open Text WSU) | CC BY-NC-SA 4.0 | `gratuito` | https://opentext.wsu.edu/carriecuttler/ |
| `introduction-to-psychology-open-text` | *Introduction to Psychology* (Open Textbook Library) | CC BY-NC-SA | `gratuito` | https://open.umn.edu/opentextbooks/ (buscar por "Introduction to Psychology") |
| `james-principles-of-psychology` | William James, *The Principles of Psychology* (1890) | domínio público | `gratuito` | https://www.gutenberg.org/ (buscar "Principles of Psychology") |
| `freud-conferencias-introdutorias` | Freud, *Conferências introdutórias à psicanálise* (1916–17), em tradução de domínio público | domínio público (original) | `gratuito` | https://www.gutenberg.org/ (buscar "General Introduction to Psychoanalysis") |
| `myers-psicologia` | David G. Myers, *Psicologia* (edição brasileira, Artmed) | todos os direitos reservados | `compra` | site da Artmed/Grupo A (buscar pelo título) |
| `kahneman-rapido-e-devagar` | Daniel Kahneman, *Rápido e Devagar: Duas Formas de Pensar* (Objetiva) | todos os direitos reservados | `compra` | site da editora (buscar pelo título) |
| `dsm-5-tr` | APA, *DSM-5-TR* (2022) | todos os direitos reservados | `compra` | https://www.psychiatry.org/psychiatrists/practice/dsm |
| `manual-de-publicacao-apa` | APA, *Publication Manual* (7ª ed.) | todos os direitos reservados | `compra` | https://apastyle.apa.org |

Para as três obras pagas (`myers-psicologia`, `kahneman-rapido-e-devagar`, `dsm-5-tr`) e o manual APA, a seção "Como acessar" diz onde comprar e sugere biblioteca universitária; não há link de leitura.

- [ ] **Step 2: Criar `biblioteca/humanas/openstax-psychology-2e.md` como exemplar**

```markdown
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

# Psychology 2e

**Autor:** OpenStax · **Ano:** 2020 · **Idioma:** inglês · **Nível:** introdutório
**Licença:** CC BY 4.0 · **Como obter:** gratuito, online ou PDF

## Por que ler

É o livro-texto base do curso: cobre as 16 áreas clássicas da psicologia em nível
universitário introdutório, com revisão por pares e licença aberta. Escrito em
inglês acadêmico acessível — leia um capítulo por vez e use o glossário ao final.

## Como acessar

Leitura online gratuita e PDF no site da OpenStax. Não é necessário cadastro.
Se o inglês pesar, leia primeiro o resumo do capítulo e depois o corpo do texto.

## Capítulos por módulo

| Módulo | Ler |
|---|---|
| [[cursos/humanas/psicologia/01-fundamentos-e-historia\|Mês 1 — Fundamentos e História]] | cap. 1 |
| [[cursos/humanas/psicologia/02-metodo-cientifico-e-neurociencia\|Mês 2 — Método científico e neurociência]] | caps. 2 e 3 |
| [[cursos/humanas/psicologia/03-aprendizagem-e-comportamento\|Mês 3 — Aprendizagem e comportamento]] | cap. 6 |
| [[cursos/humanas/psicologia/04-cognicao-memoria-e-inteligencia\|Mês 4 — Cognição, memória e inteligência]] | caps. 5, 7 e 8 |
| [[cursos/humanas/psicologia/05-emocoes-e-motivacao\|Mês 5 — Emoções e motivação]] | cap. 10 |
| [[cursos/humanas/psicologia/06-desenvolvimento-humano\|Mês 6 — Desenvolvimento humano]] | cap. 9 |
| [[cursos/humanas/psicologia/07-personalidade-e-diferencas-individuais\|Mês 7 — Personalidade]] | cap. 11 |
| [[cursos/humanas/psicologia/08-psicologia-social\|Mês 8 — Psicologia social]] | cap. 12 |
| [[cursos/humanas/psicologia/09-psicopatologia\|Mês 9 — Psicopatologia]] | cap. 15 |
| [[cursos/humanas/psicologia/10-abordagens-da-psicoterapia\|Mês 10 — Psicoterapia]] | cap. 16 |
| [[cursos/humanas/psicologia/11-psicanalise-e-teorias-aprofundadas\|Mês 11 — Psicanálise]] | caps. 1 e 11 (história e personalidade) |
| [[cursos/humanas/psicologia/12-psicologia-aplicada-e-integracao\|Mês 12 — Psicologia aplicada]] | caps. 13 e 14 |

## Limitações ou vieses

Cobre sobretudo a tradição anglo-americana e trata a psicanálise em poucas páginas;
para Freud, Klein, Winnicott e Lacan, use as obras do catálogo indicadas no Mês 11.
A edição é de 2020: temas de replicação e novos consensos do DSM-5-TR aparecem
superficialmente.

## Relacionado

- Curso: [[cursos/humanas/psicologia/00-comece-aqui|Psicologia]]
```

- [ ] **Step 3: Criar as outras 9 notas de livro**

Copie a estrutura do exemplar. Regras por obra:

- `noba-project`: sem capítulos numerados; na tabela use os **nomes dos módulos** do Noba (ex.: "History of Psychology", "Research Designs", "Conditioning and Learning", "Memory (Encoding, Storage, Retrieval)", "Emotion Experience and Well-Being", "The Developing Parent", "Personality Traits", "Social Cognition", "Mental Health", "Therapeutic Orientations"). Aponte 1–2 módulos por mês. `## Limitações`: licença CC BY-NC-SA impede uso comercial; cobertura irregular entre temas.
- `research-methods-in-psychology-wsu`: para os Meses 2, 9 e 12; `## Limitações` cita que os exemplos são majoritariamente de psicologia social e cognitiva.
- `introduction-to-psychology-open-text`: alternativa ao OpenStax para quem quiser segunda explicação; usar nos Meses 1, 4 e 6.
- `james-principles-of-psychology`: leitura histórica opcional do Mês 1; avisar que os dois volumes são longos e que a edição de 1890 usa termos fora de uso.
- `freud-conferencias-introdutorias`: Mês 11, com a ressalva de que a tradução disponível gratuitamente é anterior e que parte das proposições não tem sustentação empírica atual.
- `myers-psicologia`: livro-texto de referência em português, `obtencao: compra`, indicar a edição mais recente da Artmed e biblioteca universitária; `## Limitações`: custo e recorte introdutório.
- `kahneman-rapido-e-devagar`: Mês 4 (julgamento e decisão), `obtencao: compra`; `## Limitações`: parte dos achados de *priming* social não se replicou — leia junto com a literatura de replicação citada no Mês 2.
- `dsm-5-tr`: Mês 9, `obtencao: compra`, uso estritamente como referência classificatória; incluir aviso de que o manual não substitui treinamento clínico nem serve para autodiagnóstico.
- `manual-de-publicacao-apa`: Meses 2 e 12, para leitura crítica de artigos; `obtencao: compra`, com alternativa gratuita: guia resumido da APA no site.

- [ ] **Step 4: Criar `biblioteca/catalogo.md`**

```markdown
# Catálogo de livros

Metadados, licença e link de acesso de cada obra usada nos cursos. Nenhum arquivo
de livro é hospedado neste repositório: só o caminho legal até ele.

## Como ler a coluna "Acesso"

- **Gratuito** — leitura aberta, sem cadastro ou com cadastro simples.
- **Compra** — obra protegida; compre ou peça em biblioteca. Não há link de cópia.
- **Biblioteca** — disponível em acervo universitário ou serviço de empréstimo.

## Ciências Humanas

| Livro | Autor | Ano | Idioma | Nível | Licença | Acesso |
|---|---|---|---|---|---|---|
| [[biblioteca/humanas/openstax-psychology-2e\|Psychology 2e]] | OpenStax | 2020 | inglês | introdutório | CC BY 4.0 | Gratuito |
| [[biblioteca/humanas/noba-project\|Noba Project]] | vários autores | contínuo | inglês | introdutório | CC BY-NC-SA 4.0 | Gratuito |
| [[biblioteca/humanas/research-methods-in-psychology-wsu\|Research Methods in Psychology]] | Cuttler, Jhangiani & Leighton | 2019 | inglês | intermediário | CC BY-NC-SA 4.0 | Gratuito |
| [[biblioteca/humanas/introduction-to-psychology-open-text\|Introduction to Psychology]] | Open Textbook Library | — | inglês | introdutório | CC BY-NC-SA | Gratuito |
| [[biblioteca/humanas/james-principles-of-psychology\|The Principles of Psychology]] | William James | 1890 | inglês | avançado | domínio público | Gratuito |
| [[biblioteca/humanas/freud-conferencias-introdutorias\|Conferências introdutórias à psicanálise]] | Sigmund Freud | 1916–17 | português/inglês | intermediário | domínio público (original) | Gratuito |
| [[biblioteca/humanas/myers-psicologia\|Psicologia]] | David G. Myers | edição corrente | português | introdutório | todos os direitos reservados | Compra |
| [[biblioteca/humanas/kahneman-rapido-e-devagar\|Rápido e Devagar]] | Daniel Kahneman | 2011 | português | intermediário | todos os direitos reservados | Compra |
| [[biblioteca/humanas/dsm-5-tr\|DSM-5-TR]] | APA | 2022 | inglês/português | avançado | todos os direitos reservados | Compra |
| [[biblioteca/humanas/manual-de-publicacao-apa\|Publication Manual (7ª ed.)]] | APA | 2020 | inglês | intermediário | todos os direitos reservados | Compra |

## Outras áreas

Nenhum livro cadastrado ainda.
```

- [ ] **Step 5: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` itens 1, 4 e 6.
Expected: 10 notas de livro e o catálogo conformes (item 4 verde); item 1 continua acusando só os módulos das Tasks 5–7; item 6 sem PDF e com os obrigatórios ainda pendentes de Tasks 8–9.

- [ ] **Step 6: Commit**

```bash
git add biblioteca
git commit -m "feat: catalogo de 10 livros com licenca e link legal"
```

---

### Task 5: Hub do curso e módulos 1–4

**Files:**
- Create: `cursos/humanas/psicologia/00-comece-aqui.md`
- Create: `cursos/humanas/psicologia/01-fundamentos-e-historia.md`
- Create: `cursos/humanas/psicologia/02-metodo-cientifico-e-neurociencia.md`
- Create: `cursos/humanas/psicologia/03-aprendizagem-e-comportamento.md`
- Create: `cursos/humanas/psicologia/04-cognicao-memoria-e-inteligencia.md`

**Interfaces:**
- Consumes: notas de livro da Task 4 (`openstax-psychology-2e`, `noba-project`, `james-principles-of-psychology`, `myers-psicologia`, `kahneman-rapido-e-devagar`) e `_templates/modulo.md`.
- Produces: os alvos de wikilink `cursos/humanas/psicologia/0N-…` esperados pelo hub do curso; módulos 5–12 chegam nas Tasks 6 e 7, então o `## Próximo` do módulo 4 fica pendente até lá — esperado.

- [ ] **Step 1: Criar `00-comece-aqui.md`**

```markdown
---
area: humanas
curso: psicologia
nivel: introdutorio
carga-semanal: 5-7h
duracao: 12 meses
atualizado: 2026-10-27
---

# Psicologia

Curso de introdução à Psicologia para quem estuda por conta própria. A ordem é
deliberada: primeiro método científico, comportamento, cognição e desenvolvimento;
depois personalidade, psicopatologia, psicoterapia e psicanálise. Assim você
constrói critério para avaliar teorias antes de entrar nas mais discutidas.

> Este percurso não equivale a uma graduação, não inclui prática supervisionada e
> não habilita ao exercício profissional da Psicologia no Brasil.

## Carga e ritmo

5 a 7 horas por semana, um módulo por mês. Cada módulo exige cerca de 4 semanas:
duas de leitura, uma de exercícios e resumo, uma de revisão.

## Módulos

| Mês | Tema |
|---|---|
| 1 | [[cursos/humanas/psicologia/01-fundamentos-e-historia\|Fundamentos e história]] |
| 2 | [[cursos/humanas/psicologia/02-metodo-cientifico-e-neurociencia\|Método científico e neurociência]] |
| 3 | [[cursos/humanas/psicologia/03-aprendizagem-e-comportamento\|Aprendizagem e comportamento]] |
| 4 | [[cursos/humanas/psicologia/04-cognicao-memoria-e-inteligencia\|Cognição, memória e inteligência]] |
| 5 | [[cursos/humanas/psicologia/05-emocoes-e-motivacao\|Emoções e motivação]] |
| 6 | [[cursos/humanas/psicologia/06-desenvolvimento-humano\|Desenvolvimento humano]] |
| 7 | [[cursos/humanas/psicologia/07-personalidade-e-diferencas-individuais\|Personalidade e diferenças individuais]] |
| 8 | [[cursos/humanas/psicologia/08-psicologia-social\|Psicologia social e relações humanas]] |
| 9 | [[cursos/humanas/psicologia/09-psicopatologia\|Psicopatologia]] |
| 10 | [[cursos/humanas/psicologia/10-abordagens-da-psicoterapia\|Abordagens da psicoterapia]] |
| 11 | [[cursos/humanas/psicologia/11-psicanalise-e-teorias-aprofundadas\|Psicanálise e teorias aprofundadas]] |
| 12 | [[cursos/humanas/psicologia/12-psicologia-aplicada-e-integracao\|Psicologia aplicada e integração]] |

## Leituras

**Obrigatórias**

- [[biblioteca/humanas/openstax-psychology-2e|Psychology 2e — OpenStax]] — livro-texto base, capítulos indicados em cada módulo (gratuito, em inglês)
- [[biblioteca/humanas/noba-project|Noba Project]] — módulos curtos para revisar tema específico (gratuito, em inglês)

**Opcionais**

- [[biblioteca/humanas/myers-psicologia|Psicologia — David G. Myers]] — em português, para quem prefere o texto-base no idioma nativo
- [[biblioteca/humanas/kahneman-rapido-e-devagar|Rápido e Devagar — Kahneman]] — complemento do Mês 4

## Rotina semanal sugerida (6 h)

| Atividade | Horas/semana |
|---|---:|
| Leitura de livro-texto | 2 |
| Videoaulas universitárias | 1 |
| Leitura complementar | 1 |
| Resumos e mapas conceituais | 1 |
| Exercícios e revisão | 1 |

## Conclusão

Você conclui o curso quando consegue explicar os conceitos, comparar teorias
concorrentes, identificar evidências favoráveis e contrárias e aplicar conceitos a
exemplos sem extrapolar os dados.

Progresso e anotações: `pessoal/humanas/psicologia/progresso.md`.
```

- [ ] **Step 2: Criar `01-fundamentos-e-historia.md` (exemplar de módulo)**

Conteúdo completo, com 10 tópicos e 8 exercícios:

```markdown
---
curso: psicologia
area: humanas
ordem: 1
duracao: 4 semanas
atualizado: 2026-10-27
---

# Mês 1 — Fundamentos e História

## Objetivo

Compreender o que a Psicologia estuda e como surgiram as escolas que ainda hoje
disputam a explicação do comportamento, distinguindo escola histórica de evidência
científica atual.

## Tópicos

- [ ] 1. O que é Psicologia e quais fenômenos ela estuda
- [ ] 2. Diferenças entre Psicologia, Psiquiatria, Filosofia e Neurociência
- [ ] 3. História da Psicologia científica
- [ ] 4. Estruturalismo — Wilhelm Wundt e Edward Titchener
- [ ] 5. Funcionalismo — William James
- [ ] 6. Behaviorismo — John Watson e B. F. Skinner
- [ ] 7. Psicanálise — Sigmund Freud
- [ ] 8. Psicologia da Gestalt
- [ ] 9. Psicologia humanista — Carl Rogers e Abraham Maslow
- [ ] 10. Revolução cognitiva e Psicologia contemporânea

## Leituras

- [[biblioteca/humanas/openstax-psychology-2e|Psychology 2e]] — cap. 1 (Introdução à Psicologia)
- [[biblioteca/humanas/noba-project|Noba Project]] — módulos "History of Psychology" e "The Nature-Nurture Question"
- Leitura histórica opcional: [[biblioteca/humanas/james-principles-of-psychology|The Principles of Psychology]] — prefácio e cap. 1

## Conceitos-chave

- **Psicologia:** estudo científico do comportamento e dos processos mentais.
- **Escola (de pensamento):** tradição que compartilha objeto, método e vocabulário próprios.
- **Introspecção:** relato sistemático da própria experiência, método do estruturalismo.
- **Estruturalismo:** decompor a mente em elementos básicos.
- **Funcionalismo:** explicar processos mentais pelo papel que cumprem na adaptação.
- **Behaviorismo:** estudar comportamento observável, recusando explicações mentalistas.
- **Psicanálise:** teoria e método clínico que atribui papel central ao inconsciente.
- **Gestalt:** princípios de organização perceptiva: o todo não é a soma das partes.
- **Humanismo:** ênfase na experiência subjetiva, no crescimento e na autoatualização.
- **Revolução cognitiva:** retorno dos processos mentais como objeto, com método experimental e modelos de processamento.

## Exercícios

1. Qual afirmação descreve corretamente o objeto da Psicologia contemporânea?

   a) Estudo da alma, com método filosófico.
   b) Estudo científico do comportamento e dos processos mentais.
   c) Estudo exclusivo de transtornos mentais.
   d) Estudo do cérebro, com exclusão do comportamento.

   <details>
   <summary>Gabarito</summary>

   **1.** b — A Psicologia contemporânea investiga comportamento e processos mentais com método científico (OpenStax, cap. 1, seção "What Is Psychology?").

   </details>

2. A principal diferença entre Psiquiatria e Psicologia é:

   a) A Psiquiatria trata apenas crianças; a Psicologia, adultos.
   b) A Psiquiatria é médica e pode prescrever; a Psicologia não prescreve.
   c) A Psicologia é científica; a Psiquiatria não.
   d) Não há diferença prática.

   <details>
   <summary>Gabarito</summary>

   **2.** b — Psiquiatria é especialidade médica, com prescrição de psicofármacos; a Psicologia forma profissionais que não prescrevem (tópico 2).

   </details>

3. O estruturalismo de Wundt e Titchener caracteriza-se por:

   a) Estudar a função adaptativa da consciência.
   b) Decompor a experiência consciente em elementos com introspecção controlada.
   c) Descrever o inconsciente por associação livre.
   d) Medir tempo de reação em tarefas de aprendizagem.

   <details>
   <summary>Gabarito</summary>

   **3.** b — Introspecção como método e elementos da consciência como objeto: o "o quê" da mente (OpenStax, cap. 1, "Structuralism").

   </details>

4. Explique, em 3 a 5 linhas, por que o funcionalismo de William James é considerado uma resposta ao estruturalismo.

   <details>
   <summary>Gabarito</summary>

   **4.** O estruturalismo pergunta *o que* compõe a mente; James pergunta *para que* ela serve. O foco passa do elemento estático à função adaptativa da consciência, o que aproxima a Psicologia da biologia e da teoria da evolução. Critério: apontar a troca de "elementos" por "função/adaptação".

   </details>

5. Descreva a diferença central entre behaviorismo e psicanálise quanto ao que é considerado dado legítimo para a Psicologia.

   <details>
   <summary>Gabarito</summary>

   **5.** O behaviorismo aceita apenas comportamento observável e controle por ambiente; a psicanálise trabalha com conteúdo inconsciente inferido de sonhos, atos falhos e fala do paciente. Um recusa o inobservável como evidência; o outro o toma como núcleo. Critério: mencionar o observável contra o inconsciente inferido.

   </details>

6. Em que sentido a psicologia humanista se opõe tanto ao behaviorismo quanto à psicanálise?

   <details>
   <summary>Gabarito</summary>

   **6.** Recusa o determinismo (ambiental, no behaviorismo; pulsional, na psicanálise) e coloca a experiência subjetiva, a liberdade de escolha e a tendência de crescimento no centro. Critério: nomear determinismo e experiência subjetiva.

   </details>

7. Uma reportagem afirma: "a Gestalt provou que o todo é maior que a soma das partes". Reescreva a frase de forma mais precisa, explicando o que os estudos de percepção mostraram.

   <details>
   <summary>Gabarito</summary>

   **7.** Os estudos mostram que a percepção é organizada por princípios (proximidade, semelhança, fechamento, continuidade) e não por soma de sensações isoladas — o percepto depende da configuração. "Provar" é forte demais: são regularidades experimentais, não uma tese metafísica. Critério: princípios de organização + ressalva sobre "provar".

   </details>

8. Um estudante diz: "Freud foi o pai da psicologia e já provou que tudo é inconsciente". Aponte dois erros na afirmação e reescreva-a de modo defensável.

   <details>
   <summary>Gabarito</summary>

   **8.** (i) A Psicologia científica é anterior a Freud (Wundt, 1879); (ii) "provou" é inadequado — proposições psicanalíticas têm sustentação empírica desigual e parte não é testável como formulação original. Reescrita aceitável: "Freud criou uma tradição clínica que colocou o inconsciente no centro, com influência cultural ampla e evidência científica heterogênea". Critério: reconhecer Wundt e qualificar a evidência.

   </details>

## Resultado esperado

Você deve conseguir comparar as escolas históricas (objeto, método, o que cada uma
rejeita) e explicar por que uma escola histórica não é automaticamente evidência
científica atual.

## Anotações

Suas anotações deste módulo vão em `pessoal/humanas/psicologia/01-fundamentos-e-historia.md`
(copie `_templates/anotacao.md`). Marque o progresso ali, não nesta nota.

## Próximo

[[cursos/humanas/psicologia/02-metodo-cientifico-e-neurociencia|Mês 2 — Método científico e neurociência]]
```

- [ ] **Step 3: Criar o módulo 2 (`02-metodo-cientifico-e-neurociencia.md`)**

Mesma estrutura do exemplar, com 10 tópicos copiados do plano de origem (seção
"Mês 2 — Método científico e bases biológicas"): método científico aplicado à
Psicologia; hipóteses, teorias e experimentos; correlação versus causalidade; viés
de confirmação e vieses de pesquisa; estatística básica, validade, confiabilidade e
replicação; sistema nervoso central e periférico; neurônios, sinapses e
neurotransmissores; estruturas e funções do cérebro; sistema límbico e emoção;
neuroplasticidade, genética e ambiente.

Leituras: OpenStax caps. 2 e 3; `research-methods-in-psychology-wsu` (capítulos 1–3);
`manual-de-publicacao-apa` apenas como referência de leitura crítica.

Exercícios (8): 3 de múltipla escolha sobre correlação/causalidade, validade e
estrutura do neurônio; 3 discursivas sobre replicação, viés de confirmação e
diferença entre correlação e causa; 2 de aplicação — (a) uma manchete que confunde
correlação com causa, (b) um estudo com amostra pequena e sem replicação.

- [ ] **Step 4: Criar o módulo 3 (`03-aprendizagem-e-comportamento.md`)**

Tópicos da seção "Mês 3 — Aprendizagem e comportamento" (10 itens, de comportamento
reflexo a comportamento governado por regras). Leituras: OpenStax cap. 6;
`noba-project` módulos "Conditioning and Learning" e "Operant Conditioning".

Exercícios (8): 3 de múltipla escolha sobre reforço positivo/negativo, punição e
extinção; 3 discursivas sobre condicionamento clássico versus operante, aprendizagem
observacional e análise funcional; 2 de aplicação — (a) um hábito de estudo que se
mantém por reforço negativo, (b) um caso de generalização de medo.

- [ ] **Step 5: Criar o módulo 4 (`04-cognicao-memoria-e-inteligencia.md`)**

Tópicos da seção "Mês 4 — Psicologia cognitiva" (10 itens, de sensação e percepção a
tomada de decisões e metacognição). Incluir a lista de autores do plano de origem
(Neisser, Kahneman, Tversky, Miller, Baddeley) dentro do objetivo ou da seção de
leituras. Leituras: OpenStax caps. 5, 7 e 8; `noba-project` módulos de memória e
atenção; `kahneman-rapido-e-devagar` como complemento (capítulos sobre heurísticas).

Exercícios (8): 3 de múltipla escolha sobre memória de trabalho, heurísticas e
falsas memórias; 3 discursivas sobre codificação/recuperação, vieses cognitivos e
limites da introspecção; 2 de aplicação — (a) por que testemunho ocular é frágil,
(b) um erro de julgamento explicado por heurística de disponibilidade.

- [ ] **Step 6: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` itens 1, 3 e 5.
Expected: os quatro módulos passam no item 3 (frontmatter, 8 seções, ≥8 tópicos, 8–10 exercícios, gabarito, instrução `pessoal/`); o hub do curso passa no item 5; o item 1 continua acusando apenas os módulos 5–12.

- [ ] **Step 7: Commit**

```bash
git add cursos/humanas/psicologia
git commit -m "feat: hub do curso de psicologia e modulos 1 a 4"
```

---

### Task 6: Módulos 5–8

**Files:**
- Create: `cursos/humanas/psicologia/05-emocoes-e-motivacao.md`
- Create: `cursos/humanas/psicologia/06-desenvolvimento-humano.md`
- Create: `cursos/humanas/psicologia/07-personalidade-e-diferencas-individuais.md`
- Create: `cursos/humanas/psicologia/08-psicologia-social.md`

**Interfaces:**
- Consumes: `_templates/modulo.md`, notas de livro da Task 4 e o padrão do módulo 1 (Task 5).
- Produces: módulos 5–8, com `## Próximo` encadeando até o 9.

- [ ] **Step 1: Criar o módulo 5 (`05-emocoes-e-motivacao.md`)**

Tópicos da seção "Mês 5 — Emoções e motivação" (10 itens, de emoções/sentimentos/humor
a relação entre emoção, cognição e comportamento). Leituras: OpenStax cap. 10;
`noba-project` módulos sobre emoção e motivação.

Exercícios (8): 3 de múltipla escolha sobre James-Lange, Cannon-Bard e Schachter-Singer;
3 discursivas sobre avaliação cognitiva, regulação emocional e teoria da
autodeterminação; 2 de aplicação — (a) ansiedade antes de prova interpretada por duas
teorias diferentes, (b) queda de motivação intrínseca quando se introduz recompensa
externa.

- [ ] **Step 2: Criar o módulo 6 (`06-desenvolvimento-humano.md`)**

Tópicos da seção "Mês 6 — Psicologia do desenvolvimento" (10 itens, de hereditariedade
versus ambiente a desenvolvimento moral). Leituras: OpenStax cap. 9; `noba-project`
módulos sobre desenvolvimento na infância e apego; `introduction-to-psychology-open-text`
como segunda explicação.

Exercícios (8): 3 de múltipla escolha sobre estágios de Piaget, zona de desenvolvimento
proximal e tipos de apego; 3 discursivas sobre Erikson, crítica à noção de estágios e
Kohlberg; 2 de aplicação — (a) criança que conserva volume em uma tarefa piagetiana,
(b) interpretação apressada de um teste de apego.

- [ ] **Step 3: Criar o módulo 7 (`07-personalidade-e-diferencas-individuais.md`)**

Tópicos da seção "Mês 7 — Personalidade" (10 itens, de conceito de personalidade a
avaliação e limitações dos testes). Leituras: OpenStax cap. 11; `noba-project`
módulos "Personality Traits" e "Personality Assessment"; `myers-psicologia`
(compra) como alternativa em português.

Exercícios (8): 3 de múltipla escolha sobre id/ego/superego, Big Five e testes
projetivos; 3 discursivas sobre Jung, Adler e limites psicométricos; 2 de aplicação —
(a) resultado de teste de revista interpretado sem validade, (b) comparação entre
teoria dos traços e explicação psicodinâmica para o mesmo comportamento.

- [ ] **Step 4: Criar o módulo 8 (`08-psicologia-social.md`)**

Tópicos da seção "Mês 8 — Psicologia social" (10 itens, de cognição social a atração
interpessoal). Exigência específica do plano de origem: estudar experimentos clássicos
**com suas críticas metodológicas e éticas**; incluir na seção de leituras uma nota
sobre isso e cobrar em pelo menos dois exercícios (Asch e Milgram: validade ecológica,
ética, generalização). Leituras: OpenStax cap. 12; `noba-project` módulos "Social
Cognition" e "Conformity and Obedience".

Exercícios (8): 3 de múltipla escolha sobre dissonância cognitiva, conformidade e
atribuição; 3 discursivas sobre obediência à autoridade, preconceito e influência
social; 2 de aplicação — (a) revisão ética de um experimento hipotético, (b) efeito de
grupo em decisão.

- [ ] **Step 5: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` itens 1 e 3.
Expected: módulos 1–8 conformes no item 3; item 1 acusa apenas os módulos 9–12 e os obrigatórios das Tasks 8–9.

- [ ] **Step 6: Commit**

```bash
git add cursos/humanas/psicologia
git commit -m "feat: modulos 5 a 8 de psicologia"
```

---

### Task 7: Módulos 9–12

**Files:**
- Create: `cursos/humanas/psicologia/09-psicopatologia.md`
- Create: `cursos/humanas/psicologia/10-abordagens-da-psicoterapia.md`
- Create: `cursos/humanas/psicologia/11-psicanalise-e-teorias-aprofundadas.md`
- Create: `cursos/humanas/psicologia/12-psicologia-aplicada-e-integracao.md`

**Interfaces:**
- Consumes: `_templates/modulo.md`, notas de livro da Task 4, padrão do módulo 1.
- Produces: módulos 9–12; o módulo 12 usa `## Próximo` com "Fim do curso" e link para o hub.

- [ ] **Step 1: Criar o módulo 9 (`09-psicopatologia.md`)**

Tópicos da seção "Mês 9 — Psicopatologia" (14 itens, de saúde mental a fatores de
risco e prevenção). Leituras: OpenStax cap. 15; `dsm-5-tr` (referência classificatória,
compra); `noba-project` módulos sobre saúde mental.

Exigências de segurança do conteúdo, obrigatórias no texto: seção de objetivo com
aviso de que reconhecer sintomas não é diagnosticar; exercícios nunca pedem diagnóstico
de caso; incluir em "Conceitos-chave" a distinção entre modelo biopsicossocial e
modelo categorial do DSM.

Exercícios (8): 3 de múltipla escolha sobre critérios gerais de transtorno, diferença
DSM-5-TR/CID-11 e modelo biopsicossocial; 3 discursivas sobre normalidade e cultura,
comorbidade e limites da classificação; 2 de aplicação — (a) caso com sintomas que
exigem encaminhamento profissional (a resposta deve indicar encaminhamento, não
diagnóstico), (b) por que um sintoma isolado não define transtorno.

- [ ] **Step 2: Criar o módulo 10 (`10-abordagens-da-psicoterapia.md`)**

Tópicos da seção "Mês 10 — Abordagens da psicoterapia" (12 itens, de fundamentos da
psicoterapia a ética e limites profissionais). Leituras: OpenStax cap. 16;
`noba-project` módulo "Therapeutic Orientations".

Exercícios (8): 3 de múltipla escolha sobre aliança terapêutica, TCC e ACT; 3
discursivas sobre diferenças entre abordagens, evidência de eficácia e ética; 2 de
aplicação — (a) escolher abordagem para um caso e justificar sem prescrever,
(b) por que "terapia funciona" não significa "qualquer terapia funciona para tudo".

- [ ] **Step 3: Criar o módulo 11 (`11-psicanalise-e-teorias-aprofundadas.md`)**

Tópicos da seção "Mês 11 — Psicanálise e aprofundamento teórico" (12 itens, do
surgimento da psicanálise a críticas epistemológicas). Leituras: `freud-conferencias-introdutorias`
(domínio público) para as conferências 1–5; `noba-project` para contraste com a
psicologia científica; OpenStax cap. 1 (história) e cap. 11 (personalidade).

Exigência: cada tópico teórico termina com uma linha sobre nível de evidência; a seção
"Resultado esperado" exige distinguir tradição clínica de hipótese testável.

Exercícios (8): 3 de múltipla escolha sobre primeira/segunda tópica, repressão e
transferência; 3 discursivas sobre Klein, Winnicott e Lacan; 2 de aplicação —
(a) classificar uma afirmação psicanalítica como testável ou não, (b) comparar
explicação psicanalítica e comportamental do mesmo sintoma.

- [ ] **Step 4: Criar o módulo 12 (`12-psicologia-aplicada-e-integracao.md`)**

Tópicos da seção "Mês 12 — Psicologia aplicada e integração" (11 itens, de psicologia
organizacional a integração entre explicações biológicas, cognitivas, comportamentais
e sociais). Leituras: OpenStax caps. 13 e 14; `noba-project` módulos de psicologia
organizacional e saúde; `manual-de-publicacao-apa` para leitura crítica.

Exercícios (8): 3 de múltipla escolha sobre psicologia organizacional, psicologia da
saúde e limites da psicologia positiva; 3 discursivas sobre ética na pesquisa,
leitura crítica de um artigo e integração de níveis de explicação; 2 de aplicação —
(a) avaliar um programa de bem-estar corporativo com base em evidência, (b) integrar
explicações biológica, cognitiva e social para um mesmo fenômeno.

`## Próximo` deste módulo:

```markdown
[[cursos/humanas/psicologia/00-comece-aqui|Fim do curso — volte ao início]]
```

- [ ] **Step 5: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` itens 1, 3 e 5.
Expected: 12 módulos conformes; hub do curso com 12 links resolvidos; item 1 sem nenhuma quebra interna.

- [ ] **Step 6: Commit**

```bash
git add cursos/humanas/psicologia
git commit -m "feat: modulos 9 a 12 de psicologia"
```

---

### Task 8: Camada de agentes

**Files:**
- Create: `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md`
- Create: `_meta/agentes/tutor.md`, `_meta/agentes/avaliador.md`, `_meta/agentes/plano.md`

**Interfaces:**
- Consumes: estrutura de pastas e convenções das Tasks 1–7.
- Produces: `AGENTS.md` como fonte única de regra, referenciada por `INICIO.md` e pelos adaptadores.

- [ ] **Step 1: Criar `AGENTS.md`**

```markdown
# Instruções para agentes de IA — Alexandria

Este repositório é um vault de estudo. Quem o abre espera um tutor, não um gerador
de resumo genérico. Siga estas regras em qualquer agente, em qualquer sistema
operacional.

## Papel

Atue como tutor socrático: explique em camadas (intuição → definição → exemplo →
exceção), verifique entendimento com uma pergunta antes de avançar e só então
aprofunde. Corrija exercícios com rubrica, não com elogio vazio. Quando o usuário
pedir plano, adapte o curso existente em vez de inventar um novo.

## Navegação (leia pouco)

1. `INICIO.md` → hub da área (`areas/`) → hub do curso (`cursos/<area>/<curso>/00-comece-aqui.md`)
   → módulo em estudo.
2. Leia apenas o módulo atual e as notas de livro que ele cita. Nunca varra o vault
   inteiro nem abra `biblioteca/catalogo.md` inteiro sem necessidade.
3. Progresso e anotações do aluno ficam em `pessoal/` (fora do git).

## Limites de conteúdo

- Não diagnostique, não prescreva, não simule sessão clínica e não afirme que o
  usuário tem transtorno. Diante de sofrimento intenso, risco de autoagressão ou
  uso de substâncias, oriente procurar profissional habilitado ou serviço de saúde.
- Não ensine técnica clínica como se o usuário pudesse aplicá-la em terceiros.
- Não transforme escola histórica em evidência atual: sinalize o nível de sustentação
  empírica de teorias (psicanálise incluída).
- Não prometa resultado terapêutico nem substitua acompanhamento profissional.

## Fontes

- Cite apenas obras presentes em `biblioteca/`, com autor, capítulo ou seção.
- Se a informação não estiver no vault, diga o que falta e ofereça buscar fonte
  externa confiável (universidade, periódico, órgão oficial), deixando claro que é
  externa.
- Nunca invente referência, DOI, página, capítulo ou citação literal.
- Respeite licença: obra `gratuito` pode ser lida no link; obra `compra` ou
  `biblioteca` não pode ser reproduzida nem pirateada. Nunca sugira site de PDF
  irregular.
- Trecho citado de obra protegida: no máximo paráfrase curta com referência, nunca
  cópia extensa.

## Exercícios

- Use primeiro os exercícios do módulo; só gere novos se o usuário pedir.
- Ao corrigir discursiva, diga o que faltou (conceito, comparação, evidência) e qual
  seção reler.
- Registre o resultado em `pessoal/<area>/<curso>/progresso.md` quando o usuário
  pedir, com data e o que errou.

## Escrita no repositório

- Escreva somente em `pessoal/`. Nunca altere `cursos/`, `areas/`, `biblioteca/` ou
  `_meta/` sem pedido explícito.
- Sugestão de melhoria no conteúdo versionado: mostre o diff proposto e espere
  aprovação.
- Antes de propor commit em qualquer arquivo do vault, execute a checklist de
  `_meta/VERIFICACAO.md` com suas próprias ferramentas (busca de arquivos e leitura).
  Não há script a rodar.

## Idioma e forma

Português do Brasil; termos técnicos no original entre parênteses quando ajudam.
Resposta curta e direta, com link do vault para o que for citado. Sem preâmbulo,
sem repetir o pedido.
```

- [ ] **Step 2: Criar os adaptadores**

`CLAUDE.md`:

```markdown
# Claude Code — Alexandria

Leia `AGENTS.md` na raiz e siga-o como fonte única de regras: papel de tutor,
limites de conteúdo, política de fontes e escrita restrita a `pessoal/`.

Específico deste host: use `_meta/agentes/tutor.md` como roteiro de explicação e
`_meta/agentes/avaliador.md` ao corrigir exercícios. Não carregue o vault inteiro
no contexto: siga a ordem de navegação do `AGENTS.md`.
```

`GEMINI.md`: mesmo texto, trocando o título para `Gemini CLI / Antigravity — Alexandria` e a linha específica por: "Específico deste host: prefira respostas curtas com link do vault e confirme entendimento antes de avançar de tópico."

`.github/copilot-instructions.md`:

```markdown
# Copilot — Alexandria

Siga `AGENTS.md` (raiz) como fonte única de regras. Resuma o módulo em estudo,
não o vault inteiro. Nunca diagnostique nem prescreva. Cite apenas obras de
`biblioteca/`, com capítulo, e nunca invente referência. Escrita apenas em `pessoal/`.
```

- [ ] **Step 3: Criar `_meta/agentes/tutor.md`**

```markdown
# Playbook — tutor

## Sequência de uma explicação

1. **Pergunta de partida:** o que o usuário já sabe sobre o conceito (uma pergunta,
   não um questionário).
2. **Intuição:** uma frase com exemplo do cotidiano, sem termo técnico.
3. **Definição:** o conceito com o vocabulário do módulo, citando a leitura.
4. **Exemplo e contraexemplo:** um caso que se aplica e um que não se aplica.
5. **Exceção ou crítica:** limite do conceito, evidência contrária, versão atual.
6. **Checagem:** uma pergunta que exija aplicar, não repetir.
7. **Próximo passo:** tópico seguinte do módulo ou exercício correspondente.

## Regras

- Uma pergunta por vez; espere a resposta.
- Se o usuário errar, aponte a parte correta antes de corrigir o resto.
- Nunca entregue resumo pronto do módulo inteiro quando o pedido é dúvida pontual.
- Se o conceito não estiver no módulo, diga em qual módulo do curso ele aparece.
- Anotação sugerida vai para `pessoal/<area>/<curso>/<slug>.md`, com o formato de
  `_templates/anotacao.md`.
```

- [ ] **Step 4: Criar `_meta/agentes/avaliador.md`**

```markdown
# Playbook — avaliador

## Rubrica para discursivas

| Critério | Peso | O que conta |
|---|---:|---|
| Conceito correto | 2 | Usa o termo como o módulo define |
| Comparação/relação | 2 | Distingue de teoria concorrente ou de caso próximo |
| Evidência ou exemplo | 1 | Cita achado, estudo ou caso pertinente |
| Limite/qualificação | 1 | Não extrapola o que a evidência permite |

Nota de 0 a 6. Abaixo de 4: reler a seção indicada e refazer o exercício.

## Como corrigir

1. Diga o que está certo, em uma frase.
2. Diga o que falta, citando o critério e o tópico.
3. Dê a resposta-modelo em no máximo 5 linhas.
4. Indique a leitura exata (livro e capítulo do catálogo).
5. Se o erro for conceitual, proponha um exercício novo do mesmo tópico.

## Registro

Quando o usuário pedir, acrescente em `pessoal/<area>/<curso>/progresso.md`:

```markdown
- 2026-10-27 — Mês 1, exercício 5 — errei a distinção behaviorismo/psicanálise — revisar tópico 6
```

## Proibições

Não diagnostique o usuário, não avalie "personalidade" ou "saúde mental" a partir
das respostas e não use os exercícios como instrumento psicológico.
```

- [ ] **Step 5: Criar `_meta/agentes/plano.md`**

```markdown
# Playbook — plano de estudos

## Entrada

Área, curso, horas por semana disponíveis, data de início e objetivo do usuário.

## Saída

Plano em tabela, com semanas numeradas:

| Semana | Módulo | Tópicos | Leitura (capítulo) | Exercícios | Revisão |
|---|---|---|---|---|---|

## Regras

- Use os módulos existentes; não crie módulo novo sem pedido.
- Redistribua tópicos, nunca reordene pré-requisitos: método científico e
  aprendizagem vêm antes de personalidade e psicopatologia.
- Reserve 1 semana de revisão a cada 4 semanas de conteúdo.
- Some as horas e mostre o total; se não couber, corte leitura opcional primeiro.
- Entregue também um bloco de checkboxes para colar em
  `pessoal/<area>/<curso>/progresso.md`.
- Termine com o critério de conclusão do curso, copiado do hub.
```

- [ ] **Step 6: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` itens 1 e 6.
Expected: item 1 verde; item 6 ainda acusa os três arquivos de `_meta/` da Task 9 e nenhum outro.

- [ ] **Step 7: Commit**

```bash
git add AGENTS.md CLAUDE.md GEMINI.md .github _meta/agentes
git commit -m "feat: camada de agentes (AGENTS.md, adaptadores e playbooks)"
```

---

### Task 9: Contribuição, convenções e fontes

**Files:**
- Create: `_meta/COMO-CONTRIBUIR.md`, `_meta/CONVENCOES.md`, `_meta/FONTES.md`

**Interfaces:**
- Consumes: convenções já aplicadas nas Tasks 1–8.
- Produces: os três arquivos obrigatórios do item 6 da checklist e os links a partir de `INICIO.md`.

- [ ] **Step 1: Criar `_meta/COMO-CONTRIBUIR.md`**

```markdown
# Como contribuir

## Antes de abrir PR

1. Percorra `_meta/VERIFICACAO.md` inteira e resolva todas as pendências.
2. Confira que nenhum PDF, EPUB ou trecho longo de obra protegida entrou no commit.
3. Um PR por assunto: um curso novo, uma correção de módulo, um livro novo.

## Adicionar uma área

1. Copie `_templates/area.md` para `areas/<slug>.md` e preencha o frontmatter.
2. Inclua a área na tabela de `INICIO.md` e na de `README.md`.
3. Se a área ainda não tem curso, a tabela fica com "Nenhum curso publicado ainda."

## Adicionar um curso

1. Crie a pasta `cursos/<area>/<curso>/`.
2. Copie `_templates/curso.md` para `00-comece-aqui.md`; preencha frontmatter, aviso
   de que não equivale a graduação, carga, tabela de módulos, leituras e rotina.
3. Copie `_templates/modulo.md` para cada módulo, com prefixo `NN-`.
4. Cada módulo precisa das 8 seções e de 8 a 10 exercícios com gabarito em
   `<details><summary>Gabarito</summary>`.
5. Cadastre as leituras em `biblioteca/<area>/` (modelo `_templates/livro.md`) e na
   tabela de `biblioteca/catalogo.md`.
6. Inclua o curso no hub da área e o link de progresso em `pessoal/`.

## Adicionar um livro

1. Abra o link e confirme que é do titular ou de repositório legítimo.
2. Preencha `licenca`, `obtencao` e `verificado` (AAAA-MM). Obra paga: `obtencao:
   compra` ou `biblioteca`, com instrução de aquisição — nunca link de cópia.
3. Preencha "Por que ler", "Como acessar" e "Capítulos por módulo".
4. Inclua a linha no catálogo.

## Corrigir conteúdo

Abra issue ou PR com: módulo, trecho, o que está errado, fonte que sustenta a
correção (livro e capítulo, artigo com DOI ou documento oficial).

## Ferramentas

Não há script no repositório, de propósito: ele abre igual no Windows, no macOS e no
Linux e serve também de contexto para agentes de IA. A verificação é a checklist de
`_meta/VERIFICACAO.md`.
```

- [ ] **Step 2: Criar `_meta/CONVENCOES.md`**

```markdown
# Convenções do vault

## Nomes

- Pastas e arquivos: `kebab-case`, ASCII, minúsculas, sem acento nem `ç`.
- Módulos: prefixo de dois dígitos (`01-…`).
- Um nome de arquivo só pode existir uma vez no vault inteiro — `[[wikilink]]`
  resolve por nome. O item 1 da checklist reprova duplicata.

## Estrutura de uma nota

- H1 único, em português, com o nome legível.
- Módulo: exatamente as 8 seções, nesta ordem: Objetivo, Tópicos, Leituras,
  Conceitos-chave, Exercícios, Resultado esperado, Anotações, Próximo.
- Livro: frontmatter completo, "Por que ler", "Como acessar", "Capítulos por módulo".
- Acima de ~150 linhas, divida a nota em duas.

## Frontmatter

Chaves por tipo de nota (todas obrigatórias):

- Área: `area`
- Curso: `area`, `curso`, `nivel`, `carga-semanal`, `duracao`, `atualizado`
- Módulo: `curso`, `area`, `ordem`, `duracao`, `atualizado`
- Livro: `titulo`, `autor`, `ano`, `idioma`, `nivel`, `licenca`, `obtencao`,
  `acesso`, `verificado`

Datas em `AAAA-MM-DD`; `verificado` em `AAAA-MM`.

## Links

- Dentro do vault: `[[caminho/do/arquivo|texto visível]]`.
- Em `README.md`: link relativo markdown (`[texto](caminho/arquivo.md)`), porque
  wikilink não renderiza no GitHub.
- Link externo sempre com URL completa e conferida.

## Exercícios

- 8 a 10 por módulo: 3 múltipla escolha, 3 discursivas, 2 de aplicação.
- Gabarito dentro de `<details><summary>Gabarito</summary>`.
- Questão autoral; não copie exercício de livro protegido.

## Tom

Explicativo e direto, sem sensacionalismo. Teoria contestada é apresentada com o
nível de evidência, não como fato estabelecido.

## Portabilidade

Nada de script, binário, caminho absoluto de máquina ou comando específico de
sistema operacional. O vault é Markdown puro e abre em Windows, macOS e Linux.
```

- [ ] **Step 3: Criar `_meta/FONTES.md`**

```markdown
# Política de fontes e licenças

## Regra

O vault publica metadados e links. Não hospeda PDF, EPUB, digitalização nem trecho
longo de obra protegida.

## O que pode entrar

- Obra com licença aberta explícita (CC BY, CC BY-SA, CC BY-NC, CC BY-NC-SA,
  domínio público), com a licença no campo `licenca` e no texto da nota.
- Obra paga ou sem licença aberta: só metadados e link para editora, livraria ou
  catálogo de biblioteca, com `obtencao: compra` ou `obtencao: biblioteca`.
- Repositório institucional ou biblioteca digital que distribua o arquivo
  legalmente pelo próprio titular.

## O que não pode entrar

- Link para site de PDF pirata, espelho de livro, "biblioteca" de arquivos sem
  licença, grupo de mensagens ou drive compartilhado.
- Arquivo de livro no repositório, mesmo "temporário".
- Cópia extensa de capítulo, tabela ou figura protegida.

## Verificação

- Todo livro tem `verificado: AAAA-MM` preenchido depois de abrir o link.
- Revisão periódica: a cada seis meses, reabrir os links do catálogo e atualizar
  `verificado`; link morto é corrigido ou a obra sai do catálogo.
- A checklist cobre apenas links internos; link externo é conferência manual.

## Remoção

Se um titular contestar um link, ele é removido no próximo commit e a nota fica com
"obra indisponível no catálogo" até a substituição. Contato: abrir issue no
repositório.

## Licença do conteúdo próprio

Texto original do vault: CC BY-SA 4.0 (`LICENSE`). Obras citadas permanecem com
seus titulares.
```

- [ ] **Step 4: Verificar com a checklist**

Percorra `_meta/VERIFICACAO.md` **inteira**, itens 1 a 7.
Expected: zero pendência. O repositório está completo nesta altura.

- [ ] **Step 5: Commit**

```bash
git add _meta/COMO-CONTRIBUIR.md _meta/CONVENCOES.md _meta/FONTES.md
git commit -m "docs: contribuicao, convencoes e politica de fontes"
```

---

### Task 10: Verificação final e publicação

**Files:**
- Modify: `README.md` (acrescentar "Estrutura do repositório")

**Interfaces:**
- Consumes: todo o vault.
- Produces: repositório pronto para push com a checklist de ponta a ponta verde.

- [ ] **Step 1: Acrescentar a seção "Estrutura do repositório" em `README.md`**

```markdown
## Estrutura do repositório

| Caminho | O que é |
|---|---|
| `INICIO.md` | Nó central: áreas, como estudar, como usar com agente |
| `areas/` | Um hub por área de conhecimento |
| `cursos/` | Trilhas completas por área e curso |
| `biblioteca/` | Catálogo e uma nota por livro, com licença e link legal |
| `_templates/` | Modelos para criar curso, módulo, livro e anotação |
| `_meta/` | Contribuição, convenções, política de fontes, playbooks e checklist |
| `AGENTS.md` | Regras que agentes de IA seguem neste vault |
| `pessoal/` | Sua área local, fora do git |
```

- [ ] **Step 2: Percorrer `_meta/VERIFICACAO.md` inteira**

Itens 1 a 7, um por um, marcando cada checkbox. Expected: zero pendência.

- [ ] **Step 3: Conferir contagens de conteúdo**

Liste os arquivos com `git ls-files` (ou pela árvore de arquivos do editor).
Expected: 13 em `cursos/humanas/psicologia/` (hub + 12 módulos) e 11 em `biblioteca/` (catálogo + 10 livros).

Expected também: 10 ocorrências de `acesso:` nas notas de livro (uma por livro).

- [ ] **Step 4: Conferir que nada proibido entrou**

Na saída de `git ls-files`, procure por `.pdf`, `.epub`, `.mobi` e `.djvu`.
Expected: nenhum resultado.

Run: `git status --short`
Expected: apenas `README.md` modificado; nada em `pessoal/`.

- [ ] **Step 5: Abrir `INICIO.md` no Obsidian e percorrer o caminho**

Abra o vault e vá de `INICIO.md` até `biblioteca/humanas/openstax-psychology-2e` em três cliques (nó central → hub da área → hub do curso → módulo → livro). Confirme que nenhum link aparece em vermelho e que a tabela de áreas abre no celular e no desktop.

- [ ] **Step 6: Commit e push**

```bash
git add README.md
git commit -m "docs: estrutura do repositorio no README"
git push origin main
```

---

## Notas de execução

- Tasks 5–7 produzem muito texto. Cada módulo é um deliverable independente: o
  revisor pode rejeitar o módulo 9 sem bloquear os demais.
- Se uma URL da Task 4 não for confirmável, troque a obra por outra de acesso aberto
  e registre a substituição no commit; não crie nota com link não conferido.
- O conteúdo da Psicologia vem de `plano_estudos_psicologia_12_meses.md`; o executor
  transcreve os tópicos e escreve exercícios autorais sobre eles. Não copie exercício
  de livro.
- Nada de script em tarefa futura, por mais tentador que pareça com 12 módulos: a
  checklist é o contrato, e ela precisa continuar executável no macOS e no Linux.
