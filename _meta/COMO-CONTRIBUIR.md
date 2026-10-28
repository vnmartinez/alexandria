# Como contribuir

Correções, novas obras no catálogo e cursos de outras áreas são bem-vindos. O
repositório é só Markdown: dá para contribuir pelo próprio GitHub, sem instalar
nada.

## Antes de começar

- Leia `_meta/CONVENCOES.md` (nomes, formato e regras de link) e `_meta/FONTES.md`
  (o que pode entrar no catálogo).
- Não edite sua cópia de `cursos/` para estudar: anotações vão em `pessoal/`.

## Tipos de contribuição

### Corrigir um erro

Erro de conteúdo, gabarito errado, link quebrado: abra uma *issue* descrevendo o
problema (arquivo, mês, exercício) ou envie um *pull request* com a correção e a
fonte que a sustenta.

### Adicionar uma obra ao catálogo

1. Confirme que a obra tem acesso legal (veja `_meta/FONTES.md`).
2. Abra o link você mesmo e anote o mês em `verificado`.
3. Acrescente uma seção `### <Título>` na área certa de `biblioteca/catalogo.md`,
   com todos os campos do formato em `_meta/CONVENCOES.md`.
4. Não crie link do catálogo para cursos.

### Criar um curso

1. Copie `_templates/curso.md` para `cursos/<area>/<curso>.md`.
2. Preencha cabeçalho, bibliografia e um bloco `## Mês N — Tema` por mês, com 10 ou
   mais tópicos e de 8 a 10 exercícios com gabarito recolhido.
3. Cite só obras do catálogo; inclua as que faltarem no mesmo *pull request*.
4. Acrescente o curso na seção "Cursos" de `areas/<area>.md`.
5. Se a área estava vazia, atualize a tabela de áreas do `README.md`.

### Criar uma área nova

As 7 áreas cobrem o conhecimento acadêmico de forma ampla. Antes de propor uma
oitava, abra uma *issue* para discutir.

## Checklist obrigatória

Antes de abrir o *pull request*, percorra `_meta/VERIFICACAO.md` e diga na
descrição que todos os itens estão verdes. Um agente de IA pode fazer essa
conferência por você: peça que siga a checklist e relate o resultado.

## Licença das contribuições

Ao contribuir, você concorda em licenciar seu texto sob CC BY-SA 4.0, a mesma
licença do repositório (arquivo `LICENSE`).
