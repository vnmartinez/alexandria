↑ [[_meta/COMO-CONTRIBUIR|Como contribuir]]

# Convenções

## Formato

- Só Markdown. Nenhum script, binário, caminho absoluto de máquina nem comando
  específico de sistema operacional.
- Sem plugin da comunidade do Obsidian. `<details>` e `<summary>` são permitidos
  para recolher gabaritos.
- Português do Brasil. H1 legível, em linguagem natural (`# Psicologia`).

## Nomes

- Pastas e arquivos em `kebab-case`, ASCII, minúsculos: `artes-e-letras.md`.
- Nomes únicos no vault inteiro: wikilink resolve por nome. Exceção: `README.md`
  (raiz e `pessoal/`); o de `pessoal/` é linkado sempre pelo caminho completo.
- Cursos: `cursos/<area>/<curso>.md`. Áreas: `areas/<area>.md`.
- Áreas válidas: `humanas`, `exatas`, `natureza`, `saude`, `aplicadas`,
  `engenharias`, `artes-e-letras`.

## Grafo e links

O grafo do Obsidian é uma árvore: toda nota tem exatamente um pai, nenhuma fica
solta e não há ciclo. Só estes wikilinks existem:

| Arquivo | Pai | Filhos |
|---|---|---|
| `INICIO.md` | — | 7 áreas, catálogo, `pessoal/README`, `_meta/sobre` |
| `_meta/sobre.md` | `INICIO` | `AGENTS`, `_meta/COMO-CONTRIBUIR` |
| `areas/<area>.md` | `INICIO` | cursos da própria área |
| `cursos/<area>/<curso>.md` | sua área | âncoras internas (`[[#Mês N — Tema]]`) |
| `biblioteca/catalogo.md` | `INICIO` | — |
| `AGENTS.md` | `_meta/sobre` | `CLAUDE`, `GEMINI`, playbooks de `_meta/agentes/` |
| `_meta/agentes/*.md` | `AGENTS` | — |
| `_meta/COMO-CONTRIBUIR.md` | `_meta/sobre` | `CONVENCOES`, `FONTES`, `VERIFICACAO`, os 3 modelos |
| `_meta/{CONVENCOES,FONTES,VERIFICACAO}.md` | `COMO-CONTRIBUIR` | — |
| `pessoal/README.md` | `INICIO` | — |
| `README.md` | — | `INICIO` (link relativo) |

- Link para o pai fica na primeira linha (`↑ [[…]]`). Exceções sem linha de pai,
  ligadas só pelo link que vem do pai: modelos (o link seria copiado para a nota
  nova), adaptadores (lidos por ferramentas) e `README.md` (é a entrada do GitHub).
- Nada de link lateral (área para área, curso para curso), curso cruzado, link de
  curso para catálogo ou de catálogo para curso.
- O curso cita obras pelo título, em texto; o catálogo é aberto pelo nó central.
- Qualquer outra menção a arquivo vai entre crases. Nos modelos, links de exemplo
  também ficam entre crases, para não criar nós fantasmas no grafo.
- O `README.md` linka `INICIO.md` por caminho relativo e todo o resto por URL
  completa do GitHub (`https://github.com/vnmartinez/alexandria/blob/main/<caminho>`),
  que funciona no site e não cria aresta no grafo.
- `.github/copilot-instructions.md` fica em pasta oculta, que o Obsidian não indexa;
  não entra no grafo.
- Links externos sempre em URL completa com `https://`.

## Curso

Estrutura completa em `_templates/curso.md`. Resumo:

- Frontmatter: `area`, `curso`, `nivel`, `carga-semanal`, `duracao`, `atualizado`.
- Cabeçalho: link para a área, H1, público, aviso de não habilitação, Carga e
  ritmo, Índice, Bibliografia.
- Por mês, `## Mês N — Tema` com `### Objetivo`, `### Tópicos`, `### Leituras`,
  `### Conceitos-chave`, `### Exercícios`, `### Resultado esperado`,
  `### Anotações` e a linha "Próximo".
- Tópicos: `- [ ] N. Texto.` — no mínimo 10.
- Exercícios: de 8 a 10, numerados; 3 de múltipla escolha (alternativas em sublista
  `- a) …`), 3 discursivos e o restante de aplicação. Gabarito único por mês:

  ```html
  <details>
  <summary>Gabarito</summary>

  1. b — explicação.

  </details>
  ```

  Deixe uma linha em branco depois de `<summary>` e antes de `</details>`, ou o
  Markdown interno não é renderizado.

## Entrada do catálogo

Uma seção `## <Área>` por área e uma `### <Título>` por obra:

```markdown
### <Título>

- **Autor:** <nome> (use "Autores" ou "Organizador" quando couber)
- **Ano:** <ano ou edição> · **Idioma:** <idioma> · **Nível:** <introdutório|intermediário|avançado|referência>
- **Licença:** <CC BY 4.0 | domínio público | todos os direitos reservados | …> · **Obtenção:** <gratuito|compra|biblioteca>
- **Acesso:** <URL oficial verificada, ou instrução de compra/empréstimo sem link de cópia>
- **Verificado:** <AAAA-MM>
- **Por que ler:** <uma a três linhas>
```

## Área pessoal

- `pessoal/` não vai para o git; só `pessoal/README.md` é versionado.
- Notas do aluno: `pessoal/<area>/<curso>/mes-NN.md`, a partir de
  `_templates/anotacao.md`.
- Conteúdo versionado nunca linka para `pessoal/`; só indica o caminho em texto.
