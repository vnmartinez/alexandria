---
area: <slug-da-area>
---

↑ `[[INICIO|Alexandria]]` ← troque pelo link sem crases

# <Nome da área>

<Uma ou duas frases: o que a área cobre e para quem estuda.>

## Cursos

| Curso | Nível | Módulos |
|---|---|---|
| `[[cursos/<area>/<curso>\|<Curso>]]` | <nível> | <n> |

Sem curso ainda: escreva "Nenhum curso publicado ainda." no lugar da tabela.

## Como adicionar um curso

1. Copie `_templates/curso.md` para `cursos/<area>/<curso>.md` — o curso inteiro
   fica nessa nota única, com um `## Módulo N — Tema` por módulo.
2. Acrescente o curso na seção acima com um link para a nota do curso.
3. Inclua as obras no catálogo (`biblioteca/catalogo.md`), na seção desta área.
4. Percorra `_meta/VERIFICACAO.md` antes do commit.

<!-- Regras: links só para INICIO (pai) e para os cursos da área (filhos).
     Nada de curso de outra área, livro ou link lateral. Os links deste modelo
     estão entre crases para não aparecerem no grafo; remova as crases ao usar. -->
