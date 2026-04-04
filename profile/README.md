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
| [Aceituna-cicd-frontend](https://github.com/Aceituna-cicd/Aceituna-cicd-frontend) | Vue 3 SPA — dashboard and management UI | 🔧 Planned |
| [Aceituna-cicd-docs](https://github.com/Aceituna-cicd/Aceituna-cicd-docs) | Public documentation (English) | ✅ Active |
| [Aceituna-cicd-specs](https://github.com/Aceituna-cicd/Aceituna-cicd-specs) | Project specifications (French) | ✅ Active |

---

## Current state

The **backend** is the active focus. Core data management is fully operational:

- **Artifacts** — register builds, track `(project, name, version)` uniqueness, update build metadata
- **Projects** — group artifacts, manage per-user access
- **Environments** — explicit creation, per-user access, deployment blocking on deletion
- **Deployments** — record `success` / `failed` / `in_progress` status, full history with soft-delete
- **Users** — role-based (`admin` / `standard`), bcrypt passwords, last-admin guard
- **Access management** — grant/revoke per-user access to projects and environments

**In progress:** authentication middleware (JWT and API token modes), RBAC enforcement, aggregated read-only views.

**Not yet started:** Vue 3 frontend.

---

## Tech stack

| Layer | Technology |
|---|---|
| Backend | Go 1.25 · Gin · GORM · zerolog · Viper |
| Database | SQLite (default) · PostgreSQL (planned) |
| API docs | Swagger UI (swaggo) |
| Frontend | Vue 3 · Vite · TypeScript · Pinia · vue-i18n *(planned)* |
| Container | Docker multi-stage build |

---

## Project board

All tasks are tracked on the [GitHub kanban board](https://github.com/orgs/Aceituna-cicd/projects/1).

Documentation is available at [Aceituna-cicd-docs](https://github.com/Aceituna-cicd/Aceituna-cicd-docs).
