# Contributing to Nexo

Thanks for your interest! Nexo is a personal project, but PRs from invited collaborators and occasional outside contributions are welcome.

## Prerequisites

- Node.js (see `.node-version`)
- pnpm (`corepack enable`)
- Docker (for the local database)

## Getting started

```bash
git clone https://github.com/nexo-suite/nexo
cd nexo
pnpm install
cp .env.example .env   # fill in OAuth credentials + secrets
pnpm docker:db         # start local Postgres
pnpm db:migrate        # run migrations
pnpm dev               # start all apps
```

See [Local Development](docs/local-development.md) for the full walkthrough including OAuth app setup.

## Making changes

1. Create a branch from `main`
2. Make your changes
3. Run `pnpm qc` — this is the same gate CI enforces:
   ```bash
   pnpm qc   # sort, format, sync, knip, lint, type:check, build, test
   ```
4. Open a PR against `main`

## Commit style

This project uses [Conventional Commits](https://www.conventionalcommits.org/) — release-please reads them to generate changelogs and version bumps.

```
feat(finance): add CSV export
fix(auth): handle expired session on refresh
chore(deps): update drizzle-orm to 0.40
```

## PR checklist

- `pnpm qc` passes
- No secrets or env values committed
- DB schema changes include a migration (`pnpm db:generate`)
- Dockerfile changes tested locally

## Questions?

Open a [Discussion](https://github.com/nexo-suite/nexo/discussions) — bugs go in [Issues](https://github.com/nexo-suite/nexo/issues).
