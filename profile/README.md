# Aceituna-CICD

**Aceituna-CICD** is an artifact version tracking tool for CI/CD pipelines. It records which version of each component was built and where it was deployed, giving teams a single source of truth across their delivery chain.

---

## What it does

When a pipeline builds an artifact, it registers it with Aceituna. When a deployment runs, it records which artifact version landed on which environment. From that point, anyone can answer questions like:

- What is deployed on production right now?
- Which environments have version `2.1.0` of `api-service`?
- What was the deployment history of this artifact?

---

## Repositories

| Repository | Description | Status |
|---|---|---|
| [Aceituna-cicd-backend](https://github.com/Aceituna-cicd/Aceituna-cicd-backend) | Go REST API — artifact tracking, deployments, projects, environments, users | ✅ Active |
| [Aceituna-cicd-frontend](https://github.com/Aceituna-cicd/Aceituna-cicd-frontend) | Vue 3 SPA — dashboard, artefact/environment/project views, admin panel | ✅ Active |
| [Aceituna-cicd-docs](https://github.com/Aceituna-cicd/Aceituna-cicd-docs) | Public documentation (English) | ✅ Active |
| [Aceituna-cicd-specs](https://github.com/Aceituna-cicd/Aceituna-cicd-specs) | Project specifications (French) | ✅ Active |

---

## Current state

The **backend** is feature-complete: all CRUD resources, authentication (JWT + API tokens), RBAC, aggregated read-only views, Vue SPA serving (`server/static.go`), Docker, structured logging, Swagger docs, and 90%+ test coverage across all packages.

The **frontend** is fully implemented: all views (Dashboard, Artefact, Environment, Project, Admin panel), authentication flow (login/logout, JWT in Pinia), i18n EN+FR with language switcher, WCAG 2.1 AA, and 200+ Vitest unit tests. Playwright E2E tests are the remaining planned item.

---

## Tech stack

| Layer | Technology |
|---|---|
| Backend | Go 1.25 · Gin · GORM · zerolog · Viper |
| Database | SQLite (default) · PostgreSQL (planned) |
| API docs | Swagger UI (swaggo) |
| Frontend | Vue 3 · Vite · TypeScript · Pinia · vue-i18n |
| Container | Docker multi-stage build |

---

## Project board

All tasks are tracked on the [GitHub kanban board](https://github.com/orgs/Aceituna-cicd/projects/1).

Documentation is available at [Aceituna-cicd-docs](https://github.com/Aceituna-cicd/Aceituna-cicd-docs).
