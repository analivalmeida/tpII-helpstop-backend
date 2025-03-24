# Técnicas de Programação II 

![Logo por Extenso](https://github.com/user-attachments/assets/3fa1120d-97be-4046-8f7c-dd92a37a8947)

![Badge do Status](https://img.shields.io/badge/status-em%20desenvolvimento-pink)

![Badge da Licença](https://img.shields.io/badge/licença-MIT-pink)

## HelpApp

O HelpApp é um sistema de gestão de atendimentos voluntários, desenvolvido com o objetivo de facilitar o encontro entre aqueles que precisam de ajuda e aqueles dispostos a oferecer suporte. Através de uma plataforma intuitiva e interativa, o HelpApp conecta os usuários de maneira eficiente, promovendo uma experiência positiva tanto para quem solicita quanto para quem oferece o atendimento voluntário.

- **Objetivo**: Organizar atendimentos voluntários de maneira eficiente.
- **Problema Resolvido**: Facilitar o encontro entre solicitantes e voluntários.
- **Público-Alvo**: Organizações e indivíduos que oferecem e solicitam ajuda voluntária.

### Tecnologias e Frameworks Utilizados

- **.NET Core**: Plataforma de desenvolvimento para o back-end, permitindo uma estrutura escalável e de alta performance.
- **SQL Server**: Banco de dados relacional utilizado para persistência de dados, garantindo confiabilidade e integridade das informações.
- **Azure Server Apps**: Plataforma de nuvem para a implantação do sistema, oferecendo escalabilidade e alta disponibilidade.
- **Clean Architecture**: Arquitetura aplicada para organizar o código de forma que cada camada do sistema seja desacoplada, facilitando manutenção e testes.
- **SOLID**: Princípios de design de software que foram seguidos para garantir que o sistema fosse flexível, sustentável e de fácil compreensão.

## Funcionalidades

- **Cadastro de Usuários**: Permite o cadastro de dois tipos de usuários no sistema: **Ajudantes**, voluntários que se cadastraram para oferecer ajuda, e **Solicitantes**, pessoas que precisam de ajuda e buscam voluntários.

- **Registro e Gerenciamento de Atendimentos**: Permite registrar e gerenciar atendimentos voluntários, com a opção de visualizar o histórico e o status de cada atendimento.

- **Histórico e Relatórios de Ações**: Os usuários podem acessar o histórico de atendimentos realizados e gerar relatórios com informações sobre os atendimentos passados.

- **Login Seguro com Autenticação e Autorização**: Implementação de login seguro com autenticação (verificação de identidade) e autorização (controle de acesso) para garantir que apenas usuários autorizados possam acessar as funcionalidades.

## Estrutura de Pastas

- **HelpApp.API**: Pasta com a camada de interface que expõe os endpoints da API.
  
- **HelpApp.Application**: Pasta com a camada de aplicação responsável pela lógica dos casos de uso.
  - **Interfaces**: Subpasta que define contratos para os serviços da aplicação.
    - `ICategoryService.cs`
    - `IProductService.cs`
  - **Services**: Subpasta que implementa a lógica de negócios específica da aplicação.
    - `CategoryService.cs`
    - `ProductService.cs`

- **HelpApp.Domain**: Pasta com a camada central da arquitetura, onde estão as entidades e regras de negócio.
  - **Entities**: Subpasta que define os modelos do domínio.
    - `Category.cs`
    - `Product.cs`
  - **Validation/**: Subpasta que contém as regras de validação do domínio.
    - `DomainExceptionValidation.cs`

- **HelpApp.Infra.Data**: Pasta com a camada de infraestrutura responsável pelo acesso a dados.
  - **Repositories**: Subpasta que implementa os repositórios para persistência em banco de dados.
    - `CategoryRepositories.cs`
    - `ProductRepositories.cs`

- **HelpApp.Infra.IoC**: Pasta com a camada responsável pela injeção de dependências e configuração de serviços.
  - `DependencyInjectionAPI.cs`: Define a configuração dos serviços injetáveis do projeto.
 
  ## Arquitetura do Projeto

  O HelpApp segue a Clean Architecture, garantindo a separação de responsabilidades e facilitando a manutenção, escalabilidade e testabilidade do sistema. O código é dividido em quatro camadas principais:

- Domain: O núcleo do sistema, contendo as regras de negócio.

- Application: Implementação dos casos de uso e orquestração da lógica.

- Infrastructure: Persistência de dados e comunicação com serviços externos.

- Interface: Pontos de entrada do sistema, como controllers e front-end.

|                   Interface (API)                     |
|-------------------------------------------------------|
|  **Controllers:** Recebem requisições e chamam a camada de Aplicação. |
|                                                       |
|                   **Application**                         |
|                                                       |
|  **Casos de uso:** Orquestram a lógica de aplicação, chamando serviços e validando regras de negócio.     |
|                                                       |
|                      **Domain**                           |
|                                                       |
|  Entidades e regras de negócio. Não depende de nada   |
|  externo. Implementa as validações essenciais.        |
|                                                       |
|                 **Infrastructure**                        |
|                                                       |
|  **Repositórios:** Comunicação com o banco de dados.      |
|  Implementação de serviços externos (ex: autenticação)|
|                                                       |




