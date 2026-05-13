# Esports-Stats-Hub 🎮

[![Build Status](https://img.shields.io/badge/CI%2FCD-Active-success)](#)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4)](#)
[![EF Core](https://img.shields.io/badge/EF_Core-Relational-339933)](#)
[![Agile](https://img.shields.io/badge/Methodology-Agile%2FScrum-blue)](#)

An enterprise-grade, N-Tier ASP.NET Core backend and management portal designed to ingest, process, and analyze Counter-Strike match telemetry and behavioral patterns.

## Executive Summary
This project serves as a robust backend infrastructure for e-sports data analytics. It features a RESTful API capable of receiving parsed match logs—integrating seamlessly with upstream extraction tools like the `demoinfocs-golang` parser—a secure Blazor/Razor frontend for data management, and a highly decoupled architecture utilizing Dependency Injection and Custom Middleware.

## Agile Project Management & Delivery
The development lifecycle is structured into distinct Agile Epics to ensure continuous integration and iterative delivery:

*   **Epic 1: Foundation & Data Access** - Repository setup, Dependency Injection configuration, and Entity Framework Core migrations.
*   **Epic 2: Quality Assurance & Middleware** - Data validation pipelines and custom HTTP request middleware.
*   **Epic 3: REST API Implementation** - Development of decoupled endpoints for Match and Player telemetry (CRUD).
*   **Epic 4: Security & Identity** - JWT/Cookie authentication and RBAC authorization policies.
*   **Epic 5: Management Portal** - Razor/Blazor interactive frontend for data visualization.

## Architecture & Tech Stack
*   **Framework**: ASP.NET Core Web API & Blazor/Razor Pages
*   **Persistence**: Entity Framework Core (Code-First approach)
*   **Database**: SQLite (Dev/Test) / SQL Server (Prod)
*   **DevOps/Deployment**: Container-ready architecture (Docker), designed for CI/CD pipeline integration (GitHub Actions/Azure DevOps).
*   **Telemetry Pipeline**: Designed to ingest JSON payloads containing structured behavioral data and match events.

## Requirement Traceability Matrix
This repository strictly adheres to the defined technical specifications:
- [ ] **RESTful Operations**: `GET`, `POST`, `PUT`, `DELETE` fully implemented for core domain entities.
- [ ] **Data Validation**: FluentValidation / DataAnnotations ensuring payload integrity.
- [ ] **Dependency Injection**: Services and repositories registered via the built-in IoC container.
- [ ] **Middleware**: Custom request pipeline interception for error handling and logging.
- [ ] **Entity Framework**: Relational data modeling with migrations.
- [ ] **Authentication**: Secure endpoints requiring verified identity.
- [ ] **Views**: Razor/Blazor UI implemented for frontend interactions.

## 📡 API Specification

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `GET`  | `/api/matches` | Retrieves paginated match history. | No |
| `GET`  | `/api/matches/{id}` | Fetches granular behavioral stats for a specific match. | No |
| `POST` | `/api/matches` | Ingests a new parsed CS demo JSON payload. | Yes |
| `PUT`  | `/api/matches/{id}` | Updates metadata, tags, or analyst notes. | Yes |
| `DELETE`| `/api/matches/{id}` | Purges corrupted or anomalous match records. | Yes |

## 🚀 CI/CD & Local Provisioning

### Prerequisites
* .NET 10.0 SDK
* SQL Server (or SQLite configured in `appsettings.json`)

### Environment Setup
1. **Clone the repository:**
   ```bash
git clone [https://github.com/YourUsername/Esports-Stats-Hub.git](https://github.com/YourUsername/Esports-Stats-Hub.git)
cd Esports-Stats-Hub

   ```
 2. **Restore dependencies:**
   ```bash
dotnet restore
   
   ```
 3. **Apply Database Migrations:**
   ```bash
dotnet ef database update
   
   ```
 4. **Run the Application:**
   ```bash
dotnet run
   
   ```