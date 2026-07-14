# Resume Builder

A self-hosted instance of [Reactive Resume](https://github.com/amruthpillai/reactive-resume) — a free, open-source resume builder.

## Stack

- **Web** — TanStack Start / React / Vite (`apps/web`)
- **API** — Hono / Node.js (`apps/server`)
- **Database** — PostgreSQL (local or [Supabase](https://supabase.com))

## Prerequisites

- Node.js 24
- pnpm 11 (`corepack enable`)
- PostgreSQL (or a Supabase project)

## Setup

```bash
cp .env.example .env.local
```

Set at least:

| Variable | Example |
| --- | --- |
| `APP_URL` | `http://localhost:3000` |
| `DATABASE_URL` | `postgresql://postgres:PASSWORD@HOST:5432/postgres` |
| `AUTH_SECRET` | any long random string (`openssl rand -hex 32`) |

Comment out the `S3_*` variables in `.env.local` to use local filesystem storage under `./data`.

```bash
pnpm install
dotenvx run -f .env.local -- pnpm db:migrate
dotenvx run -f .env.local -- pnpm dev
```

Open [http://localhost:3000](http://localhost:3000).

## Scripts

| Command | Description |
| --- | --- |
| `pnpm dev` | Start web + API |
| `pnpm db:migrate` | Apply database migrations |
| `pnpm build` | Production build |

## License

MIT — based on [Reactive Resume](https://github.com/amruthpillai/reactive-resume) by Amruth Pillai.
