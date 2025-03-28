# Técnicas de Programação II 

![Logo por Extenso](https://github.com/user-attachments/assets/3fa1120d-97be-4046-8f7c-dd92a37a8947)

![Badge do Status](https://img.shields.io/badge/status-em%20desenvolvimento-pink)

![Badge da Licença](https://img.shields.io/badge/licença-MIT-pink)

## HelpApp

O HelpApp é um sistema de gestão de atendimentos voluntários, desenvolvido com o objetivo de facilitar o encontro entre aqueles que precisam de ajuda e aqueles dispostos a oferecer suporte. Através de uma plataforma intuitiva e interativa, o HelpApp conecta os usuários de maneira eficiente, promovendo uma experiência positiva tanto para quem solicita quanto para quem oferece o atendimento voluntário.

- **Objetivo**: Organizar atendimentos voluntários de maneira eficiente.
- **Problema Resolvido**: Facilitar o encontro entre solicitantes e voluntários.
- **Público-Alvo**: Organizações e indivíduos que oferecem e solicitam ajuda voluntária.

### Funcionalidades

- **Cadastro de Usuários**: Permite o cadastro de dois tipos de usuários no sistema: **Ajudantes**, voluntários que se cadastraram para oferecer ajuda, e **Solicitantes**, pessoas que precisam de ajuda e buscam voluntários.

- **Registro e Gerenciamento de Atendimentos**: Permite registrar e gerenciar atendimentos voluntários, com a opção de visualizar o histórico e o status de cada atendimento.

- **Histórico e Relatórios de Ações**: Os usuários podem acessar o histórico de atendimentos realizados e gerar relatórios com informações sobre os atendimentos passados.

- **Login Seguro com Autenticação e Autorização**: Implementação de login seguro com autenticação (verificação de identidade) e autorização (controle de acesso) para garantir que apenas usuários autorizados possam acessar as funcionalidades.

## Arquitetura do Projeto

### Estrutura de Pastas

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
 
### Arquitetura Utilizada

  O HelpApp segue a Clean Architecture, garantindo a separação de responsabilidades e facilitando a manutenção, escalabilidade e testabilidade do sistema. O código é dividido em quatro camadas principais:

- **Domain:** O núcleo do sistema, contendo as regras de negócio.

- **Application:** Implementação dos casos de uso e orquestração da lógica.

- **Infrastructure:** Persistência de dados e comunicação com serviços externos.

- **Interface:** Pontos de entrada do sistema, como controllers e front-end.

### Padrões Utilizados

O projeto adota os seguintes padrões de arquitetura:

- **Clean Architecture:** Separação de responsabilidades e desacoplamento entre camadas.

- **DDD (Domain-Driven Design):** Modelagem orientada ao domínio para garantir que o código represente fielmente as regras do negócio.

- **SOLID:** Princípios para garantir modularidade e manutenção do código.

### Princípios SOLID Aplicados

- **S - Single Responsibility Principle**
Esse princípio afirma que uma classe deve ter apenas uma responsabilidade e uma razão para mudar, nada além disso. Quanto menor a classe, maior o entendimento que você vai ter dela e mais simples será de refatorar e se precisar excluir não vai ter tanto trabalho.
  
- **O - Open/Closed Principle**
Esse princípio afirma que as classes devem estar abertas para extensãode novas funcionalidades mas fechadas para modificação do código já existente, o que minimiza o risco de introduzir bugs em funcionalidades já testadas.

- **L - Liskov Substitution Principle**
Esse princípio afirma que uma classe derivada deve poder substituir a classe base sem alterar as funcionalidades. Um exemplo seria ser pagar o plano básico de um serviço de streaming e mudar para um plano mais premium, você vai ter os benefícios do plano básico + os benefícios do plano premium.

- **I - Interface Segregation Principle**
Esse princípio afirma que uma interface não deve forçar classes a implementar métodos que elas não utilizam, ou seja, se o método não vai ser utilizado no momento mas vai ser no futuro, coloque ele apenas no futuro.

- **D - Dependency Inversion Principle**
Esse princípio afirma que você deve inverter as dependências, ou seja, módulos de alto nível não devem depender de módulos de baixo nível, mas sim de abstrações. Abstrações não devem depender de detalhes, mas sim os detalhes que devem depender das abstrações. Isso facilita a troca de umplementações sem impactar tanto o código

### Tecnologias e Frameworks Utilizados

- **.NET Core**: Plataforma de desenvolvimento para o back-end, permitindo uma estrutura escalável e de alta performance.
- **SQL Server**: Banco de dados relacional utilizado para persistência de dados, garantindo confiabilidade e integridade das informações.
- **Azure Server Apps**: Plataforma de nuvem para a implantação do sistema, oferecendo escalabilidade e alta disponibilidade.
- **Clean Architecture**: Arquitetura aplicada para organizar o código de forma que cada camada do sistema seja desacoplada, facilitando manutenção e testes.
- **SOLID**: Princípios de design de software que foram seguidos para garantir que o sistema fosse flexível, sustentável e de fácil compreensão.

## Instruções para rodar o projeto

### Pré-requisitos
- Ter uma conta no GitHub
- Ter as dependências necessárias instaladas

### Tutorial
- Abra o Explorador de Arquivos
- Entre na pasta que deseja clonar o repositório e escreva na barra de pesquisa "cmd"
- Dê o comando "git clone https://github.com/analivalmeida/tpII-helpstop-backend.git"
- Abra o Visual Studio e clique em  "Abrir um projeto ou solução" e selecione HelpApp.sln
- Abra o arquivo **appsettings.json**
- Edite a chave **ConnectionStrings** com os dados corretos do seu banco
- Abra o Package Manager Console no Visual Studio (Tools > NuGet Package Manager > Package Manager Console) e execute: Update-Database
- No VS clique no botão "Iniciar" com o ícone de play verde

## Camada de Testes

Atualmente, os testes estão concentrados em três camadas principais:

- **Domain**
  - Validação das regras de negócio das entidades (Category.cs, Product.cs)
  - Testes unitários para métodos críticos (exemplo: restrições de nome e preço)
- **Application**
  - Testes dos casos de uso (ProductService.cs, CategoryService.cs)
  - Garantia de que os serviços chamam corretamente os repositórios
- **Infrastructure**
  - Testes nos repositórios (ProductRepositories.cs, CategoryRepositories.cs)
  - Verificação da integração com o banco de dados (testes de persistência)
 
**Observação:** A camada de **Interface (API)** não possui testes automatizados no momento, mas pode ser validada via Postman ou Swagger.

### Execução dos Teste

Para rodar os testes, siga os passos abaixo:

- Abra o terminal na raiz do projeto
- Navegue até a pasta de testes
- Execute o comando: "dotnet test"

### Ferramentas

O HelpApp utiliza as seguintes ferramentas para testes:

- xUnit → Framework de testes unitários
- FluentAssertions → Para tornar as asserções mais legíveis e expressivas

---

## Agradecimentos
Obrigada por ter interesse no meu projeto e por ler até aqui! 🩷

🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷🩷
