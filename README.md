# Catering Service

Catering Service is a layered ASP.NET Core Web API for managing tenants, companies, suppliers, dishes, menu categories, addresses, and users in a catering platform backed by PostgreSQL.

## Stack

- ASP.NET Core Web API
- Layered solution structure: `CateringService`, `CateringService.Application`, `CateringService.Domain`, `CateringService.Persistence`, `CateringService.Tests`
- Entity Framework Core with PostgreSQL
- JWT bearer authentication
- FluentValidation for request validation
- AutoMapper for DTO mapping
- Serilog for structured logging
- API versioning
- Swagger / OpenAPI
- Health checks
- xUnit unit tests

## Features

- CRUD endpoints for tenants, companies, addresses, dishes, menu categories, and users
- Tenant block and unblock operations
- Company search and filtering scenarios
- Supplier-scoped dishes and menu categories
- Multipart form support for dish creation with local file storage
- Global error handling middleware
- Request logging filter with Serilog
- JWT authentication
- PostgreSQL health check endpoint
- Swagger UI for manual API testing
- API versioning for dish endpoints

## Run Locally

Restore dependencies:

```bash
dotnet restore
```

Start PostgreSQL with Docker Compose:

```bash
docker-compose up -d
```

Apply EF Core migrations:

```bash
dotnet ef database update --project .\CateringService.Persistence\CateringService.Persistence.csproj --startup-project .\CateringService\CateringService.csproj
```

Start the API:

```bash
dotnet run --project .\CateringService\CateringService.csproj
```

## Example Request

`POST /api/tenants`

```http
Content-Type: application/json

{
  "name": "Acme Catering"
}
```

## Testing

```bash
dotnet test
```
