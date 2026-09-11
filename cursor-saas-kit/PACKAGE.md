# PACKAGE.md — Cursor SaaS Starter Rules

Instructions for packaging the **$29** ZIP sold on Gumroad / Lemon Squeezy (or delivered manually from the waitlist).

---

## What buyers receive

A single archive, suggested name:

```
cursor-saas-starter-rules-v1.zip
```

Contents (paths inside the ZIP):

```
cursor-saas-starter-rules/
  README.md                 ← from product/README.md
  rules/
    nextjs-app-router.mdc
    stripe-webhooks.mdc
    prisma-schema.mdc
    auth-patterns.mdc
    api-route-security.mdc
    testing.mdc
    seo.mdc
    copywriting.mdc
  docs/
    QUICKSTART.md
    WORKFLOWS.md
  LICENSE.txt               ← short buyer license (generate at pack time)
```

Do **not** include this `PACKAGE.md`, internal play notes, or the marketing `landing/` folder in the customer ZIP (landing is public on GitHub Pages).

---

## Build the ZIP (local)

From the play folder:

```bash
cd /workspace/money-maker/plays/01-cursor-saas-kit

STAGE=dist/cursor-saas-starter-rules
rm -rf dist && mkdir -p "$STAGE/rules" "$STAGE/docs"

cp product/README.md "$STAGE/"
cp product/rules/*.mdc "$STAGE/rules/"
cp product/docs/*.md "$STAGE/docs/"

cat > "$STAGE/LICENSE.txt" << 'LIC'
Cursor SaaS Starter Rules — Buyer License
Copyright (c) Diego Marzejon / Tools That Help

You may use these rules and docs in your own projects (personal or commercial).
You may not resell, republish, or redistribute the pack (or substantial portions)
as a competing product or free public mirror.

No warranty. Provided as-is.
LIC

cd dist && zip -r cursor-saas-starter-rules-v1.zip cursor-saas-starter-rules
ls -la cursor-saas-starter-rules-v1.zip
```

Upload that ZIP to Gumroad/Lemon when payment is connected. Price: **$29**.

---

## Waitlist fulfillment (until checkout is live)

1. Buyer emails **toolsthathelp@agentmail.to**.  
2. Collect payment via invoice/link when ready.  
3. Send the ZIP + thank-you note pointing at `docs/QUICKSTART.md`.

---

## Repo layout (public money-kit)

| Path | Purpose |
|------|---------|
| `docs/index.html` or `index.html` | Sales landing (GitHub Pages) |
| `cursor-saas-kit/` | Public mirror of product files + PACKAGE.md |
| `README.md` | Repo index linking products |

GitHub Pages expectation: **https://dmarzejon.github.io/money-kit/**

Enable Pages: Settings → Pages → Deploy from branch `main` → `/docs` (if using `docs/index.html`) or `/ (root)` if using root `index.html`.

---

## Version bumps

When editing rules:

1. Bump a short changelog note in `product/README.md`.  
2. Rebuild ZIP as `cursor-saas-starter-rules-vN.zip`.  
3. Notify waitlist / prior buyers if material fixes (webhooks/auth).
