# 🦄 DOTNET TEMPLATE SKELETON BASED ON ONION ARCHITECTURE

[![Github][github-shield]][github-url]
[![Kofi][kofi-shield]][kofi-url]
[![LinkedIn][linkedin-shield]][linkedin-url]
[![Khanakat][khanakat-shield]][khanakat-url]

## CONTENT

* 🔥 [Description](#description)
* ⚙️ [Installation](#installation)
* 🍵 [Usage](#usage)
* 📓 [Summary](#summary)
* 🏗️ [Project Structure](#project-structure)
* 📄 [License](#license)
* ⭐️ [Give me a star](#give-me-a-star)

## DESCRIPTION

This project is a .NET template skeleton built on the Onion Architecture, providing a solid foundation for scalable, maintainable, and robust application development.

## INSTALLATION

### Clone project

📌 You can Clone this repository using:

```bash
git clone https://github.com/FernandoCalmet/dotnet-onion-architecture-skeleton.git
```

### Setup dotnet template

📌 To install this ``dotnet template``, navigate to the root directory of this repository and run the following command:

```bash
dotnet new install .
```

### Data migration

📌 To migrate your data with ``Entity Framework Core`` you can run the following commands using the Package Manager Console:

Command | Description
--- | ---
add-migration ``[name]`` --startup-project MyCompany.MyProduct.Api --project MyCompany.MyProduct.Persistence --context ApplicationDbContext | Create a new migration with the specific migration name
remove-migration | Remove the latest migration.
update-database | Update the database to the latest migration.
update-database ``[name]`` | Update the database to a specific migration name point.
get-migrations | Lists all available migrations.
script-migration | Generates a SQL script for all migrations.
drop-database | Drop the database.

## USAGE

To create a new project using this template, use the dotnet new command followed by the template name. You can specify additional parameters to customize the generated project.

```bash
dotnet new onion-architecture-skeleton --MyCompanyMyProduct true --DatabaseProvider postgres
```

### Parameters

The following parameters are available for this template:

Parameter | Short Option | Description
--- | --- | ---
--UseSwagger | -U | Includes Swagger UI in the generated project.
--DatabaseProvider | -D | Specifies the database provider to use. Supported values are sqlserver and postgresql.

### Conditional Code and Files

This template uses conditional syntax to include or exclude certain parts of the code based on the parameters you provide. For example, if you specify -D postgresql, the generated project will include a PostgresSql specific repository implementation, and exclude the other database provider files.

## SUMMARY

### Simplifying Software Development
Developing a robust, scalable, and maintainable software architecture is a complex task. The Onion Architecture, a design pattern developed by Jeffrey Palermo and inspired by Uncle Bob's Clean Architecture, addresses these challenges. This architecture aims to make software independent of external dependencies like frameworks, databases, and UI, promoting decoupling and testability.

### Understanding Onion Architecture
The Onion Architecture is structured in four key layers:

### Domain Layer
The core of the architecture, containing business logic, entities, value objects, business rules, and interfaces for contracts with other layers.

### Application Layer
Serves as an interface between the Presentation and Domain layers, containing services that orchestrate application flow and data mapping.

### Infrastructure Layer
Houses technical details like data storage, logging, messaging, etc., and implements interfaces from the Domain layer.

### Presentation Layer
Responsible for presenting output to users and communicating with the Application layer to access Domain layer information.

### Benefits of Onion Architecture in Dotnet
The Onion Architecture enhances testability, maintainability, and flexibility. It allows writing unit tests that depend solely on the Domain layer, unaffected by external frameworks or dependencies. This design also follows the Single Responsibility Principle, simplifying maintenance and refactoring.

## Project Structure
The updated project structure aligns with the principles of Onion Architecture, ensuring a clear separation of concerns and improved maintainability. Here's an overview of the updated directory structure:

```
MyCompany.MyProduct.sln
│
├───src
│   ├───Solution Items
│   │   ├───.editorconfig
│   │   ├───DirectoryBuild.props
│   │   └───Directory.Packages.props
│   ├───Core
│   │   ├───MyCompany.MyProduct.Application
│   │   │   ├───Abstractions
│   │   │   │   ├───Authentication
│   │   │   │   ├───Authorization
│   │   │   │   ├───Caching
│   │   │   │   ├───Clock
│   │   │   │   ├───Data
│   │   │   │   ├───Emails
│   │   │   │   └───Messaging
│   │   │   ├───Behaviors
│   │   │   ├───Exceptions
│   │   │   ├───Extensions
│   │   │   └───Features
│   │   └───MyCompany.MyProduct.Domain
│   │       ├───Abstractions
│   │       ├───Entities
│   │       ├───Enums
│   │       ├───Errors
│   │       ├───Events
│   │       ├───Primitives
│   │       ├───Repositories
│   │       ├───Services
│   │       ├───Shared
│   │       ├───Time
│   │       └───ValueObjects
│   └───External
│       ├───MyCompany.MyProduct.Api
│       │   ├───Extensions
│       │   ├───Middleware
│       │   ├───OpenApi
│       │   └───Dockerfile
│       ├───MyCompany.MyProduct.Infrastructure
│       │   ├───Authentication
│       │   ├───Authorization
│       │   ├───BackgroundJobs
│       │   ├───Caching
│       │   ├───Clock
│       │   ├───Emails
│       │   ├───EventBus
│       │   ├───Extensions
│       │   ├───Logging
│       │   └───Notifications
│       ├───MyCompany.MyProduct.Persistence
│       │   ├───Configurations
│       │   ├───Constants
│       │   ├───Data
│       │   ├───Interceptors
│       │   ├───Extensions
│       │   ├───Migrations
│       │   ├───Repositories
│       │   └───Specifications
│       └───MyCompany.MyProduct.Presentation
│           ├───Authorization
│           ├───Contracts
│           ├───Endpoints
│           ├───Extensions
│           └───Routes
├───tests
│   ├───MyCompany.MyProduct.Api.FunctionalTests
│   │   ├───.files
│   │   └───Infrastructure
│   ├───MyCompany.MyProduct.Application.UnitTests
│   ├───MyCompany.MyProduct.ArchitectureTests
│   │   ├───Application
│   │   ├───Domain
│   │   ├───Infrastructure
│   │   ├───Persistence
│   │   ├───Presentation
│   │   └───Layers
│   ├───MyCompany.MyProduct.Domain.UnitTests
│   │   └───Infrastructure
│   └───MyCompany.MyProduct.IntegrationTests
│       ├───.files
│       └───Infrastructure
└───docker-compose
```

This structure ensures that each component of our system is neatly organized, facilitating easier navigation and understanding of the codebase.

### Conclusion
Onion Architecture offers a robust framework for building maintainable and scalable applications in .NET. By segregating the application into distinct layers, it promotes a clean separation of concerns and enhances the overall software quality. We encourage you to adopt this architecture in your next .NET project for a noticeable improvement in your development process.

## LICENSE
This project is licensed under the License (MIT License) - see the [LICENSE](LICENSE) file for details.

## GIVE ME A STAR
If you found this Implementation useful or used it in your Projects, please give it a star. Thank you! Or, if you're feeling really generous, [Support the project with a small contribution!](https://ko-fi.com/fernandocalmet).

<!--- reference style links --->
[github-shield]: https://img.shields.io/badge/-@fernandocalmet-%23181717?style=flat-square&logo=github
[github-url]: https://github.com/fernandocalmet
[kofi-shield]: https://img.shields.io/badge/-@fernandocalmet-%231DA1F2?style=flat-square&logo=kofi&logoColor=ff5f5f
[kofi-url]: https://ko-fi.com/fernandocalmet
[linkedin-shield]: https://img.shields.io/badge/-fernandocalmet-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/fernandocalmet
[linkedin-url]: https://www.linkedin.com/in/fernandocalmet
[khanakat-shield]: https://img.shields.io/badge/khanakat.com-brightgreen?style=flat-square
[khanakat-url]: https://khanakat.com
