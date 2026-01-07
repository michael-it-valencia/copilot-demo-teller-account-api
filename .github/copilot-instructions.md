# Copilot Instructions for the Teller Account API

## Overview
This project is a backend account API for a bank teller application, built using Domain Driven Design (DDD) principles and microservices architecture with .NET 10. The API follows clean architecture practices and is designed for easy integration and deployment.

## Architecture
- **Domain Driven Design**: The project is structured around the core domain of account management, ensuring that business logic is central to the design.
- **Microservices**: Each service is responsible for a specific functionality, promoting separation of concerns and scalability.
- **In-Memory Database**: For development and testing, an in-memory database is utilized, simplifying setup and teardown processes.

## Developer Workflows
- **Building the Project**: Use the command `dotnet build` to compile the project.
- **Running Tests**: Execute `dotnet test` to run unit and integration tests. Ensure that the in-memory database is properly configured for tests.
- **Debugging**: Use Visual Studio or VS Code with the .NET debugger to set breakpoints and inspect the application flow.

## Project Conventions
- **Minimal API**: The project leverages .NET 10's minimal API features for streamlined endpoint definitions.
- **Swagger Integration**: Swagger is integrated for API documentation. Access it at `/swagger` after running the application.
- **Docker Deployment**: A Dockerfile is included for containerized deployment. Build the image using `docker build -t teller-account-api .` and run it with `docker run -p 80:80 teller-account-api`.

## Key Files and Directories
- **`/src`**: Contains the main application code, organized by feature.
- **`/tests`**: Contains unit and integration tests, ensuring code quality and functionality.
- **`Dockerfile`**: Configuration for building the Docker image.
- **`Program.cs`**: Entry point for the application, where services are configured and endpoints are defined.

## Integration Points
- **External Services**: The API may interact with external services for account verification and transaction processing. Ensure proper error handling and logging for these interactions.

## Conclusion
These instructions should help AI agents understand the structure and workflows of the Teller Account API project, enabling them to assist effectively in development tasks.