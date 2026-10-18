# cosori-headless-storefront

**Purpose**: Headless e-commerce storefront built on modern cloud infrastructure. Decouples the product catalog and backend from the customer-facing web interface, enabling multi-channel support and rapid iteration on frontend experiences.

**Stack**: Next.js 14+ (App Router, TypeScript strict), Supabase (PostgreSQL + auth), Tailwind CSS + shadcn/ui, Vercel deployment.

**Key commands** (from package.json): [review package.json for install / dev / build / test / lint scripts]

**Key directories**: `src/` (Next.js app), `public/` (static assets), `lib/` (utilities & API clients), `components/` (React components), `.env.local` (secrets, never commit).

**Conventions**: Commit messages follow `<type>: <description>` (feat/fix/refactor/docs/test/chore). TypeScript strict mode. Tailwind + shadcn/ui for all UI. Supabase environment refs and keys in `.env.local` only.

**Guardrails**:
- Always work on a branch in a git worktree: `~/Projects/.worktrees/cosori-headless-storefront/<branch>`
- Production deploys only via PR → Vercel preview → Barron approves merge
- Never push directly to `main`; never run `vercel --prod`
- Never modify `NEXT_PUBLIC_SUPABASE_*` env vars (database connection is immutable)
- Secrets only in local `chmod 600` files; never hardcode or commit
- No deletion or archival of features without explicit approval

## Shared agent memory (all tools)
- Global rules: `~/Projects/_brain/GLOBAL-AGENTS.md`; project registry: `~/Projects/_brain/projects.yaml`.
- Current state and next steps: `docs/STATUS.md`. Update it at the end of every session.
- Main clone `~/Projects/cosori-headless-storefront` stays on main and clean; do work in `git worktree add ~/Projects/.worktrees/cosori-headless-storefront/<branch> -b <branch>`.
