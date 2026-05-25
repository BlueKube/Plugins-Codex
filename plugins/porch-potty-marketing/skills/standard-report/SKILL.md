---
name: standard-report
description: Generate a named standard Porch Potty marketing report for a marketer in chat, such as weekly scorecard, daily flash, channel summary, ROAS by market, or LTV cohort. Use uploaded exports, pasted data, existing reports, or connected read-only sources; mark unavailable sections missing or degraded.
---

# Standard Report

Use this skill when the user asks for a named Porch Potty standard report, scorecard, channel summary, or recurring marketing readout.

## Operating Rules

- Recommend; humans act. Never take or instruct live changes to ad accounts, Shopify, Amazon, pricing, budgets, payment, or account permissions. If the user asks to act, produce an approval-ready plan only.
- Never ask for or handle secrets in chat.
- Prefer uploaded files, pasted data, existing reports, and connected read-only sources. If a source is unavailable, mark the section `missing` or `degraded`.
- Cite every factual or numeric claim to evidence.
- Surface source disagreements instead of smoothing them over.

## Inputs

Ask for the report name when it is missing or ambiguous. Depending on the report, use:

- Ecommerce KPIs: revenue, orders, AOV, conversion rate, traffic, refunds, discounts, gross margin where available.
- Paid media KPIs: spend, purchases, revenue/conversion value, ROAS, CAC/CPA, CTR, CPC, CPM, CVR, campaign/ad/creative dimensions.
- Lifecycle or retention exports when requested: email/SMS revenue, sends, opens, clicks, unsubscribes, cohorts, repeat purchase.
- Prior-period data for deltas.
- Optional brand context and prior reports.

## Source Unblocking Workflow

Before declaring a report section blocked, work through every safe option:

1. Check current files, pasted data, existing reports, and connected read-only sources.
2. Check whether a relevant built-in Codex plugin is installed and usable. For example, use Google Drive or Spreadsheets for Drive/Sheets exports and reports; use browser/Chrome only when the user explicitly approves visible account access.
3. If a useful built-in plugin is not installed or connected, tell the user exactly which Codex plugin or connector to install/connect and why. Do not claim unavailable Shopify, GA4, ads, Klaviyo, Amazon, or Search Console access.
4. Offer the export fallback: ask for the smallest CSV/XLSX/PDF/screenshot/pasted table that unlocks the requested report.
5. Offer visible-browser/OAuth fallback only after explaining the read-only goal and getting human approval. The human completes login, MFA, OAuth consent, account selection, and export/download clicks. Stop at credentials, billing, permissions, payment, settings changes, PII, or live-change boundaries.
6. If no route is available, mark the section `missing` or `degraded` and continue with supported sections only.

Include a short `Source access attempted` note when the report is partial.

## Steps

1. Resolve the report name or ask a concise clarification if multiple reports match.
2. Preflight required sources. For missing sources, run the Source Unblocking Workflow before marking each `ready`, `partial`, `stale`, `missing`, or `degraded`.
3. Use a bundled definition if one exists later; otherwise use the common structures below.
4. Build only the rows and sections supported by evidence.
5. Add caveats for missing context that affects interpretation.
6. End with cited recommendations only when the report supports them.

## Common Report Types

- **weekly-scorecard:** headline KPIs versus prior week by channel.
- **daily-flash:** yesterday or latest-day revenue, orders, spend, efficiency, and anomalies.
- **channel-summary:** performance by channel with wins, risks, and next actions.
- **roas-by-market:** spend, revenue/conversion value, ROAS/MER by region where source data supports it.
- **ltv-cohort:** cohort revenue, repeat purchase, payback, and retention only when cohort data is present.

## Missing-Input Output

If the requested report cannot run cleanly, return:

- **Status:** `partial`, `degraded`, or `blocked_by_missing_inputs`
- **Runnable sections:** sections that can be produced now
- **Missing sections:** sections blocked by missing source data
- **Needed upload/connection:** smallest built-in plugin/connector, export, pasted table, report, or approved visible-browser/OAuth path needed
- **Decision impact:** what cannot be recommended until the data arrives

## Quality Rules

- Cite every number to a real source row, named report, or pasted input.
- Do not invent rows for unavailable sources.
- Mark recommendations conditional when margin, inventory, attribution/incrementality, or freshness context is missing.
- End every report with `Sources:`.

## Output

Return one self-contained Markdown report in the requested report format.
