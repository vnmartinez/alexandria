# Checklist de verificação

Percorra esta lista antes de cada commit. Não há script: qualquer pessoa ou agente
consegue executar as conferências no Obsidian, no GitHub ou num editor de texto, em
Windows, macOS ou Linux. "Verde" significa zero pendência.

## 1. Links internos e forma do grafo

- [ ] Liste os arquivos `.md` do vault, fora de `_templates/` e `docs/`.
- [ ] Procure todas as ocorrências de `[[` e confira se cada alvo existe.
      Em `[[caminho/arquivo|texto]]`, o alvo é o caminho, não o texto. Em
      `[[#Mês N — Tema]]`, o alvo é um título `##` da mesma nota, escrito igual.
- [ ] Confirme que nenhum nome de arquivo aparece duas vezes no vault: wikilink
      resolve por nome, e duplicata torna o destino imprevisível. Única exceção:
      `README.md` (raiz e `pessoal/`), que nunca é alvo de wikilink.
- [ ] Wikilink só existe em `INICIO.md`, `areas/`, `cursos/` e `biblioteca/`, e
      só nestas direções: `INICIO` → áreas e catálogo; área → `INICIO` e cursos da
      área; curso → sua área e âncoras da própria nota; catálogo → `INICIO`.
- [ ] Nenhum link lateral: área para área, curso para curso, curso para catálogo,
      catálogo para curso.
- [ ] `_meta/`, `_templates/`, `AGENTS.md`, adaptadores e `README.md` citam caminhos
      entre crases, sem `[[` fora de código.

## 2. Links do README

- [ ] Todo link interno do `README.md` usa
      `https://github.com/vnmartinez/alexandria/blob/main/<caminho>` e o caminho
      existe no repositório. Nenhum link relativo (`](arquivo.md)`).

## 3. Contrato do curso

Vale para cada nota em `cursos/<area>/<curso>.md`.

- [ ] Frontmatter com `area`, `curso`, `nivel`, `carga-semanal`, `duracao`,
      `atualizado`.
- [ ] Link para a área no topo e aviso de que o percurso não equivale a graduação
      nem habilita ao exercício profissional.
- [ ] Seções de cabeçalho: Carga e ritmo, Índice, Bibliografia. O índice tem uma
      âncora por mês.
- [ ] Um `## Mês N — Tema` por mês, em ordem (12 no curso de Psicologia).
- [ ] Em cada mês, nesta ordem: Objetivo, Tópicos, Leituras, Conceitos-chave,
      Exercícios, Resultado esperado, Anotações, e a linha "Próximo" (exceto no
      último mês).
- [ ] Pelo menos 10 tópicos no formato `- [ ] N. …`.
- [ ] Entre 8 e 10 exercícios numerados: 3 de múltipla escolha, 3 discursivos e
      os demais de aplicação.
- [ ] Gabarito único por mês em `<details>` com `<summary>Gabarito</summary>`,
      cobrindo todos os exercícios.
- [ ] Anotações apontam para `pessoal/`.
- [ ] Toda obra citada em Leituras existe no catálogo, com o mesmo título.
- [ ] Seção `## Conclusão` no fim.

## 4. Contrato do catálogo

Vale para `biblioteca/catalogo.md`.

- [ ] Uma seção `## <Área>` por área com obras e uma `### <Título>` por obra.
- [ ] Cada obra tem autor, ano, idioma, nível, licença, obtenção
      (`gratuito`, `compra` ou `biblioteca`), acesso, verificado (`AAAA-MM`) e
      "Por que ler".
- [ ] Obra `gratuito` tem link que abre em página oficial do titular, repositório
      institucional ou acervo de domínio público. Obra `compra` ou `biblioteca` não
      tem link de cópia.
- [ ] Nenhum link para curso ou módulo.

## 5. Áreas e nó central

- [ ] `INICIO.md` lista as 7 áreas e o catálogo.
- [ ] Cada arquivo em `areas/` tem `area:` no frontmatter, link para `INICIO` e
      lista só os cursos da própria área.

## 6. Higiene do repositório

- [ ] Nenhum `.pdf`, `.epub`, `.mobi` ou `.djvu` versionado.
- [ ] `pessoal/` fora do git, exceto `pessoal/README.md`.
- [ ] Arquivos obrigatórios presentes: `README.md`, `INICIO.md`, `AGENTS.md`,
      `LICENSE`, `_meta/COMO-CONTRIBUIR.md`, `_meta/CONVENCOES.md`,
      `_meta/FONTES.md`.
- [ ] Nenhum script, binário ou caminho absoluto de máquina no repositório.

## 7. Conferência de leitura

- [ ] Abrir `INICIO.md` no Obsidian e chegar a um mês do curso em três cliques
      (área → curso → mês pelo índice), sem link em vermelho.
- [ ] Abrir o catálogo a partir de `INICIO.md` em um clique.
- [ ] No grafo, com **Órfãos** desligado, ver só a árvore: `INICIO`, 7 áreas,
      cursos e catálogo, sem ciclo.
