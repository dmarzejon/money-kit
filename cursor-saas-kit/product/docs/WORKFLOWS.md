# End-to-End Cursor Workflows

Three copy-paste workflows. Use with the included `.mdc` rules active. Adjust names to your schema.

---

## Workflow 1 — Stripe Checkout + Webhook Entitlement

**Goal:** User clicks Upgrade → Stripe Checkout → webhook sets `plan = pro` → gated page unlocks.

### Steps in Cursor

1. **Schema** (with `prisma-schema` rule):  
   > Add Subscription model linked to User with stripeCustomerId, stripeSubscriptionId, status enum, priceId. Create migration.

2. **Checkout Session** (Server Action):  
   > Create a Server Action `createCheckoutSession` that requires auth, ensures Stripe customer, creates Checkout Session in subscription mode with metadata.userId, success/cancel URLs. Use price from env.

3. **Webhook** (`stripe-webhooks` + `api-route-security`):  
   > Implement POST `/api/webhooks/stripe` with raw body signature verify, idempotent event store, handlers for checkout.session.completed and customer.subscription.*.

4. **Gate** (`auth-patterns`):  
   > Add `requirePlan("pro")` helper and protect `/app/export` page.

5. **Test** (`testing`):  
   > Unit-test the status mapper. Document Playwright path: login → upgrade → (mock/fixture webhook) → export visible.

### Done when

- Test-mode payment marks user pro in DB without refreshing from the success page alone.  
- Cancel via Customer Portal sets status correctly on next webhook.

---

## Workflow 2 — Auth + Tenant-Scoped CRUD

**Goal:** Signed-in user can create/list/delete only their own `Project` rows.

### Steps in Cursor

1. **Auth glue** (`auth-patterns`):  
   > Wire session helper `requireUser()`. On first login, upsert Prisma User.

2. **Prisma** (`prisma-schema`):  
   > Project model: id, userId, name, timestamps. Index userId.

3. **Server Actions** (`api-route-security`):  
   > `createProject`, `listProjects`, `deleteProject` — zod validate; always `where: { userId }`.

4. **UI**:  
   > Server Component list + client form calling actions. Empty state CTA.

5. **Test**:  
   > Unit-test that delete with wrong userId returns not found / forbidden. Optional e2e: two users cannot see each other’s projects.

### Done when

- Direct API/action calls with another user’s project id fail closed.  
- No Client Component receives a Prisma client or secrets.

---

## Workflow 3 — Marketing Page → SEO → Waitlist CTA

**Goal:** Ship a landing section that ranks/shares cleanly and captures emails until billing is live.

### Steps in Cursor

1. **Page** (`copywriting` + `nextjs-app-router`):  
   > Build `(marketing)/page.tsx` with headline, 3 benefits, what-you-get list, $29 price, FAQ, CTA mailto or form posting to a Route Handler.

2. **SEO** (`seo`):  
   > Add metadata, OG image, `sitemap.ts`, `robots.ts` disallowing `/app` and `/api`.

3. **Waitlist API** (`api-route-security`):  
   > POST email with zod; rate-limit; store in DB or forward to AgentMail / provider. No public list dump.

4. **Copy pass**:  
   > Tighten headline to persona + outcome; remove hype adjectives.

### Done when

- View-source shows real title/description.  
- CTA goes to **toolsthathelp@agentmail.to** (or your form) until Gumroad/Lemon is live.  
- Lighthouse/basic crawl does not flag `noindex` on the homepage.

---

## Tips

- One workflow per Cursor chat/composer session when possible.  
- `@`-mention the relevant `.mdc` files if globs do not attach.  
- Commit schema + webhook + gate together so prod never bills without entitlement.
