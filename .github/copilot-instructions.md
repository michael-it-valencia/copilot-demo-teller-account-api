# Copilot Instructions for Teller Account API

## Project Overview
This is a .NET 10 minimal API for bank teller account management, built with domain-driven design (DDD) and clean architecture principles. The API provides CRUD operations for account entities using an in-memory database.

## Architecture & Design Patterns
- **Clean Architecture**: Organize code into layers - Domain (business logic), Application (use cases), Infrastructure (data access), and Presentation (API endpoints)
- **Domain-Driven Design**: Model the domain with entities like `Account`, value objects, and domain services
- **Minimal API**: Use ASP.NET Core minimal APIs for lightweight, high-performance endpoints
- **Dependency Injection**: Register services in `Program.cs` with scoped/singleton lifetimes as appropriate

## Key Components
- **Account Entity**: Core domain model with properties like Id, AccountNumber, Balance, AccountType
- **Repository Pattern**: Abstract data access with interfaces in Domain, implementations in Infrastructure
- **CQRS Pattern**: Separate commands (create/update/delete) from queries (read operations)

## Development Workflow
- **Build**: `dotnet build` - compiles the project
- **Run**: `dotnet run` - starts the API server on localhost:5000/5001
- **Test**: `dotnet test` - runs unit and integration tests
- **Docker**: `docker build -t teller-api .` then `docker run -p 8080:80 teller-api`

## Testing Strategy
- **Unit Tests**: Test domain logic and services in isolation using xUnit/MSTest
- **Integration Tests**: Test API endpoints with WebApplicationFactory, verifying HTTP responses and data persistence
- **In-Memory Database**: Use EF Core in-memory provider for fast, isolated tests

## Code Conventions
- **Naming**: PascalCase for classes/methods, camelCase for parameters
- **Async/Await**: Use async methods for I/O operations
- **Validation**: Use DataAnnotations or FluentValidation for input validation
- **Error Handling**: Return appropriate HTTP status codes (400 for bad requests, 404 for not found, 500 for server errors)

## Dependencies
- **EF Core**: For ORM and in-memory database
- **Swashbuckle.AspNetCore**: For Swagger/OpenAPI documentation
- **xUnit**: For testing framework

## File Structure
```
src/
├── Domain/          # Entities, interfaces, domain services
├── Application/     # Use cases, commands, queries
├── Infrastructure/  # Data access, external services
└── Presentation/    # API controllers/endpoints
tests/
├── UnitTests/       # Domain and service tests
└── IntegrationTests/# API endpoint tests
```