# Projektname: acme-dashboard
# Ziel: Web-Frontend für BI-Daten mit React, Tailwind, Zustand, API-Backend in FastAPI
# Wichtigste Repos:
- github.com/user/acme-dashboard
- github.com/user/acme-backend

## Stack
- Frontend: React, Zustand, Tailwind
- Backend: FastAPI, SQLModel, Alembic, Postgres
- Auth: Auth0
- Deployment: Docker Compose

## Meine Präferenzen
- Code bitte so generieren, dass alles in VSCode direkt läuft (keine veralteten Syntax-Elemente)
- Unittest-Framework: pytest
- Keine Inline-Mocks, stattdessen Fixtures
- Typisierung: Mypy-konform, aber nicht dogmatisch
- Kein Prettier, sondern eslint + custom .eslintrc

## Lokale Entwicklungsumgebung
- MacBook Pro M1, 32GB RAM, macOS 15.3
- Python 3.12 via pyenv, Node 20 via nvm
- VSCode, Cursor, Warp Terminal
- Docker Desktop

## Architektur
- Monorepo mit /frontend und /backend
- Gemeinsames .env Template für Dev/Prod

## Aktuelle Painpoints
- API Schema-Änderungen sorgen regelmäßig für Breaks in den Frontend-Types
- Auth0 Integration im Backend noch fehleranfällig
- Docker Compose mit mehreren Netzwerken (dev/prod) – Abhängigkeiten manchmal unstabil

## Nächste Schritte
- Automatische Generierung von OpenAPI-Types für Frontend
- End-to-End Teststrategie (Cypress oder Playwright?)
