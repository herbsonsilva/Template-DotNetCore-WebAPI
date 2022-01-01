<img alt="GoStack" src="https://images.unsplash.com/photo-1610547189313-1fbea2dcd059?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&h=300&q=80" />

<h2 align="center">
  Estrutura inicial para projetos Web API com .NET Core
</h2>

*<blockquote align="center">“Motivação é o que te faz começar, hábito é o que te faz continuar!"</blockquote>*

<br>

<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/herbsonsilva/estrutura-projeto-nodejs?color=blueviolet">

  <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/herbsonsilva/estrutura-projeto-nodejs?color=blueviolet">

  <img alt="Repository size" src="https://img.shields.io/github/repo-size/herbsonsilva/estrutura-projeto-nodejs?color=blueviolet">

  <a href="https://github.com/herbsonsilva/estrutura-projeto-nodejs/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/herbsonsilva/estrutura-projeto-nodejs?color=blueviolet">
  </a>

  <a href="https://github.com/herbsonsilva/estrutura-projeto-nodejs/blob/master/LICENSE">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-blueviolet">
  </a>

  <a href="https://github.com/herbsonsilva/estrutura-projeto-nodejs/stargazers">
    <img alt="Stargazers" src="https://img.shields.io/github/stars/herbsonsilva/estrutura-projeto-nodejs?style=social">
  </a>
</p>

<p align="center">
  <a href="#rocket-sobre">Sobre</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#shrug-como-utilizar">Como utilizar</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#books-dependências">Bibliotecas</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#wrench-ferramentas">Ferramentas</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#computer-comandos-utilizados">Camadas do Projeto</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#scroll-licença">Licença</a>
</p>

## :rocket: Sobre

Repositório contendo toda configuração inicial necessária para começar a desenvolver um projeto Web API com .NET Core utilizando os princípios de Arquitetura em Camadas, TDD, DDD, Clean Code e SOLID.

Desenvolvido conforme conhecimento adquirido nas aulas do GoStack Bootcamp da Rocketseat.

A idéia aqui é não ter que precisar configurar um novo projeto .NET Core do zero, evitando a instalação de bibliotecas e as configurações necessárias para iniciar o desenvolvimento e testes da aplicação.

Logo abaixo você encontrará a relação das bibliotecas e ferramentas utilizadas neste projeto.

## :shrug: Como utilizar

Faça o download do arquivo .zip e descompacte-o em um local de sua preferência ou clone o repositório.

## :books: Bibliotecas

Nome | Ambiente | Descrição
:---: | :---: | ---
**`xUnit`** | Teste | Framework para Desenvolvimento de Testes.
**`Moq`** | Teste | Framework para Mocking (imitação de objetos reais da aplicação).


## :computer: Estrutura do Projeto

Camada | Descrição | Pasta | Projeto | Descrição
--- | --- | --- | --- | ---
**`Tests`** | Camada que surportará os Testes do Projeto. | **`0 - Tests`** | **`Template.Application.Tests`** | Contém a Biblioteca de Classes para realização dos `Testes de Unidade`.
**` `** | **` `** | **`./Services`** | Pasta que contém os testes de unidade dos `Services` do projeto `Template.Application`.
**`Web/Host`** | Camada que surportará o Front-end/API Controllers, Conexões e Configurações. | **`1 - Web`** |  **`Template.WebAPI`** | Contém o projeto `Web API .NET Core`.
**`Application`** | Camada que suportará as Interfaces de Serviços, Serviços e as ViewModels. Ela será responsável por gerenciar as informações e conterá toda a Regra de Negócio.| **`2 - Application`** | **`Template.Application`** | Contém a Biblioteca de Classes que proverá os serviços da aplicação.
**`Domain`** | Camada que suportará as Interfaces de Repositórios, as Entidades de Domínio e os Models. | **`3 - Domain`** | **`Template.Domain`** | Contém a Biblioteca de Classes que proverá as entidades.
**`Infrastructure`** | Camada que suportará o Projeto de Dados, Contexto e Classes de Repositórios, Classes de Mapeamentos de Objetos e Projetos Extras (Autorizações, Logs, Notificações) | **`4 - Infrastructure`** | **` `** | Inicia o `controle de versão` do Git no projeto.
**` `** | | **`4.1 - Data`** | **`Template.Data`** | Inicia o `controle de versão` do Git no projeto.
**` `** | | **`4.2 - CrossCutting`** | **` `** | Inicia o `controle de versão` do Git no projeto.


## Template.WebAPI

Pastas | Descrição
--- | ---
**`Controllers`** | Contém as `Rotas da Aplicação` (Endpoints) que receberão as requisições do Front-end, chamarão as `Interfaces das classes de Serviço` na camada `Application` e retornarão as respostas ao Front-end.

## Template.Application

