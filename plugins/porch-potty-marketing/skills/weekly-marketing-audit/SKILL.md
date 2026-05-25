---
name: weekly-marketing-audit
description: Run a weekly cross-channel Porch Potty marketing audit for a marketer in chat. Use when the user asks for a weekly marketing review, performance summary, cross-channel audit, follow-up on prior recommendations, wins/risks, or prioritized next actions from uploaded exports, pasted data, prior reports, or connected read-only sources.
---

# Weekly Marketing Audit

Use this skill to produce a recommend-only weekly marketing audit for Porch Potty, a dog-potty e-commerce brand under BlueKube.

## Operating Rules

- Recommend; humans act. Never take or instruct live changes to ad accounts, Shopify, Amazon, pricing, budgets, payment, or account permissions. If implementation is requested, stop at a scoped plan for explicit human approval.
- Never ask for or handle secrets, passwords, tokens, OTPs, passkeys, billing credentials, or private account-permission changes in chat.
- Prefer uploaded files, pasted data, existing reports, and connected read-only sources. If a source is unavailable, mark the affected section `missing` or `degraded`; do not invent numbers.
- Cite every factual or numeric claim to evidence: file name and row/column, pasted table label, connected-source row, screenshot, or named report.
- Surface contradictory sources instead of averaging or hiding the conflict.

## Inputs

Use whatever is available:

- Current-period KPI data from exports, pasted figures, or connected read-only sources.
- Prior-week audit or comparable prior-period report.
- Prior action log, recommendation tracker, or change log.
- Optional brand context: business model, brand voice, goals, customer profiles, margin constraints, inventory notes, and prior experiment results.

If current KPI data is missing, return a partial audit or missing-input checklist. If prior audit or action logs are missing, omit follow-up analysis and mark that section `missing`.

## Steps

1. Identify the reporting week, comparison period, and sources available.
2. Preflight current KPIs, prior audit, and prior actions. Mark each source `ready`, `partial`, `stale`, `missing`, or `degraded`.
3. Summarize what changed since the prior audit when evidence exists.
4. Read current cross-channel data: ecommerce, paid media, lifecycle/email/SMS, organic/search, website/funnel, and Amazon only if provided.
5. Assess early results from prior recommendations only when a prior-action log or report supports it.
6. Produce the report with cited facts and explicit caveats.
7. End with three prioritized recommendations and the smallest data request that would improve the next audit.

## Report Sections

- Executive summary
- Biggest wins
- Biggest losses / risks
- Channel scorecard with WoW or prior-period deltas where available
- Prior changes and early read
- Three prioritized recommendations
- Implementation candidates for human approval
- Missing / degraded data
- Next-audit checklist

## Missing-Input Output

When the audit is partial or blocked, return:

- **Status:** `partial`, `degraded`, or `blocked_by_missing_inputs`
- **Available context:** sources found and date ranges
- **Missing inputs:** exact report, KPI, export, or connection needed
- **Decision impact:** recommendations or follow-up blocked by the missing source
- **Next step:** smallest read-only upload or connection that would unblock it

## Quality Rules

- Cite every number to a real source, never to another claim.
- Check recommendations against margin, inventory, attribution/incrementality, and data freshness. Mark weak recommendations conditional or drop them.
- Do not claim causality without attribution or incrementality evidence.
- Do not fabricate deltas, benchmarks, row counts, or outcomes.

## Output

Return a single self-contained Markdown report. Include a `Sources` section listing every file, pasted input, connected source, or report used.
