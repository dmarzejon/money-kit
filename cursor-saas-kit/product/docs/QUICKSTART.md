# Quickstart — Cursor SaaS Starter Rules

**Time:** ~10 minutes · **Requires:** Cursor IDE + a Next.js (App Router) project

---

## 1. Unzip the pack

You should see:

```
product/
  README.md
  rules/*.mdc
  docs/QUICKSTART.md
  docs/WORKFLOWS.md
```

## 2. Install rules into Cursor

From your SaaS repo root:

```bash
mkdir -p .cursor/rules
cp /path/to/product/rules/*.mdc .cursor/rules/
```

Confirm in Cursor: **Settings → Rules** (or the `.cursor/rules` folder in the file tree). Rules with `globs` activate when matching files are in context; you can also `@`-mention a rule in chat.

## 3. Project prerequisites (recommended)

- Next.js 14+ with App Router  
- TypeScript  
- Prisma + Postgres (or compatible)  
- Stripe account (test mode is fine)  
- Auth provider (Auth.js, Clerk, or similar)

If you are greenfield, scaffold with `create-next-app` (App Router + TS + ESLint), then add Prisma and Stripe.

## 4. Env checklist

```bash
# .env.local (never commit)
DATABASE_URL=
STRIPE_SECRET_KEY=
STRIPE_WEBHOOK_SECRET=
STRIPE_PRICE_PRO=          # price_...
NEXTAUTH_SECRET=           # or provider-specific secrets
NEXTAUTH_URL=http://localhost:3000
```

## 5. First prompt to try

Open a relevant file (e.g. `app/api/webhooks/stripe/route.ts` or create it), then in Cursor chat:

> Using our Stripe webhooks and Prisma rules, implement a verified webhook handler that upserts subscription status for the authenticated user id in metadata. Include idempotency on event.id.

## 6. Next

Run one of the three end-to-end flows in [WORKFLOWS.md](./WORKFLOWS.md).

## Support

toolsthathelp@agentmail.to
