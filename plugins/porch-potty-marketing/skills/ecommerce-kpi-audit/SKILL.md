---
name: ecommerce-kpi-audit
description: Audit Porch Potty Shopify, GA4, Search Console, and website KPIs from uploaded exports, pasted data, existing reports, or connected read-only sources. Use when the user asks about revenue, AOV, conversion rate, traffic, product performance, landing pages, checkout, funnel drop-off, CRO, or ecommerce profitability.
---

# Ecommerce KPI Audit

Use this skill for recommend-only Shopify and website KPI analysis for Porch Potty.

## Operating Rules

- Recommend; humans act. Never change or instruct live changes to Shopify, themes, apps, checkout, products, inventory, pricing, discounts, payment, Amazon, budgets, or account permissions. Produce a plan for explicit human approval only.
- Never ask for or handle secrets, passwords, tokens, OTPs, passkeys, or payment credentials in chat.
- Prefer uploaded exports, pasted data, existing reports, and connected read-only sources. If a source is unavailable, mark affected sections `missing` or `degraded`.
- Cite every factual or numeric claim to evidence.
- Surface Shopify/GA4/source disagreements rather than reconciling them silently.

## Inputs

Use whatever data exists for the requested period:

- Shopify: revenue, orders, AOV, conversion rate if available, product sales, refunds/returns, discounts, gross margin, customer type, inventory.
- GA4 / website: sessions, users, source/medium, landing pages, funnel drop-off, checkout behavior, ecommerce events, conversion rate.
- Search Console / SEO: queries, pages, clicks, impressions, CTR, average position when requested.
- Performance/UX: Core Web Vitals, site speed, landing-page notes, screenshots, heatmaps, or test reports if provided.
- Optional brand context: value propositions, product positioning, CRO history, A/B test criteria, customer profiles, margin and inventory constraints.

## Steps

1. Confirm scope, date range, and source freshness.
2. Preflight Shopify revenue truth, GA4/traffic, product data, margin, inventory, attribution, and cohort/repeat-purchase inputs.
3. Build a KPI scorecard only from available evidence.
4. Identify product winners/losers, funnel issues, traffic-source performance, landing-page problems, and conversion opportunities.
5. Estimate lift or profit impact only where the data supports it; otherwise mark recommendations conditional.
6. Provide a recommend-only implementation plan if requested.

## Replenishment / Repeat-Purchase Gate

For replenishment, subscription, repeat-purchase, LTV, payback, or profit-lift claims, require product-order history, cohort/repeat-purchase signals, subscription status where relevant, margin, and inventory context. If any are missing, return:

- **Status:** `blocked_by_missing_inputs` or `partial`
- **Observed facts:** signals actually present
- **Blocked ideas:** ideas that need more data
- **Missing inputs:** exact order, cohort, subscription, margin, or inventory rows needed
- **Next step:** smallest read-only source/report that would unblock it

## Report Sections

- Executive read
- KPI scorecard
- Product winners and losers
- Funnel issues
- Traffic-source performance
- Landing-page performance
- Conversion opportunities
- Implementation plan for human approval
- Evidence and caveats

## Quality Rules

- Cite every number to a real source row.
- Do not estimate revenue, conversion lift, profit lift, or payback without supporting data.
- Check each recommendation against margin, inventory, attribution, implementation effort, and freshness.
- Mark missing Shopify, GA4, margin, inventory, or cohort data clearly.

## Output

Return one self-contained Markdown report with cited evidence and a `Sources` section.
