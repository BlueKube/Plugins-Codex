---
name: check-what-i-can-run
description: Inspect the current chat, uploaded files, pasted data, existing reports, and connected read-only sources to tell the user which Porch Potty marketing reports are runnable now, degraded, or blocked. Use before audits, standard reports, budget decisions, scale decisions, or when the user asks what can be run.
---

# Check What I Can Run

Use this readiness preflight before producing or trusting Porch Potty marketing reports.

## Operating Rules

- Recommend; humans act. Do not take or instruct live changes to ad accounts, Shopify, Amazon, pricing, budgets, payment, or account permissions.
- Never ask for or handle secrets in chat.
- Prefer uploaded files, pasted data, existing reports, and connected read-only sources.
- Do not browse account UIs or use a browser unless the user explicitly asks for visible browser verification. Stop at credentials, OTPs, billing, settings changes, PII, or any live-change boundary.
- Every readiness claim must cite the file, pasted input, connected source, or visible context used.

## Sources To Inspect

Assess what the current session can reach, in this order:

1. Uploaded exports and files in the conversation or workspace.
2. Pasted data, screenshots, or named reports in chat.
3. Connected read-only sources the user has made available.
4. Stored KPI/report history if the current session has one.
5. Optional visible-browser verification only when explicitly requested.

Do not ask for credentials. For any missing source, name the smallest upload, export, report, or read-only connection needed.

## Steps

1. Identify requested report(s) or assess all plugin reports if none are named.
2. Inventory sources by type: Shopify/ecommerce, GA4/website, paid media, lifecycle/email/SMS, Amazon, margin, inventory, cohort/LTV, prior reports, action logs.
3. For each source, record access method, date range, freshness, fields available, and caveats.
4. Decide which reports are runnable now, runnable degraded, or blocked.
5. Apply the gating rules below.
6. Return a concise readiness matrix and next fetch recommendation.

## Per-Source Readout

For every source in scope, report:

- **Source** and **role** such as Shopify = revenue truth, GA4 = traffic/funnel, ad platform = spend/return.
- **Status:** `ready`, `ready_with_caveats`, `partial`, `stale`, `missing_data`, `missing_credentials`, `needs_browser_verification`, or `not_configured`.
- **Access method:** connector, upload, pasted data, named report, or browser.
- **Date range** and freshness.
- **Missing fields** and the smallest next step.
- **Evidence citation** for the readiness claim.

## Top-Level Decision

Return:

- **decision:** `proceed_clean`, `proceed_with_warnings`, `partial_only`, or `halt`
- **reportAllowed / recommendationsAllowed / budgetIncreaseAllowed:** booleans
- **ready sources / caveat sources / blocked sources**
- **missing inputs**
- **blocked outputs**
- **next fetch**

## Gating Rules

- Missing Shopify or another credible revenue truth blocks revenue, order, conversion, and incrementality reports.
- Missing margin blocks scale, profit, CAC/LTV, payback, and contribution recommendations.
- Missing inventory blocks scale, promotion, replenishment, or launch recommendations.
- Missing attribution/incrementality blocks budget reallocations and causal-impact claims.
- Missing cohort data blocks realized-LTV and payback claims.
- Missing prior audit/action log degrades follow-up on prior recommendations.
- Contradictory rows across sources must be flagged; do not average them.

## Report Readiness Map

Assess these skills:

- `weekly-marketing-audit`
- `standard-report`
- `paid-media-audit`
- `ecommerce-kpi-audit`

For each, mark `ready`, `ready_with_caveats`, `degraded`, or `blocked`, then list the exact evidence and missing inputs.

## Output

Return a concise Markdown readiness report with a matrix, top-level decision, report-by-report status, missing inputs, next fetch, and `Sources`.
