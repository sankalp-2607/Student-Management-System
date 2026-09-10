# Student Management System

A RESTful Web API built with **ASP.NET Core**, **Entity Framework Core**, and **SQL Server** for managing student records. The application implements full CRUD functionality using the **Repository Pattern** for clean separation of concerns.

![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet)
![C#](https://img.shields.io/badge/C%23-239120?logo=c-sharp&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?logo=microsoftsqlserver&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

---

## Overview

This project is a backend API for managing student records — supporting creation, retrieval, updates, deletion, and search. It's built around a layered architecture (Controllers → Repositories → Data) to keep business logic decoupled from data access, and uses Entity Framework Core's Code-First approach for schema management.

## Features

- Full CRUD operations for student records
- Search students by name
- Repository Pattern for data access abstraction
- Dependency Injection throughout
- Code-First EF Core migrations
- Swagger / OpenAPI documentation
- SQL Server persistence

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | ASP.NET Core Web API (.NET 8) |
| Language | C# |
| ORM | Entity Framework Core |
| Database | SQL Server |
| Docs | Swagger / OpenAPI |
| Tooling | Visual Studio / VS Code, Git |

## Project Structure

```text
StudentManagementSystem
│
├── Controllers/
│   └── StudentsController.cs
├── Models/
│   └── Student.cs
├── Data/
│   └── ApplicationDbContext.cs
├── Repositories/
│   ├── IStudentRepository.cs
│   └── StudentRepository.cs
├── DTOs/
├── Migrations/
├── Program.cs
└── appsettings.json
```

## Database Schema

**Student**

| Field | Type |
|---|---|
| Id | int |
| FirstName | string |
| LastName | string |
| Email | string |
| Age | int |
| Course | string |
| CreatedAt | DateTime |

## Getting Started

### Prerequisites

- [.NET SDK 8.0+](https://dotnet.microsoft.com/download)
- SQL Server (local or remote instance)
- Visual Studio 2022 or VS Code

### Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/student-management-system.git
cd student-management-system
```

Update the connection string in `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=YOUR_SERVER;Database=StudentManagementDB;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

Apply migrations and run:

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
dotnet run
```

The API will start locally, and Swagger UI will be available at `/swagger`.

## API Reference

### Get all students
```http
GET /api/students
```

### Get student by ID
```http
GET /api/students/{id}
```

### Create a student
```http
POST /api/students
```
```json
{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john@example.com",
  "age": 20,
  "course": "Computer Science"
}
```

### Update a student
```http
PUT /api/students/{id}
```

### Delete a student
```http
DELETE /api/students/{id}
```

### Search students
```http
GET /api/students/search?name=john
```

## Roadmap

- [ ] JWT authentication & authorization
- [ ] Role-based access control
- [ ] Pagination and sorting
- [ ] Global exception handling middleware
- [ ] Logging with Serilog
- [ ] Unit tests (xUnit)
- [ ] Docker support
- [ ] Cloud deployment (Azure)

## Contributing

Contributions and suggestions are welcome. Fork the repo, create a feature branch, and submit a pull request.

## License

This project is licensed under the MIT License.

## Author

**Sankalp Sharma**
B.Tech Computer Science · ASP.NET Core & React Developer
