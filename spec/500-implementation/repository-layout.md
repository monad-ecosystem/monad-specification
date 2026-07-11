# Monad Repository Layout

## Status

Draft

## Version

0.1.0

---

# Abstract

The Monad Repository Layout defines the physical structure of the Monad implementation monorepo.

The layout reflects Monad's domain architecture and enables:

- scalable development
- clear ownership
- automated tooling
- AI-assisted engineering
- long-term maintainability

---

# 1. Repository Root

The repository root represents the complete Monad ecosystem.

Example:

```

monad/

```

---

# 2. Root Structure

```

monad/

├── apps/

├── services/

├── packages/

├── agents/

├── domains/

├── schemas/

├── infrastructure/

├── environments/

├── tooling/

├── tests/

├── examples/

├── docs/

├── governance/

├── security/

├── observability/

├── scripts/

└── .github/

```

---

# 3. Applications

Location:

```

apps/

```

Purpose:

User-facing products.

Example:

```

apps/

├── web-console/

├── admin-console/

├── developer-portal/

└── cli/

```

Applications consume platform services.

They SHOULD NOT contain core domain logic.

---

# 4. Services

Location:

```

services/

```

Purpose:

Backend platform capabilities.

Structure:

```

services/

├── identity/

├── engineering-model/

├── control-plane/

├── policy-engine/

├── automation/

├── event-service/

├── ai-runtime/

├── capability-service/

├── tool-service/

└── integration-service/

```

Each service owns:

```

src/

tests/

docs/

config/

component.yaml

```

---

# 5. Domains

Location:

```

domains/

```

Purpose:

Shared domain definitions.

Contains:

- domain models
- business concepts
- invariants
- specifications

Example:

```

domains/

├── engineering/

├── identity/

├── automation/

├── intelligence/

└── governance/

```

---

# 6. Packages

Location:

```

packages/

```

Purpose:

Reusable libraries.

Example:

```

packages/

├── api-client/

├── event-sdk/

├── telemetry/

├── security/

├── configuration/

├── schemas/

└── testing/

```

Packages MUST remain domain-neutral.

---

# 7. Agents

Location:

```

agents/

```

Purpose:

AI agent implementations.

Example:

```

agents/

├── architect/

├── developer/

├── operations/

├── security/

├── compliance/

└── researcher/

```

Agents contain:

```

agent.yaml

prompts/

tools/

memory/

evaluation/

```

---

# 8. Schemas

Location:

```

schemas/

```

Purpose:

Shared contracts.

Contains:

```

schemas/

├── api/

├── events/

├── domain/

├── agents/

└── policies/

```

Schemas are version controlled.

---

# 9. Infrastructure

Location:

```

infrastructure/

```

Purpose:

Platform infrastructure.

Example:

```

infrastructure/

├── kubernetes/

├── terraform/

├── containers/

├── networking/

└── databases/

```

---

# 10. Environments

Location:

```

environments/

```

Purpose:

Environment definitions.

Example:

```

environments/

├── local/

├── development/

├── staging/

└── production/

```

---

# 11. Governance

Location:

```

governance/

```

Purpose:

Repository governance.

Contains:

- policies
- standards
- ownership
- contribution rules

---

# 12. Security

Location:

```

security/

```

Purpose:

Security controls.

Contains:

- threat models
- security policies
- scanning configuration

---

# 13. Observability

Location:

```

observability/

```

Purpose:

Operational visibility.

Contains:

- dashboards
- alerts
- telemetry configuration

---

# 14. Documentation

Location:

```

docs/

```

Contains:

```

docs/

├── architecture/

├── guides/

├── operations/

├── development/

└── decisions/

```

---

# 15. Component Metadata

Every major component MUST include:

```

component.yaml

````

Example:

```yaml
name: ai-runtime

domain: intelligence

owner: platform-ai

language: python

runtime: container

status: production
````

---

# 16. Dependency Rules

Allowed direction:

```
apps

 ↓

services

 ↓

packages

 ↓

domains
```

Reverse dependencies are discouraged.

---

# 17. Forbidden Patterns

Avoid:

* shared dumping grounds
* circular dependencies
* hidden coupling
* duplicated models

---

# 18. Build Boundaries

Each component SHOULD have:

* independent build process
* independent tests
* clear dependencies

---

# 19. AI Readability

The repository SHOULD expose:

* architecture metadata
* dependency graph
* ownership information
* component intent

AI systems should be able to reason about repository structure.

---

# 20. Repository Layout Principle

The Monad Repository Layout defines:

> A domain-oriented, AI-readable monorepo structure that scales from a small engineering team to a global platform ecosystem.