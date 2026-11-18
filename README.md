# Order-to-Cash AI Employee

A goal-driven assistant for small shops in Bangladesh. The owner sets a goal, such as "collect
all unpaid dues from last month". The assistant drafts customer reminders for the owner to
review, and the owner approves each one and sends it from their own WhatsApp or SMS. Nothing is
sent, paid or changed without the owner's explicit approval.

Status: in development, not yet used by real shops. The dues-collection flow works end to end on
test data; order import, invoices, stock and the pilot safeguards are still to be built.

## Stack

PostgreSQL 16, Express 5, React 19 (installable PWA), Node 22, with Redis and BullMQ for
background work. JavaScript (ES modules) in a pnpm workspace: `client/`, `server/`, `shared/`.

## Run locally

Requires Node 22, pnpm, PostgreSQL 16 and Redis.

```sh
pnpm install
pnpm test                            # unit, contract, property and integration tests
pnpm --filter @owner/client dev:mock # the app on mock data, no backend needed
pnpm --filter @owner/client e2e      # browser test of the dues scenario
```

Environment variables are listed in `.env.example`.

## Where to start reading

- `AGENTS.md`: working rules for anyone changing this project.
- `specs/001-order-to-cash-agent/handoff.md`: current state, decisions and next steps.
- `specs/001-order-to-cash-agent/spec.md`: what the product must do.
