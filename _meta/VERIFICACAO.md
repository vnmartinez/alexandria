↑ [[_meta/COMO-CONTRIBUIR|Como contribuir]]

# Checklist de verificação

Percorra esta lista antes de cada commit. Não há script: qualquer pessoa ou agente
consegue executar as conferências no Obsidian, no GitHub ou num editor de texto, em
Windows, macOS ou Linux. "Verde" significa zero pendência.

## 1. Links internos e forma do grafo

- [ ] Liste os arquivos `.md` do vault (fora de pastas ocultas e de `pessoal/`,
      exceto `pessoal/README.md`).
- [ ] Procure todas as ocorrências de `[[` fora de código e confira se cada alvo
      existe. Em `[[caminho/arquivo|texto]]`, o alvo é o caminho, não o texto. Em
      `[[#Módulo N — Tema]]`, o alvo é um título `##` da mesma nota, escrito igual.
      Nos modelos, links de exemplo ficam entre crases e não contam.
- [ ] Confirme que nenhum nome de arquivo aparece duas vezes no vault: wikilink
      resolve por nome, e duplicata torna o destino imprevisível. Única exceção:
      `README.md` (raiz e `pessoal/`); o de `pessoal/` só é linkado pelo caminho
      completo.
- [ ] Cada wikilink segue a tabela de pai e filhos de `_meta/CONVENCOES.md`.
- [ ] Nenhuma ponta solta: toda nota listada recebe link do pai (ou, no caso do
      `README.md`, linka `INICIO`).
- [ ] Nenhum link lateral: área para área, curso para curso, curso para catálogo,
      catálogo para curso, nem atalho que pule o pai.

## 2. Links do README

- [ ] O único link relativo do `README.md` é para `INICIO.md`.
- [ ] Os demais links internos usam
      `https://github.com/vnmartinez/alexandria/blob/main/<caminho>` e o caminho
      existe no repositório.

## 3. Contrato do curso

Vale para cada nota em `cursos/<area>/<curso>.md`.

- [ ] Frontmatter com `area`, `curso`, `nivel`, `atualizado`, sem previsão de
      tempo em lugar nenhum da nota (carga, duração, semestre, mês).
- [ ] Link para a área no topo e aviso de que o percurso não equivale a graduação
      nem habilita ao exercício profissional.
- [ ] Seções de cabeçalho: Como usar, Mapa de dependências, Índice, Bibliografia
      (e Fontes, quando o curso deriva de ementas). O índice tem uma âncora por
      módulo.
- [ ] Um `## Módulo N — Tema` por módulo, em ordem. Toda dependência tem número
      menor que o módulo e bate com o mapa.
- [ ] Em cada módulo, nesta ordem: linha `**Depende de:**`, Objetivo, Tópicos,
      Leituras, Conceitos-chave (opcional), Exercícios (opcional), Resultado
      esperado, Anotações e a linha "Próximo" (exceto no último módulo).
- [ ] Pelo menos 8 tópicos no formato `- [ ] N. …`.
- [ ] Quando houver exercícios: entre 8 e 10, numerados (3 de múltipla escolha,
      3 discursivos, os demais de aplicação), com gabarito único por módulo em
      `<details>` com `<summary>Gabarito</summary>` cobrindo todos.
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
      `LICENSE`, `_meta/sobre.md`, `_meta/COMO-CONTRIBUIR.md`,
      `_meta/CONVENCOES.md`, `_meta/FONTES.md`, `_meta/VERIFICACAO.md`.
- [ ] Nenhum script, binário ou caminho absoluto de máquina no repositório.

## 7. Conferência de leitura

- [ ] Abrir `INICIO.md` no Obsidian e chegar a um módulo do curso em três cliques
      (área → curso → módulo pelo índice), sem link em vermelho.
- [ ] Abrir o catálogo a partir de `INICIO.md` em um clique.
- [ ] No grafo, com **Órfãos** ligado, nenhum nó solto e nenhum nó fantasma
      (alvo inexistente): só a árvore a partir de `INICIO`, sem ciclo.
