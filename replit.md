# Smart Job Tracker

A responsive job-search workspace for students and job seekers to track applications, interviews, career-preparation demos, and profile preferences.

## Run & Operate

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)

## Where things live

- `artifacts/smart-job-tracker/` — React + Vite frontend for the job-tracking app
- `artifacts/api-server/` — shared API server scaffold; not currently used by the tracker
- `lib/api-spec/` and `lib/api-client-react/` — shared API contract and client generation
- `lib/db/` — shared Drizzle database package

## Architecture decisions

- The tracker is a frontend-first MVP using fictional sample data and an isolated mock API adapter.
- Authentication, durable persistence, and live AI generation are not implemented; assistant responses are explicitly demo output.
- Future server integration should preserve the API boundary and use the shared OpenAPI/client-generation conventions.

## Product

- Dashboard with application metrics, charts, recent applications, and upcoming interviews
- Application management with search, status filtering, sorting, and add/edit/view/delete flows
- Interview tracking, demo-only AI career tools, and profile/settings

## User preferences

- Use a premium, modern SaaS aesthetic with dark navy and off-white, electric-blue accents, subtle gradients, clean typography, rounded cards, and responsive layouts.

## Gotchas

_Populate as you build — sharp edges, "always run X before Y" rules._

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
