# Plano — Alexandria v1 (revisão 2)

Spec: `docs/superpowers/specs/2026-10-27-alexandria-vault-design.md` (revisão 2).
Sem script: cada tarefa termina conferindo os itens indicados de
`_meta/VERIFICACAO.md` e com um commit em português.

Já feito antes desta revisão: fundação (`.gitignore`, `LICENSE`, `pessoal/README.md`),
`INICIO.md`, `README.md`, 7 hubs de área e templates no desenho antigo.

## Tarefa 1 — Spec e plano

- Reescrever spec e plano para o desenho de nota única e grafo em árvore.
- Commit: `docs: spec e plano no desenho de nota unica`.

## Tarefa 2 — Navegação e contratos

- `INICIO.md`: textos de "Como estudar" para curso em nota única; links só para
  áreas e catálogo; caminhos de `_meta` entre crases; dica do filtro "Órfãos".
- `README.md`: navegação por URL absoluta do GitHub.
- `areas/*`: link para `INICIO` (pai); `humanas` aponta `cursos/humanas/psicologia`;
  remover "Cursos cruzados" de `saude`; instruções de novo curso em nota única.
- `_templates/`: `area.md`, `curso.md` (nota única com bloco de mês) e
  `anotacao.md`, sem wikilink; remover `modulo.md` e `livro.md`.
- `_meta/VERIFICACAO.md`: itens 3–5 para curso e catálogo em nota única; item 2
  para URLs do README; item 7 para o caminho de cliques novo.
- Commit: `refactor: navegacao por hub e contratos de nota unica`.

## Tarefa 3 — Catálogo

- `biblioteca/catalogo.md` com ~10 obras de acesso legal, URLs conferidas em 2026-10.
- Verificação: item 4.
- Commit: `feat: catalogo de obras de psicologia com acesso legal`.

## Tarefa 4 — Curso de Psicologia

- `cursos/humanas/psicologia.md`: cabeçalho, bibliografia por mês, 12 seções de mês
  com 8–10 exercícios e gabarito recolhido, conclusão.
- Verificação: itens 1, 3 e 5.
- Commit: `feat: curso de psicologia em 12 meses (nota unica)`.

## Tarefa 5 — Camada de agentes

- `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md`,
  `_meta/agentes/{tutor,avaliador,plano}.md`.
- Commit: `feat: camada de agentes tutores`.

## Tarefa 6 — Documentos de `_meta`

- `COMO-CONTRIBUIR.md`, `CONVENCOES.md`, `FONTES.md`.
- Commit: `docs: guias de contribuicao, convencoes e fontes`.

## Tarefa 7 — Verificação final e publicação

- Percorrer `_meta/VERIFICACAO.md` inteira; corrigir pendências em commit próprio.
- `git push origin main`.

## Tarefa 8 — Segundo Cérebro

- Atualizar o hub `Projetos/Pessoais/alexandria/alexandria.md` (`commit_base`,
  contexto rápido, mapa do código) e rodar o `vault-sync push`.
