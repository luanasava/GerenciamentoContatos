# Gerenciamento de Contatos

Este projeto é uma aplicação para gerenciar contatos, permitindo o cadastro, consulta, atualização e exclusão de informações de contatos, como nome, telefone e e-mail, associando-os a uma região com base no DDD.

## Funcionalidades

### Cadastro de Contatos

- Permite o cadastro de novos contatos com as seguintes informações:
    - **Nome**
    - **Telefone**
    - **E-mail**
    - **DDD** (correspondente à região)

### Consulta de Contatos

- Os usuários podem consultar os contatos cadastrados e filtrá-los por **DDD**.
- Visualização dos detalhes de cada contato.

### Atualização e Exclusão de Contatos

- Os usuários podem atualizar as informações de contatos previamente cadastrados.
- Exclusão de contatos da base de dados.

## Requisitos Técnicos

### Persistência de Dados

- Utiliza um banco de dados para armazenar as informações dos contatos.
- O projeto implementa acesso a dados com **Entity Framework Core** ou **Dapper**.

### Validações

- Validações para garantir consistência dos dados:
    - **Formato de e-mail** válido.
    - **Formato de telefone** de acordo com a norma.
    - Verificação de **campos obrigatórios**.

### Testes Unitários

- Testes unitários foram desenvolvidos utilizando **xUnit** ou para garantir a qualidade do código.


## Tecnologias Utilizadas

- **Linguagem:** C#
- **Framework:** .NET Core
- **Banco de Dados:**  SQL Server
- **ORM:** Entity Framework Core
- **Testes:** xUnit