Pastas | Descrição
--- | ---
**`IServices`** | Contém as `Interfaces das classes de Serviço` que serão chamadas através dos `Controllers` na camada `Web/Host`.
**`Services`** | Contém as `classes de Serviço` da aplicação que chamam as `Interfaces das classes de Repositório` na camada de `Domain`.
**`ViewModels`** | Contém o `modelo dos objetos` que virão ou retornarão para o Front-end através dos `Controllers` na camada `Web/Host`.

## Template.Domain

Pastas | Descrição
--- | ---
**`IRepositories`** | Contém as `Interfaces das classes de Repositório` que serão chamadas através das `classes de Serviço` na camada `Application`.
**`Entities`** | Contém o modelo dos objetos que serão salvos/persistidos no Banco de Dados.
**`Models`** | Contém o `modelo dos objetos em comum` que poderão ser compartilhados ou herdados pelas entidades para que não seja necessário ficar replicando código.

## Template.Infrastructure

Pastas | Sub-Pastas | Descrição
--- | --- | ---
**`Data`** | **` `** | Contém a Biblioteca de Classes que conterá as classes de Repositório, DbContext, Mapeamento de Classes.
**` `** | **`Context`** | Contém a `classe de Contexto` contendo todas as `Entidades de Domínio` refletidas e contidas no `Banco de Dados`.
**` `** | **`Mappings`** | Contém as `classes de mapeamento de objetos` para converter os `ViewModels em Entities` e `vice-versa`.
**` `** | **`Repositories`** | Contém as `classes de Repositório` que serão chamadas através das `Interfaces das classes de Repositório` na camada de `Domain` para executar os comandos e consultas no Banco de Dados.
**`CrossCutting`** | | Contém as Bibliotecas de Classes complementares que serão compartilhadas por toda aplicação como por exemplo: Bibliotecas para Gerenciar Autenticação, Logs, Notificações, etc.

<br/>
<br/>
<br/>
<br/>
<br/>

## Template.Application.Tests

Pastas | Descrição
--- | ---
**`Services`** | Contém as `classes de Testes dos Serviços` da aplicação que chamam as `Interfaces das classes de Serviço` na camada `Application` e as `Interfaces das classes de Repositório` na camada de `Domain`.


## :wrench: Fluxo de Desenvolvimento

> Entity > InterfaceReposity > FakeRepository > Test

> Routes > Controllers > Repository > Provider > Test

## :scroll: LICENÇA

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](../master/LICENSE) para mais detalhes.

---

