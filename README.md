# smolla-identity-provider

Centralised OAuth2/OIDC identity provider and user management platform built on ASP.NET Core, OpenIddict, and EF Core. Includes a management API and Vue 3 admin frontend.

## Repository layout

```
backend/
    src/Smolla.IdentityProvider.Domain/         Domain entities and value objects
    src/Smolla.IdentityProvider.Application/    Application services and abstractions
    src/Smolla.IdentityProvider.Infrastructure/ EF Core, OpenIddict, identity stores
    src/Smolla.IdentityProvider.Api/            Controllers (users, clients, health, version)
    src/Smolla.IdentityProvider.Host/           ASP.NET Core composition root
    tests/                                      xUnit unit + integration tests
frontend/                                       Vue 3 + TypeScript admin UI
```

## Local development

```
# Backend
cd backend
dotnet restore && dotnet build && dotnet test
dotnet run --project src/Smolla.IdentityProvider.Host

# Frontend (separate terminal)
cd frontend
npm install
npm run dev
```

## Workflows

- `ci.yml` — runs on every push and PR
- `deploy-prod.yml` — runs on push to `main`
- `deploy-staging.yml` — runs on push to `develop`
- `deploy-test.yml` — manual dispatch for shared test slot
- `release-please.yml` — opens release PRs based on conventional commits
- `sync-main-to-develop.yml` — back-merges hotfixes from `main` into `develop`

## Versioning

Managed by `release-please`; the canonical version lives in `version.txt` and is propagated to project files on each release.

## Licence

GNU Affero General Public License v3.0 — see [LICENSE](LICENSE).

Copyright (c) 2026 Adam Salisbury.
