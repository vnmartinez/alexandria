# Convenções

## Formato

- Só Markdown. Nenhum script, binário, caminho absoluto de máquina nem comando
  específico de sistema operacional.
- Sem plugin da comunidade do Obsidian. `<details>` e `<summary>` são permitidos
  para recolher gabaritos.
- Português do Brasil. H1 legível, em linguagem natural (`# Psicologia`).

## Nomes

- Pastas e arquivos em `kebab-case`, ASCII, minúsculos: `artes-e-letras.md`.
- Nomes únicos no vault inteiro: wikilink resolve por nome.
- Cursos: `cursos/<area>/<curso>.md`. Áreas: `areas/<area>.md`.
- Áreas válidas: `humanas`, `exatas`, `natureza`, `saude`, `aplicadas`,
  `engenharias`, `artes-e-letras`.

## Grafo e links

O grafo do Obsidian é uma árvore. Só estes wikilinks existem:

| Arquivo | Pode linkar para |
|---|---|
| `INICIO.md` | as 7 áreas e o catálogo |
| `areas/<area>.md` | `INICIO` e os cursos da própria área |
| `cursos/<area>/<curso>.md` | a própria área e âncoras internas (`[[#Mês N — Tema]]`) |
| `biblioteca/catalogo.md` | `INICIO` |

- Nada de link lateral (área para área, curso para curso), curso cruzado, link de
  curso para catálogo ou de catálogo para curso.
- O curso cita obras pelo título, em texto; o catálogo é aberto pelo nó central.
- `_meta/`, `_templates/`, `AGENTS.md`, adaptadores e `README.md` citam caminhos
  entre crases. Nos modelos, links de exemplo ficam entre crases para não criar nós
  fantasmas no grafo.
- O `README.md` linka por URL completa do GitHub
  (`https://github.com/vnmartinez/alexandria/blob/main/<caminho>`), que funciona no
  site e não cria aresta no grafo.
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
