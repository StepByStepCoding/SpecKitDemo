# SpeckitDemo Constitution

## Core Principles

### I. Minimal API Design
All APIs must be built using .NET Minimal API for simplicity, performance, and maintainability. Avoid traditional MVC controllers unless absolutely necessary.

### II. SOLID Principles
Strictly adhere to SOLID principles in all code: Single Responsibility, Open-Closed, Liskov Substitution, Interface Segregation, Dependency Inversion. Each class and method must demonstrate clear adherence.

### III. Test Coverage
Maintain at least 85% code coverage across all production code. Use automated tools to enforce this threshold in CI/CD pipelines.

### IV. Integration Testing
Focus on integration tests for API endpoints, services, and external dependencies. Unit tests are required, but integration tests ensure end-to-end functionality.

### V. Observability
Implement structured logging, metrics, and tracing for all services. Use tools like Serilog, Application Insights, or OpenTelemetry for observability.

## Additional Constraints
Technology stack: .NET 9.0, C# 12+, Minimal API, Entity Framework Core for data access, xUnit for testing.

Security: Implement authentication and authorization as needed, follow OWASP guidelines.

Performance: APIs must respond within 200ms for typical requests.

## Development Workflow
Code reviews required for all PRs, must verify SOLID compliance and test coverage.

CI/CD: Automated builds, tests, coverage checks.

Quality Gates: No merge without 85% coverage, passing tests, code review.

## Governance
Constitution supersedes all other practices. Amendments require documentation, team approval, and migration plan.

All PRs must verify compliance with principles.

**Version**: 1.0.0 | **Ratified**: 2026-05-02 | **Last Amended**: 2026-05-02
