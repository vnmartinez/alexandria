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