Feito com ♥ by [Herbson Silva](https://www.linkedin.com/in/herbsonsilva/) :wave::wave::wave:

<br/>
<br/>
<br/>
<br/>
<br/>

# **`Análise de Requisitos`**

## <a href="#book-usuários" style="color:white">Usuários</a>

- <a href="#computer-tela-de-cadastro-de-usuário">Criar</a> 🟠
- <a href="#computer-tela-de-inserção-do-código-de-ativação">Inserir código de ativação</a> 🔴
- <a href="#computer-tela-de-login">Realizar Login</a> 🔴
- <a href="#computer-logout">Realizar Logout</a> 🔴
- <a href="#computer-tela-de-recuperação-de-senha">Recuperar senha</a> 🔴
- <a href="#computer-tela-de-atualização-da-senha-do-usuário">Atualizar senha</a> 🔴
- <a href="#computer-tela-de-atualização-do-perfil">Atualizar perfil</a> 🔴
- <a href="#clipboard-caso-de-uso-excluir-conta-de-usuário">Excluir conta de usuário</a> 🔴

## <a href="#utils" style="color:white">Utils</a>

- <a href="#computer-tela-de-dashboard">Dashboard</a> 🔴
- <a href="#computer-menu-de-opções">Menu de opções</a> 🔴
- <a href="#clipboard-caso-de-uso-gerar-código-de-ativação">Gerar código de ativação</a> 🔴
- <a href="#clipboard-caso-de-uso-comparar-código-de-ativação">Comparar código de ativação</a> 🔴
- <a href="#clipboard-caso-de-uso-enviar-email">Enviar email</a> 🔴
- <a href="#clipboard-caso-de-uso-garbage-collector">Garbage collector</a> 🔴

<br/>
<br/>
<br/>
<br/>
<br/>


# :book: Usuários

<p align="right">
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  - <a href="#computer-tela-de-cadastro-de-usuário">Criar</a>
  - <a href="#computer-tela-de-inserção-do-código-de-ativação">Inserir código de ativação</a>
  - <a href="#computer-tela-de-login">Realizar Login</a>
  - <a href="#computer-logout">Realizar Logout</a>
  - <a href="#computer-tela-de-recuperação-de-senha">Recuperar senha</a>
  - <a href="#computer-tela-de-atualização-da-senha-do-usuário">Atualizar senha</a>
  - <a href="#computer-tela-de-atualização-do-perfil">Atualizar perfil</a>
  - <a href="#clipboard-caso-de-uso-excluir-conta-de-usuário">Excluir conta de usuário</a>

<br/>

  Table name | Column | Type | Params
  :---: | :---: | :---: | :---:
  users | . | . | .
  . |**`id`** | uuid | primary key, default: 'uuid_generate_v4()'
  . |**`name`** | varchar | not null
  . |**`email`** | varchar | not null
  . |**`password`** | varchar | not null
  . |**`avatar`** | varchar | null
  . |**`enabled`** | boolean | default: false
  . |**`created_at`** | timestamp | default: 'now()'
  . |**`updated_at`** | timestamp | default: 'now()'

<br/>

## :computer: **Tela de `Cadastro de Usuário`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  ### 👨‍💼 **RF** (Usabilidade)
  1. O usuário deve ser capaz de se cadastrar no sistema utilizando um nome, um email válido e uma senha; 🟢
  2. O usuário deve ser capaz de receber um email (para confirmar sua propriedade) com um link com um token de ativação; <a href="#clipboard-caso-de-uso-enviar-email">**📋 Enviar  email**</a> 🟢
  ### 🧑‍💻 **RNF** (Funcionalidades técnicas)
  - Localizar usuário pelo email informado;
  - Utilizar o `BCryptJS` para criptografar a senha;
  - Utilizar o `Ethereal` para testar envios de emails em ambiente de desenvolvimento;
  - Utilizar o `Amazon SES` para envios de emails em ambiente de produção;
  - O envio de emails deve acontecer em segundo plano (background job);
  - Utilizar o `Disco Local` para testar envios de imagens em ambiente de desenvolvimento;
  - Utilizar o `Amazon S3` para envios de imagens em ambiente de produção;
  ### 📐 **RN** (Regras de negócio)
  1. Não deve ser capaz criar um usuário com um email inválido;
  1. Não deve ser capaz de criar um usuário com um e-mail já existente; 🟢
  1. O usuário deve digitar duas vezes a senha a ser cadastrada;
  1. Não deve ser capaz criar um usuário se as senhas informadas estiverem diferentes;
  2. Deve ser enviado um link com um token de ativação para o email cadastrado;
  2. O token de ativação enviado por email deve expirar em 5 minutos;
  2. Se o token estiver expirado, o usuário poderá solicitar o envio de um novo token de ativação;
  2. Caso o usuário não ative sua conta em até 7 dias, o **coletor de contas inativas** excluirá o usuário e o processo de cadastro deverá ser realizado do início; <a href="#clipboard-caso-de-uso-garbage-collector">**📋 Garbage collector**</a>

<br/>

  ### :clipboard: **Caso de Uso: `Criar Usuário`**

<p align="right">

</p>

<p align="right">
  <a href="#computer-tela-de-cadastro-de-usuário">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Criar Usuário`**
  :--- | :---
  **Request http:** | **`POST`**
  **Service:** | **`CreateUser`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas ao realizar o cadastro de um usuário no sistema.
  &nbsp; | Tem como objetivo permitir a criação de um usuário para utilização do sistema.
  `Pré-condições:` | Não existir um usuário cadastrado com o mesmo email.
  `Pós-condições:` | Informar o código de ativação.
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no botão **Cadastre-se**. | &nbsp;
  &nbsp; | `2:` Carregar tela de cadastro de usuário. *`this`*
  `3:` Informar nome, email, senha e senha de confirmação. | &nbsp;
  `4:` Clicar no botão **Enviar**. | &nbsp;
  &nbsp; | `5:` Verificar se o email informado atende aos padrões de um email válido.
  &nbsp; | `6:` Localizar usuário pelo email informado.
  &nbsp; | `7:` Se o usuário existir, verificar se está ativo.
  &nbsp; | `8:` Comparar as duas senhas informadas.
  &nbsp; | `9:` <a href="#clipboard-caso-de-uso-gerar-código-de-ativação">**📋 Gerar código de ativação**</a>.
  &nbsp; | `10:` **Criar usuário.**
  &nbsp; | `11:` <a href="#clipboard-caso-de-uso-enviar-email">**📋 Enviar  email**</a> com código de ativação.
  &nbsp; | `12:` Carregar <a href="#computer-tela-de-inserção-do-código-de-ativação">**`💻 tela de inserção do código de ativação`**</a>.
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Email inválido`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Email inválido.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário existe e está ativo`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário já cadastrado.
  &nbsp; | `1:` Exibir link para <a href="#computer-tela-de-recuperação-de-senha">**`💻 tela de recuperação de senha`**</a>.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário existe e está inativo`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário já cadastrado mas ainda não foi ativado.
  &nbsp; | `2:` Exibir link para <a href="#computer-tela-de-inserção-do-código-de-ativação">**`💻 tela de inserção do código de ativação`**</a>.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Senhas divergentes`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Senhas divergentes.
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **Tela de `Inserção do Código de Ativação`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

### 👨‍💼 **RF** (Usabilidade)

1. O usuário deve ser capaz de inserir o código de ativação enviado por email;
2. O usuário deve ser capaz de solicitar o reenvio do código de ativação;

### 🧑‍💻 **RNF** (Funcionalidades técnicas)

-

### 📐 **RN** (Regras de negócio)

1. O sistema deve exibir um texto informando ao usuário que foi enviado um código de ativação para o email cadastrado.
1. O usuário precisa digitar corretamente o código de ativação enviado por email;

<br/>

### :clipboard: **Caso de Uso: `Ativar Usuário`**

<p align="right">
  <a href="#computer-tela-de-inserção-do-código-de-ativação">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Ativar Usuário`**
  :--- | :---
  **Request http:** | **`PUT`**
  **Service:** | **`ActivateUser`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para ativar um usuário.
  &nbsp; | Tem como objetivo confirmar a autenticidade do email cadastrado.
  `Pré-condições:` | O usuário precisa estar cadastrado ou ter solicitado o envio do código de ativação.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **link de ativação** enviado por email. | &nbsp;
  &nbsp; | `2:` Carregar tela de inserção do código de ativação. *`this`*
  &nbsp; | `3:` Localizar usuário pelo email constante no link.
  &nbsp; | `3:` Verificar se usuário está ativo.
  &nbsp; | `4:` Exibir campos para inserção do código de ativação.
  `6:` Informar o código de ativação. | &nbsp;
  `7:` Clicar no botão **Enviar**. | &nbsp;
  &nbsp; | `8:` <a href="#clipboard-caso-de-uso-comparar-código-de-ativação">**📋 Comparar o código informado com o código de ativação cadastrado**</a>.
  &nbsp; | `9:` **Ativar usuário.**
  &nbsp; | `10:` Retornar mensagem: Cadastro concluído com sucesso.
  &nbsp; | `11:` Carregar <a href="#computer-tela-de-login">**`💻 tela de login`**</a>.
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | `2:` Carregar a <a href="#computer-tela-de-cadastro-de-usuário">**`💻 tela de cadastro de usuário`**</a>.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário ativo`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário ativo.
  &nbsp; | `2:` Carregar <a href="#computer-tela-de-login">**`💻 tela de login`**</a>.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Código inválido`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Código inválido.
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **Tela de `Login`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  ### 👨‍💼 **RF** (Usabilidade)
  1. O usuário deve ser capaz de entrar no sistema através de email e senha; 🟢
  2. O usuário deve ser capaz de solicitar a recuperação da senha; &nbsp; <a href="#computer-tela-de-recuperação-de-senha">**`💻 tela de recuperação de senha`**</a>
  ### 🧑‍💻 **RNF** (Funcionalidades técnicas)
  - O usuário será localizado através do email;
  - Para autenticação, será utilizada a biblioteca `Json Web Token (JWT)`;
  ### 📐 **RN** (Regras de negócio)
  1. Não deve ser capaz entrar no sistema com um email inválido; 🟢
  1. Não deve ser capaz entrar no sistema com uma senha inválida; 🟢

<br/>

  ### :clipboard: **Caso de Uso: `Realizar Login`**

<p align="right">
  <a href="#computer-tela-de-login">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Realizar Login`**
  :--- | :---
  **Request http:** | **`POST`**
  **Service:** | **`AuthenticateUser`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas ao realizar login no sistema.
  &nbsp; | Tem como objetivo confirmar a autenticidade do usuário.
  &nbsp; | A autenticação é a base da segurança em um sistema.
  &nbsp; | Autenticar é garantir que uma entidade é quem diz ser.
  `Pré-condições:` | O usuário precisa estar ativo no sistema.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no botão **Login**. | &nbsp;
  &nbsp; | `2:` Carregar tela de login. *`this`*
  `3:` Informar email e senha cadastrados. | &nbsp;
  `4:` Clicar no botão **Entrar**. | &nbsp;
  &nbsp; | `5:` Localizar usuário pelo email informado.
  &nbsp; | `6:` Validar senha.
  &nbsp; | `5:` Verificar se o usuário está ativo.
  &nbsp; | `7:` **Gerar token de autenticação.**
  &nbsp; | `8:` Retornar usuário e token.
  &nbsp; | `9:` Carregar <a href="#computer-tela-de-dashboard">**`💻 página principal`**</a>.
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Email inválido`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Credenciais inválidas.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Senha inválida`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Credenciais inválidas.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário inativo`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário inativo.
  &nbsp; | `2:` Exibir link para <a href="#computer-tela-de-inserção-do-código-de-ativação">**`💻 tela de inserção do código de ativação`**</a>.
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **`Logout`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  ### 👨‍💼 **RF** (Usabilidade)
  1. O usuário deve ser capaz de sair do sistema;
  ### 🧑‍💻 **RNF** (Funcionalidades técnicas)
  -
  ### 📐 **RN** (Regras de negócio)
  -

<br/>

  ### :clipboard: **Caso de Uso: `Realizar Logout`**

<p align="right">
  <a href="#computer-logout">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Realizar Logout`**
  :--- | :---
  **Request http:** | **`POST`**
  **Service:** | **`DeleteUserSession`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas ao realizar logout do sistema.
  &nbsp; | Tem como objetivo permitir que o usuário finalize sua interação com o sistema.
  `Pré-condições:` | O usuário precisa estar logado no sistema.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no botão **Logout**. *`this`* | &nbsp;
  &nbsp; | `2:` **Excluir token e sessão do usuário.**
  &nbsp; | `3:` Carregar <a href="#computer-tela-de-login">**`💻 tela de login`**</a>.
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` -
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **Tela de `Recuperação de Senha`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

### 👨‍💼 **RF** (Usabilidade)

1. Deve ser capaz de recuperar a senha usando o e-mail; 🟢
2. O usuário deve ser capaz de receber um email com o link para recuperação da senha;
2. O usuário deve ser capaz de solicitar o reenvio do link de recuperação de senha;

### 🧑‍💻 **RNF** (Funcionalidades técnicas)

- Utilizar o `Ethereal` para testar envios de email em ambiente de desenvolvimento;
- Utilizar o `Amazon SES` para envios de email em ambiente de produção;
- O envio de emails deve acontecer em segundo plano (background job);

### 📐 **RN** (Regras de negócio)

1. Não deve ser capaz de recuperar a senha com um e-mail de um usuário inexistente; 🟢
1. Deve ser capaz de gerar um token para recuperar a senha esquecida; 🟢
2. O link enviado por email para resetar a senha deve expirar em 2h;
2. Caso o link expire, o usuário poderá solicitar o reenvio do link de recuperação de senha;

<br/>

### :clipboard: **Caso de Uso: `Recuperar Senha`**

<p align="right">
  <a href="#computer-tela-de-recuperação-de-senha">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Recuperar Senha`**
  :--- | :---
  **Request http:** | **`POST`**
  **Service:** | **`SendEmailForPasswordRecovery`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para o usuário recuperar sua senha.
  &nbsp; | Tem como objetivo permitir que o usuário solicite o envio de um link para recuperação de senha.
  `Pré-condições:` | O usuário precisa ativo no sistema.
  `Pós-condições:` | O usuário precisa clicar no link enviado por email para poder cadastrar uma nova senha.
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no botão **esqueci minha senha**. | &nbsp;
  &nbsp; | `2:` Carregar tela de recuperação de senha. *`this`*
  `3:` Informar email cadastrado. | &nbsp;
  `4:` Clicar no botão **Enviar**. | &nbsp;
  &nbsp; | `5:` Localizar usuário pelo email informado.
  &nbsp; | `3:` Verificar se usuário está inativo.
  &nbsp; | `6:` **Enviar link de recuperação para o email cadastrado.**
  &nbsp; | `7:` Carregar <a href="#computer-tela-de-cadastrar-nova-senha">**`💻 tela de cadastro de nova senha`**</a>
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **` Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário inativo`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário inativo.
  &nbsp; | `2:` Carregar <a href="#computer-tela-de-inserção-do-código-de-ativação">**`💻 tela de inserção do código de ativação`**</a>.
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **Tela de `Atualização da Senha do Usuário`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

### 👨‍💼 **RF** (Usabilidade)

1. O usuário deve ser capaz de atualizar sua senha;

### 🧑‍💻 **RNF** (Funcionalidades técnicas)

- Utilizar o `BCryptJS` para criptografar a senha;

### 📐 **RN** (Regras de negócio)

1. O usuário precisa digitar a nova senha duas vezes;

<br/>

### :clipboard: **Caso de Uso: `Atualizar Senha do Usuário`**

<p align="right">
  <a href="#computer-tela-de-atualização-da-senha-do-usuário">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Atualizar Senha do Usuário`**
  :--- | :---
  **Request http:** | **`PUT`**
  **Service:** | **`UpdateUserPassword`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para atualizar a senha do usuário.
  &nbsp; | Tem como objetivo permitir que o usuário atualize sua senha.
  `Pré-condições:` | O usuário precisa estar ativo e ter solicitado a recuperação da senha.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **link de recuperação de senha** enviado por email. | &nbsp;
  &nbsp; | `2:` Verificar se o link enviado está expirado.
  &nbsp; | `3:` Localizar usuário pelo email contido no link.
  &nbsp; | `4:` Verificar se o usuário está inativo.
  &nbsp; | `5:` Carregar tela de cadastro da nova senha. *`this`*
  `6:` Informar senha e senha de confirmação. | &nbsp;
  `7:` Clicar no botão **Confirmar**. | &nbsp;
  &nbsp; | `8:` Comparar as duas senhas informadas.
  &nbsp; | `10:` Verificar se a senha informada é igual a senha cadastrada.
  &nbsp; | `9:` **Atualizar senha.**
  &nbsp; | `10:` Retornar mensagem: Senha salva com sucesso.
  &nbsp; | `11:` Carregar <a href="#computer-tela-de-login">**`💻 tela de login`**</a>.
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`Atualizar senha através do Perfil do Usuário`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **Avatar**. | &nbsp;
  &nbsp; | `2:` Carregar tela de perfil. `*`
  `3:` Clicar na **Senha**. | &nbsp;
  &nbsp; | `4:` Carregar Modal para atualização da senha.
  `5:` Informar senha atual, nova senha e senha de confirmação. | &nbsp;
  `7:` Clicar no botão **Confirmar**. | &nbsp;
  &nbsp; | `8:` Comparar as duas novas senhas informadas.
  &nbsp; | `9:` Localizar usuário pelo id contido na sessão.
  &nbsp; | `10:` Verificar se a senha atual informada é igual a senha cadastrada.
  &nbsp; | `10:` Verificar se a nova senha informada é igual a senha cadastrada.
  &nbsp; | `11:` **Atualizar senha.**
  &nbsp; | `12:` Retornar usuário.
  &nbsp; | `13:` Atualizar tela de perfil.
  &nbsp; | `14:` Fechar Modal.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Link de recuperação expirado`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Link de recuperação inválido.
  &nbsp; | `2:` Carregar <a href="#computer-tela-de-recuperação-de-senha">**`💻 tela de recuperação de senha`**</a>
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | `2:` Carregar a <a href="#computer-tela-de-cadastro-de-usuário">**`💻 tela de cadastro de usuário`**</a>
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário inativo`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário inativo.
  &nbsp; | `2:` Exibir link para <a href="#computer-tela-de-inserção-do-código-de-ativação">**`💻 tela de inserção do código de ativação`**</a>.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Senhas divergentes`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Senhas divergentes.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Nova senha é igual a senha cadastrada`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar usuário.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Senhas atual inválida`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Senha atual inválida.
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **Tela de `Atualização do Perfil`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  ### 👨‍💼 **RF** (Usabilidade)

  1. O usuário deve ser capaz de alterar seu nome; &nbsp; <a href="#clipboard-caso-de-uso-atualizar-nome-do-usuário">**`📋 Atualizar Nome do Usuário`**</a>
  2. O usuário deve ser capaz de alterar seu email; &nbsp; <a href="#clipboard-caso-de-uso-atualizar-email-do-usuário">**`📋 Atualizar Email do Usuário`**</a>
  3. O usuário deve ser capaz de alterar sua senha; &nbsp; <a href="#clipboard-caso-de-uso-atualizar-senha-do-usuário">**`📋 Atualizar Senha do Usuário` &nbsp; Fluxo Alternativo**</a>
  4. O usuário deve ser capaz de alterar seu avatar; &nbsp; <a href="#clipboard-caso-de-uso-atualizar-avatar-do-usuário">**`📋 Atualizar Avatar do Usuário`**</a> 🟢

  ### 🧑‍💻 **RNF** (Funcionalidades técnicas)
  - O usuário será localizado pelo id contido na sessão;
  - Utilizar o `BCryptJS` para criptografar a senha;
  - Utilizar o `Ethereal` para testar envios de email em ambiente de desenvolvimento;
  - Utilizar o `Amazon SES` para envios de email em ambiente de produção;
  - O envio de emails deve acontecer em segundo plano (background job);
  ### 📐 **RN** (Regras de negócio)
  2. O usuário não deve ser capaz de alterar seu email para um email já existente;
  3. O usuário deve informar a senha atual ao alterar sua senha;
  3. O usuário precisa digitar a nova senha duas vezes.
  4. Não deve ser capaz de atualizar o avatar de um usuário inexistente; 🟢
  4. Deve ser capaz de excluir o avatar antigo antes de inserir o novo; 🟢

<br/>
<br/>
<br/>

  ### :clipboard: **Caso de Uso: `Atualizar Nome do Usuário`**

<p align="right">
  <a href="#computer-tela-de-atualização-do-perfil">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Atualizar Nome do Usuário`**
  :--- | :---
  **Request http:** | **`PUT`**
  **Service:** | **`UpdateUserName`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para atualizar o nome do usuário.
  &nbsp; | Tem como objetivo permitir que o usuário atualize seu nome.
  `Pré-condições:` | O usuário precisa estar logado no sistema.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **Avatar**. | &nbsp;
  &nbsp; | `2:` Carregar a tela de perfil. *`this`*
  `3:` Clicar no **Nome**. | &nbsp;
  &nbsp; | `4:` Carregar Modal para atualização do nome.
  `5:` Informar nome. | &nbsp;
  `6:` Clicar no botão **Confirmar**. | &nbsp;
  &nbsp; | `7:` Localizar usuário pelo id contido na sessão.
  &nbsp; | `8:` Verificar se o nome informado é igual ao nome atual cadastrado.
  &nbsp; | `9:` **Atualizar nome.**
  &nbsp; | `11:` Retornar usuário.
  &nbsp; | `12:` Atualizar tela de perfil.
  &nbsp; | `10:` Fechar Modal.
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | `2:` Carregar a <a href="#computer-tela-de-cadastro-de-usuário">**`💻 tela de cadastro de usuário`**</a>
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Nome informado é igual ao nome cadastrado`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar o usuário.
  &nbsp; | &nbsp;

<br/>
<br/>
<br/>

### :clipboard: **Caso de Uso: `Atualizar Email do Usuário`**

<p align="right">
  <a href="#computer-tela-de-atualização-do-perfil">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Atualizar Email do Usuário`**
  :--- | :---
  **Request http:** | **`PUT`**
  **Service:** | **`UpdateUserEmail`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para atualizar o email do usuário.
  &nbsp; | Tem como objetivo permitir que o usuário atualize seu email.
  `Pré-condições:` | O usuário precisa estar logado no sistema.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **Avatar**. | &nbsp;
  &nbsp; | `2:` Carregar tela de perfil. *`this`*
  `3:` Clicar no **Email**. | &nbsp;
  &nbsp; | `4:` Carregar Modal para atualização do email.
  `5:` Informar novo email e confirmação do email. | &nbsp;
  `6:` Clicar no botão **Confirmar**. | &nbsp;
  &nbsp; | `7:` Comparar os dois emails informados.
  &nbsp; | `8:` Verificar se o email informado atende aos padrões de um email válido.
  &nbsp; | `9:` Localizar usuário pelo id contido na sessão.
  &nbsp; | `10:` Localizar outros usuários com o email informado.
  &nbsp; | `11:` Verificar se o email informado é igual ao email atual cadastrado.
  &nbsp; | `12:` **Atualizar email.**
  &nbsp; | `13:` Retornar usuário.
  &nbsp; | `14:` Atualizar tela de perfil.
  &nbsp; | `15:` Fechar Modal.
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Emails divergentes`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Emails divergentes.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Email inválido`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Email inválido.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | `2:` Carregar a <a href="#computer-tela-de-cadastro-de-usuário">**`💻 tela de cadastro de usuário`**</a>
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Email já cadastrado`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Email já cadastrado.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Nova email é igual ao email cadastrado`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar usuário.
  &nbsp; | &nbsp;

<br/>
<br/>
<br/>

  ### :clipboard: **Caso de Uso: `Atualizar Avatar do Usuário`**

<p align="right">
  <a href="#computer-tela-de-atualização-do-perfil">voltar ⤴️</a> &nbsp;
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Atualizar Avatar do Usuário`**
  :--- | :---
  **Request http:** | **`PUT`**
  **Service:** | **`UpdateUserAvatar`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para atualizar o avatar do usuário.
  &nbsp; | Tem como objetivo permitir que o usuário atualize seu avatar.
  `Pré-condições:` | O usuário precisa estar logado no sistema.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **Avatar**. | &nbsp;
  &nbsp; | `2:` Carregar a tela de perfil. *`this`*
  `3:` Clicar no botão **Alterar imagem**. | &nbsp;
  `3:` Informar imagem. | &nbsp;
  `6:` Clicar no botão **Confirmar**. | &nbsp;
  &nbsp; | `7:` Localizar usuário pelo id contido na sessão.
  &nbsp; | `7:` Verificar se o usuário possui um avatar.
  &nbsp; | `8:` Se possuir, excluir avatar.
  &nbsp; | `9:` **Atualizar avatar.**
  &nbsp; | `11:` Retornar usuário.
  &nbsp; | `12:` Atualizar tela de perfil.
  &nbsp; | `10:` Fechar Modal.
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | `2:` Carregar a <a href="#computer-tela-de-cadastro-de-usuário">**`💻 tela de cadastro de usuário`**</a>
  &nbsp; | &nbsp;

<br/>
<br/>
<br/>

  ### :clipboard: **Caso de Uso: `Excluir Conta de Usuário`**

<p align="right">
  <a href="#book-usuários">usuários 📖</a> &nbsp;
  <a href="#análise-de-requisitos">index 📇</a>
</p>

  **Caso de Uso:** | **`Excluir Conta de Usuário`**
  :--- | :---
  **Request http:** | **`DELETE`**
  **Service:** | **`DeleteUser`**
  **Tabelas relacionadas:** | **`users`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | Usuário
  `Atores Secundários:` | -
  `Resumo:` | Este caso de uso descreve as etapas percorridas para realizar a exclusão de uma conta de usuário.
  &nbsp; | Tem como objetivo permitir a exclusão de um usuário e todos os registros relacionados a ele.
  `Pré-condições:` | O usuário precisa estar logado no sistema.
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` Clicar no **Avatar**. | &nbsp;
  `2:` Clicar em **Configurações**. | &nbsp;
  `2:` Clicar em **Exluir Conta de Usuário**. | &nbsp;
  &nbsp; | `3:` Carregar 💻 tela de confirmação de exclusão, informando o que acontecerá se o usuário continuar.
  `4:` Clicar em **Continuar**. | &nbsp;
  &nbsp; | `3:` Carregar 💻 tela solicitando a confirmação por senha.
  `4:` Informar senha. | &nbsp;
  `4:` Clicar em **Continuar**. | &nbsp;
  &nbsp; | `7:` Localizar usuário pelo id contido na sessão.
  &nbsp; | `8:` Validar senha.
  &nbsp; | `9:` Localizar todos os responsáveis com o id do usuário.
  &nbsp; | `9:` Localizar todos os lançamentos como o id dos responsáveis.
  &nbsp; | `10:` **Excluir lançamentos.**
  &nbsp; | `10:` **Excluir responsáveis.**
  &nbsp; | `10:` **Excluir .....**
  &nbsp; | `11:` Atualizar 💻 tela de listagem de responsáveis.
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` -
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Usuário não existe`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Usuário não existe.
  &nbsp; | `2:` Carregar <a href="#computer-tela-de-cadastro-de-usuário">**`💻 tela de cadastro de usuário`**</a>.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Responsável não encontrado`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Responsável não encontrado.
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`Existem lançamentos com o id do responsável`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` Retornar mensagem: Responsável possui um ou mais itens de lançamentos registrados em seu nome. Deseja transferi-los para outro responsável e realizar a exclusão? &nbsp;&nbsp;&nbsp; `TRANSFERIR` &nbsp;&nbsp;&nbsp; `NÃO`
  `2:` Clicar em **TRANSFERIR**. | &nbsp;
  &nbsp; | `3:` Executar <a href="#clipboard-caso-de-uso-transferir-responsável">**`📋 caso de uso transferir responsável`**</a>.
  &nbsp; | `4:` **Excluir responsável.**
  &nbsp; | `5:` Atualizar 💻 tela de listagem de responsáveis.
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>


# Utils

<p align="right">
  <a href="#análise-de-requisitos">index 📇</a>
</p>

## :computer: **Tela de `Dashboard`**

<p align="right">
  <a href="#utils">voltar ⤴️</a>
</p>

### 👨‍💼 **RF** (Usabilidade)

1. O usuário deve ser capaz de visualizar o saldo total atual;
2. O usuário deve ser capaz de visualizar o saldo individual das contas cadastradas;
3. O usuário deve ser capaz de ajustar o saldo de uma conta específica;
4. O usuário deve ser capaz de visualizar o total de contas à receber;
5. O usuário deve ser capaz de visualizar o total de contas à pagar;

### 🧑‍💻 **RNF** (Funcionalidades técnicas)

-

### 📐 **RN** (Regras de negócio)

-

<br/>

### :clipboard: **Caso de Uso: `?`**

<p align="right">
  <a href="#computer-tela-de-dashboard">voltar ⤴️</a>
</p>

  **Caso de Uso:** | **`?`**
  :--- | :---
  **Request http:** | **`?`**
  **Service:** | **`?`**
  **Tabelas relacionadas:** | **`?`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | ?
  `Atores Secundários:` | -
  `Resumo:` | ?
  &nbsp; | ?
  `Pré-condições:` | ?
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`?`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` -
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>

## :computer: **`Menu de Opções`**

<p align="right">
  <a href="#utils">voltar ⤴️</a>
</p>

### 👨‍💼 **RF** (Usabilidade)

1. O usuário deve ser capaz de visualizar o dashboard (home);
2. O usuário deve ser capaz de listar os lançamentos;
3. O usuário deve ser capaz de criar um lançamento;
4. O usuário deve ser capaz de visualizar os relatórios;
5. O usuário deve ser capaz de visualizar as metas;

### 🧑‍💻 **RNF** (Funcionalidades técnicas)

- O menu/barra de opções será localizado na parte inferior;

### 📐 **RN** (Regras de negócio)

-

<br/>

### :clipboard: **Caso de Uso: `?`**

<p align="right">
  <a href="#computer-menu-de-opções">voltar ⤴️</a>
</p>

  **Caso de Uso:** | **`?`**
  :--- | :---
  **Request http:** | **`?`**
  **Service:** | **`?`**
  **Tabelas relacionadas:** | **`?`**
  `Caso de Uso Pai:` | -
  `Ator Principal:` | ?
  `Atores Secundários:` | -
  `Resumo:` | ?
  &nbsp; | ?
  `Pré-condições:` | ?
  `Pós-condições:` | -
  &nbsp; | &nbsp;
  **Fluxo Principal:** | &nbsp;
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo Alternativo:** | **`-`**
  `Ações do Ator` | `Ações do Sistema`
  `1:` - | &nbsp;
  &nbsp; | `2:` -
  &nbsp; | &nbsp;
  **Fluxo de Exceção:** | **`?`**
  `Ações do Ator` | `Ações do Sistema`
  &nbsp; | `1:` -
  &nbsp; | &nbsp;

<br/>
<hr>
<br/>
<br/>
