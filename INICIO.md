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
| [[areas/engenharias\|Engenharias e Tecnologia]] | Projeto e operação de sistemas — **4 cursos** |
| [[areas/artes-e-letras\|Artes e Letras]] | Línguas, literatura, artes, música |

## Catálogo de livros

[[biblioteca/catalogo|Catálogo]] — metadados, licença e link de acesso de cada
obra, com a indicação do que é gratuito e do que é comprado ou emprestado.

## Como estudar

1. Clone o repositório e abra a pasta como vault no Obsidian (sem plugin nenhum,
   em Windows, macOS ou Linux).
2. Cada curso é uma nota única: o topo traz o mapa de dependências e a bibliografia,
   e cada módulo é uma seção `## Módulo N — Tema`. Não há prazo: o ritmo é seu, e
   cada módulo diz de quais outros depende.
3. Registre o seu progresso em `pessoal/<area>/<curso>/`, usando o modelo de
   anotação — essa pasta não vai para o git e não gera conflito no `git pull`.
   Veja [[pessoal/README|Sua área pessoal]].
4. Faça os exercícios do módulo antes de abrir o gabarito.
5. Ao fim do módulo, confira o "Resultado esperado": se não conseguir explicar,
   refaça as leituras indicadas.

## Como estudar com um agente de IA

Abra esta pasta no Claude Code, Codex, OpenCode, Gemini CLI ou Copilot. O agente lê
as regras e assume o papel de tutor: explica, pergunta, corrige exercício e monta
plano de estudo. Nenhuma configuração extra é necessária.

Regras, limites e playbooks dos agentes estão em [[_meta/sobre|Sobre o vault]],
junto com o guia de contribuição.

## Grafo

A navegação é uma árvore, sem pontas soltas nem ciclos. Este nó tem quatro ramos:
áreas (com os cursos), catálogo, área pessoal e "Sobre o vault" (agentes e
contribuição). Cada nota liga só ao pai e aos filhos.

## Aviso

Este vault é material de estudo autodidata. Não é graduação, não inclui prática
supervisionada e não habilita ao exercício profissional de nenhuma área. Nenhum
conteúdo aqui serve para diagnóstico ou tratamento.

Política de links e licenças: `_meta/FONTES.md`. Nenhum arquivo de livro é
hospedado neste repositório.

## Contribuir

Correções e cursos novos são bem-vindos: veja "Sobre o vault", acima.
