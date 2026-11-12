# Technology Stack

## Backend

| Area | Technology | Usage |
|---|---|---|
| Runtime | .NET 10 / C# 14 | ASP.NET Core Web API host and business modules. |
| Architecture | Modular Monolith + Clean Architecture per module | Domain-oriented module boundaries and shared building blocks. |
| ORM | Entity Framework Core 9.x | Persistence and query operations. |
| Database | PostgreSQL 17 / Npgsql | Primary relational database. |
| Schema migrations | DbUp + SQL scripts | Versioned database schema changes. |
| Authentication | ASP.NET Core Identity + JWT | Customer/admin identity and authentication. |
| Authorization | Permission-based RBAC | Fine-grained API and admin UI access. |
| CQRS | MediatR 12.x | Command/query dispatch and handlers. |
| Validation | FluentValidation 11.x | Request and command validation pipeline. |
| Result handling | Ardalis.Result | Explicit application result outcomes. |
| Mapping | Mapster | Object/DTO mapping. |
| Caching | PostgreSQL-backed distributed cache | `IDistributedCache` via `PostgresDistributedCache`; no Redis cache in the current API guidance. |
| Observability | Serilog, OpenTelemetry, Seq | Structured logs and telemetry. |
| Background jobs | Hangfire | Background job processing with PostgreSQL storage. |
| API documentation | OpenAPI + Scalar | API contract and interactive API documentation. |

## Storefront

| Area | Technology |
|---|---|
| Framework | Angular 21.2.x |
| Rendering | Angular SSR (`@angular/ssr`) |
| Language | TypeScript 5.9.x |
| Reactive layer | RxJS 7.8.x |
| Styling | Tailwind CSS 4 and project theme styles |
| API client | `ng-openapi-gen` |
| Server runtime | Node.js / Express SSR server |

## Admin Application

| Area | Technology |
|---|---|
| Framework | Angular 21.2.x |
| UI | Angular Material 21 / Material 3 theming |
| Language | TypeScript 5.9.x |
| State | Angular Signals and RxJS |
| Components | Standalone components with OnPush change detection |
| Forms | Typed reactive forms |
| API client | `ng-openapi-gen` generated services/models |
| Authentication | HttpOnly cookie-based flow with refresh handling |
| Testing | Jasmine, Karma, and Cypress (as documented by the admin project guide) |

## Quality & Testing Tooling

- xUnit v3 for backend tests.
- NSubstitute for test doubles.
- Shouldly for assertions.
- Bogus for test data generation.
- Testcontainers and Respawn for integration-test infrastructure.
- NetArchTest for architecture-rule enforcement.
- GitHub Actions and Docker are used in the private engineering repositories; internal workflow files are intentionally not included in this public showcase.

> Versions above reflect the supplied project manifests and engineering guidance at the time this portfolio was prepared. They may change as dependencies are updated.
