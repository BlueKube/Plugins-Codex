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

## Source Connection Reference

When source access, first-run setup, missing connections, MCP routes, or team onboarding matters, read `../../references/source-connections.md` and follow its source map. Prefer built-in Codex routes visible in the current session before recommending exports, official/vendor MCPs, or approved browser/OAuth paths.

## Inputs

Use whatever data exists for the requested period:

- Shopify: revenue, orders, AOV, conversion rate if available, product sales, refunds/returns, discounts, gross margin, customer type, inventory.
- GA4 / website: sessions, users, source/medium, landing pages, funnel drop-off, checkout behavior, ecommerce events, conversion rate.
- Search Console / SEO: queries, pages, clicks, impressions, CTR, average position when requested.
- Performance/UX: Core Web Vitals, site speed, landing-page notes, screenshots, heatmaps, or test reports if provided.
- Optional brand context: value propositions, product positioning, CRO history, A/B test criteria, customer profiles, margin and inventory constraints.

## Source Unblocking Workflow

Before declaring ecommerce data blocked, work through every safe option:

1. Check current files, pasted data, existing reports, and connected read-only sources.
2. Check whether a relevant built-in Codex plugin is installed and usable. Use Google Drive/Sheets/Spreadsheets for shared exports and reports; use Supabase only for intended KPI memory; use browser/Chrome only when the user explicitly approves visible account access.
3. If a useful built-in plugin is not installed or connected, tell the user exactly which Codex plugin or connector to install/connect and why.
4. If no native Codex route exists, recommend a BlueKube-approved official/vendor MCP route where one is known, or state that no approved connector is visible. For ecommerce, this may include GA4 MCP for traffic, but Shopify commerce truth should come from approved Shopify exports/reports or approved store-data access.
5. Offer the export fallback: ask for the smallest Shopify, GA4, Search Console, website, or product report export that unlocks the blocked section.
6. Offer visible-browser/OAuth fallback only after explaining the read-only goal and getting human approval. The human completes login, MFA, OAuth consent, account selection, and export/download clicks. Stop at credentials, billing, permissions, payment, settings changes, PII, or live-change boundaries.
7. If no route is available, mark the affected section `missing` or `degraded` and continue with supported sections only.

Include the attempted source path and remaining blocker in evidence and caveats.

## Steps

1. Confirm scope, date range, and source freshness.
2. Preflight Shopify revenue truth, GA4/traffic, product data, margin, inventory, attribution, and cohort/repeat-purchase inputs. For missing inputs, run the Source Unblocking Workflow.
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
- **Next step:** smallest built-in plugin/connector, read-only source/report, upload, pasted table, or approved visible-browser/OAuth path that would unblock it

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
