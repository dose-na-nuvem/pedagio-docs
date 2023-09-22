# Padrão de Commits 

O conventional commits é uma metodologia para auxiliar na estruturar de mensagens dos commits, e também manter o histórico de mudanças organizado e legível para outras pessoas do projeto.

## O problema de commits sem padrão:

- Ilegibilidade(ex: "agora vai", “novas mudancas” “add readme”).

- Problema para novos membros do time, Commits sem sentido podem complicar o processo de integração de novos membros à equipe, já que não oferecem uma visão clara do progresso do projeto.

- Cliente. Quando o cliente deseja acompanhar o andamento do projeto e se depara com commits confusos ou sem contexto, isso pode gerar confusão e incerteza sobre o progresso e a qualidade do trabalho realizado.

## Estrutura do commit


```shell
<type>[scope]: <assunto>

feat[módulo-front]: adiciona nova rota cadastrar usuário
```

Elementos entre <> é obrigatório, e entre [] são elementos opcionais.

- type: é o tipo do commit, ou seja, aqui a gente indica qual é o tipo da mudança `feat`.

- scope: contexto da mudança, como: nova feature dentro do contexto frontend. O que é ótimo para repositórios monorepo onde há muitas alterações e também sinaliza se é front ou back por exemplo.

- description: Breve descrição da alteração que está sendo feita, é sempre bom indicar a ação da mudança, exemplo: `adiciona nova rota cadastrar usuário.`


## Type: Quais são os timpos de commit

O conventional commits possui algumas flags para sinalizar os tipos das mudanças:

- `feat`: sinaliza o desenvolvimento de uma nova feature, como: a criação de um novo serviço, funcionalidade, regra de negócio, etc…

- `test`: sinaliza quando é criado cenários de testes, como: testes unitários ou integração.

- `refactor`: sinaliza refatoração de código.

- `perf`: sinaliza alterações que afetam a performance da aplicação, como: redução de ifs, melhorar query do banco, etc...

- `ci`: sinaliza alterações de arquivos de configuração do CI/CD, como: Github actions, Gitlab-ci, Circle, Travis, etc…

- `docs`: sinaliza mudanças na documentação do projeto, tipo README.md, swagger... Ex: documentação referente a deploy de ambiente, infos sobre dependências externas, etc…

- `revert`: sinaliza reversão para um commit anterior.

- `style`: sinaliza mudança de estilização de código, como: convenção de lint, indentação, espaço em brancos, remoção de comentários e consoles.log, mudanças de aspas duplas para simples, etc…

- `fix`: sinaliza correções de erros/bugs.

- `chore`: sinaliza mudanças que não afetam o código fonte da aplicação ou arquivos de testes, como: regras de lint, extensões de arquivo ao .gitignore, adição de dependências dev.

## Referências:

- [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0-beta.4/)
- [Commitlint](https://commitlint.js.org/#/)