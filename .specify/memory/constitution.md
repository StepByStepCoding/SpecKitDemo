<!--
Sync Impact Report
Version change: n/a → 1.0.0
Modified principles: none (new constitution created)
Added sections: Architecture Constraints, Development Workflow
Removed sections: none
Templates requiring updates:
- .specify/templates/plan-template.md ✅ aligned
- .specify/templates/spec-template.md ✅ aligned
- .specify/templates/tasks-template.md ✅ aligned
- .specify/templates/constitution-template.md ✅ aligned
Follow-up TODOs: none
-->

# SpeckitDemo Constitution

## Core Principles

### I. API-First Design
Every feature MUST begin with a defined API contract, endpoint, or service interface before implementation. Requirements and acceptance criteria MUST be expressed in API terms so the design is testable, reviewable, and decoupled from delivery technology.

### II. Clean Architecture
Application logic MUST be organized into layers where business rules are independent of framework, UI, persistence, and transport adapters. Core domain behavior MUST be protected by abstractions so changes in delivery or infrastructure do not force changes in business rules.

### III. Dependency Injection
All application services, external dependencies, and infrastructure components MUST be wired through dependency injection. Hidden global state and static singletons are prohibited unless documented as a necessary exception with explicit tradeoffs.

### IV. Test Coverage & Validation
The codebase MUST maintain a minimum of 85% coverage for API and domain-critical behavior. Tests MUST include contract validation, unit tests for service abstractions, and integration tests for end-to-end API flows where the feature boundary is exercised.

### V. Maintainable Delivery
Every implementation MUST include clear, documented tradeoffs, architecture review, and an explicit plan for future refinement. Changes that increase complexity MUST be justified in the plan, and code reviews MUST verify adherence to the constitution before merge.

## Architecture Constraints

- The implementation MUST use the existing C#/.NET architecture and favor native dependency injection patterns such as `Microsoft.Extensions.DependencyInjection`.
- All persistence, external integration, and platform-specific behavior MUST be behind explicit abstractions.
- API contracts and service interfaces MUST drive design decisions, not the opposite.
- Non-functional quality goals include maintainability, testability, and observable behavior for API flows.

## Development Workflow

- Every feature MUST be documented with a spec, plan, and task breakdown that references the relevant constitution principles.
- The development cycle MUST follow: define API contract → define tests → implement abstractions → implement concrete behavior → verify coverage and compliance.
- Pull requests MUST include a brief compliance note naming the applicable principles and any coverage impact.
- Exceptions to the constitution MUST be captured in a tradeoff record and reviewed before approval.

## Governance

- This constitution supersedes any conflicting informal practices in the repository.
- Amendments require an explicit proposal, peer review, and a documented migration or compliance plan.
- Versioning policy:
  - MAJOR when a core principle is removed or redefined in a backward-incompatible way.
  - MINOR when a new principle or section is added, or governance guidance is materially expanded.
  - PATCH when wording, clarity, or non-semantic refinements are made.
- Compliance review expectations:
  - All plans and specs MUST include a Constitution Check for API-first, DI, architecture, and coverage goals.
  - All PRs MUST reference at least one principle and record the coverage delta.
  - Coverage below 85% for core API or domain behavior MUST include a remediation plan in the PR description.

**Version**: 1.0.0 | **Ratified**: 2026-04-29 | **Last Amended**: 2026-04-29
