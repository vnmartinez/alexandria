# Alexandria

Vault público de trilhas de estudo por área de conhecimento. Escolha uma área,
entre em um curso e siga os meses na ordem. Tudo aqui é gratuito para ler,
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

## Catálogo de livros

[[biblioteca/catalogo|Catálogo]] — metadados, licença e link de acesso de cada
obra, com a indicação do que é gratuito e do que é comprado ou emprestado.

## Como estudar

1. Clone o repositório e abra a pasta como vault no Obsidian (sem plugin nenhum,
   em Windows, macOS ou Linux).
2. Cada curso é uma nota única: o topo traz o plano e a bibliografia, e cada mês
   é uma seção `## Mês N — Tema`. Use o índice do curso para pular de mês.
3. Copie `_templates/anotacao.md` para `pessoal/<area>/<curso>/` e registre ali o
   seu progresso — essa pasta não vai para o git e não gera conflito no `git pull`.
4. Faça os exercícios do mês antes de abrir o gabarito.
5. Ao fim do mês, confira o "Resultado esperado": se não conseguir explicar,
   refaça as leituras indicadas.

## Como estudar com um agente de IA

Abra esta pasta no Claude Code, Codex, OpenCode, Gemini CLI ou Copilot. O agente lê
`AGENTS.md` e assume o papel de tutor: explica, pergunta, corrige exercício e monta
plano de estudo. Nenhuma configuração extra é necessária.

- Regras que o agente segue: `AGENTS.md`
- Playbooks: `_meta/agentes/tutor.md`, `_meta/agentes/avaliador.md`, `_meta/agentes/plano.md`

## Grafo

A navegação é uma árvore: este nó → áreas → cursos, mais o catálogo. Para ver só a
árvore no grafo do Obsidian, desligue **Órfãos** nos filtros; os arquivos de apoio
(`_meta/`, `_templates/`, `AGENTS.md`) não têm links e somem da vista.

## Aviso

Este vault é material de estudo autodidata. Não é graduação, não inclui prática
supervisionada e não habilita ao exercício profissional de nenhuma área. Nenhum
conteúdo aqui serve para diagnóstico ou tratamento.

Política de links e licenças: `_meta/FONTES.md`. Nenhum arquivo de livro é
hospedado neste repositório.

## Contribuir

Leia `_meta/COMO-CONTRIBUIR.md`, as convenções em `_meta/CONVENCOES.md` e a
checklist em `_meta/VERIFICACAO.md`.
