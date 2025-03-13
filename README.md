# Projeto de gerenciamento de Contatos com Monitoramento e Integração de CI/CD 

Este projeto é uma aplicação para gerenciar contatos, permitindo o cadastro, consulta, atualização e exclusão de informações de contatos, como nome, telefone e e-mail, associando-os a uma região com base no DDD, também contém a implementação de um sistema de monitoramento utilizando Prometheus e Grafana, além de um pipeline de CI/CD com GitHub Actions para garantir a qualidade e a integridade do código. O sistema visa coletar métricas sobre a performance do aplicativo e garantir a execução de testes de qualidade contínuos.

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


### Persistência de Dados

- Utiliza um banco de dados para armazenar as informações dos contatos.
- O projeto implementa acesso a dados com **Entity Framework Core**.

  
### Validações

- Validações para garantir consistência dos dados:
    - **Formato de e-mail** válido.
    - **Formato de telefone** de acordo com a norma.
    - Verificação de **campos obrigatórios**.

### Testes Unitários

- Testes unitários foram desenvolvidos utilizando **xUnit** ou para garantir a qualidade do código.


### GitHub Actions - CI Pipeline
O pipeline de CI foi configurado para garantir que o código esteja sempre funcionando corretamente, através de três etapas principais:

1. Build (Compilação):
A primeira etapa garante que o código seja compilado corretamente, sem erros. Isso assegura que o sistema não tenha falhas de compilação que possam impedir a execução adequada da aplicação.

2. Testes Unitários:
Após a compilação, os testes unitários são executados. Esses testes verificam se as funções e componentes do sistema estão funcionando conforme o esperado em nível individual.

3. Testes de Integração:
A etapa de testes de integração garante que os diferentes componentes do sistema, como a comunicação com o banco de dados e outros serviços, funcionem corretamente em conjunto. Estes testes validam a integração do sistema como um todo.


## Integração com Prometheus
O sistema foi integrado com o Prometheus para coletar métricas importantes sobre o desempenho da aplicação. As métricas coletadas incluem:

- Latência das requisições: Mede o tempo de resposta de cada requisição.
- Uso de CPU: Monitora a utilização de CPU para detectar possíveis sobrecargas.
- Uso de Memória: Monitora o consumo de memória para identificar possíveis problemas de eficiência de recursos.

### Configuração de Endpoints de Métricas no Aplicativo
Foram configurados endpoints específicos no aplicativo para que o Prometheus consiga coletar as métricas mencionadas acima. Estes endpoints expõem as métricas em um formato que o Prometheus pode consumir e processar.

### Configuração de Grafana
Para facilitar a visualização das métricas coletadas pelo Prometheus, foi configurado um Dashboard no Grafana, com os seguintes painéis:

- Latência por Endpoint: Exibe o tempo médio de resposta para cada endpoint da aplicação.
- Contagem de Requisições por Status de Resposta: Mostra o número de requisições com diferentes códigos de status HTTP (por exemplo, 200, 404, 500).
- Uso de Recursos do Sistema: Exibe o consumo de CPU e memória ao longo do tempo, permitindo identificar picos de consumo e avaliar a eficiência do sistema.


## Tecnologias Utilizadas

- **Linguagem**: C#
    - Utilizada para o desenvolvimento do aplicativo, oferecendo uma plataforma robusta e moderna para aplicações backend.
- **Framework**: .NET Core
    - Framework multiplataforma utilizado para construir o aplicativo de forma eficiente, garantindo alto desempenho e escalabilidade.
- **Banco de Dados**: SQL Server
    - Sistema de gerenciamento de banco de dados relacional utilizado para armazenar dados persistentes do aplicativo.
- **ORM**: Entity Framework Core
    - Framework ORM (Object-Relational Mapping) que facilita a interação com o banco de dados, tornando as operações de leitura e escrita mais intuitivas e produtivas.
- **Testes**: xUnit
    - Framework de testes para .NET, utilizado para garantir a qualidade do código por meio de testes unitários e de integração.
- **GitHub Actions**:
    - Automatiza a integração contínua (CI) e a entrega contínua (CD), executando etapas como compilação, testes unitários e testes de integração, garantindo que o código seja sempre verificado antes de ser integrado ao repositório principal.
- **Prometheus**:
    - Ferramenta de monitoramento de sistemas que coleta métricas de desempenho em tempo real, como latência das requisições e uso de CPU/memória, permitindo a análise e a otimização da aplicação.
- **Grafana**:
    - Plataforma de visualização e análise de métricas, usada para criar dashboards interativos que exibem as informações coletadas pelo Prometheus, oferecendo insights sobre o desempenho e uso de recursos do sistema.
- **Docker**:
    - Ferramenta de contêinerização que facilita a execução de ambientes isolados para o Prometheus e Grafana, simplificando a configuração e garantindo que as ferramentas funcionem de maneira consistente em diferentes ambientes.
