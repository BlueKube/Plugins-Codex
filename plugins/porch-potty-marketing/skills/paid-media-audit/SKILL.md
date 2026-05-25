---
name: paid-media-audit
description: Audit Porch Potty paid media performance for Meta, TikTok, Google, YouTube, Pinterest, Amazon Ads, or other ad platforms. Use when the user provides exports or connected read-only ad data and wants spend, ROAS/CAC, waste, creative fatigue, structure, budget allocation, or test recommendations.
---

# Paid Media Audit

Use this skill for recommend-only paid media analysis for Porch Potty.

## Operating Rules

- Recommend; humans act. Never change or instruct live changes to bids, budgets, campaigns, ads, creatives, conversion events, targeting, exclusions, placements, pricing, payment, or account permissions. Produce an approval-ready plan only.
- Never ask for or handle secrets, passwords, tokens, OTPs, passkeys, or billing details in chat.
- Prefer uploaded exports, pasted data, existing reports, and connected read-only sources. If data is absent, mark affected findings `missing` or `degraded`.
- Cite every factual or numeric claim to evidence.
- Do not make final scale or budget-increase recommendations without margin, inventory, attribution/incrementality, and data freshness context.

## Inputs

Use any paid media export or read-only source for the review period:

- Spend, revenue/conversion value, purchases/leads/conversions, CPA/CAC, ROAS, MER, CTR, CPC, CPM, CVR.
- Campaign, ad set/ad group, ad, creative, audience, placement, search term, product group, and budget pacing data.
- Learning status, delivery constraints, attribution window, conversion action, and account structure where available.
- Optional brand context: voice, value propositions, customer profiles, prior paid-media tests, margin, inventory, and competitor notes.

If required data is missing, ask for the smallest read-only export that unblocks the question.

## Steps

1. Confirm platform, date range, comparison period, and source freshness.
2. Preflight performance, structure, creative, budget, margin, inventory, and attribution/incrementality inputs.
3. Summarize KPI performance and source caveats.
4. Identify waste: low-return spend concentration, fatigued creative, irrelevant search terms, poor placements, weak conversion paths, or delivery constraints.
5. Identify winners and scale candidates, but gate scale behind profitability, inventory, and attribution/incrementality evidence.
6. Produce recommendations grouped as high-confidence actions, tests, and open questions.
7. If implementation is requested, provide a human-approved execution plan only.

## Channel Notes

- **Meta:** objective, attribution setting, Advantage+ settings, frequency, creative fatigue, hook/hold metrics, prospecting versus retargeting.
- **TikTok:** thumb-stop/hook rate, CTR, CVR, creative spend concentration, fatigue, comment sentiment if provided.
- **Google / YouTube:** brand versus non-brand, search terms, match types, negatives, Shopping/PMax assets and product groups, network waste, impression share.
- **Amazon Ads:** campaign/target/search-term performance, advertised-product performance, placement performance, ACOS/TACOS if available.

## Scale Gate

If a campaign looks scalable but context is missing, return:

- **Status:** `blocked_by_missing_inputs`
- **Blocked campaigns:** campaigns that otherwise look like scale candidates
- **Missing inputs:** exact margin, inventory, conversion, attribution, incrementality, or new-customer data needed
- **Decision impact:** why scale is blocked
- **Next step:** smallest read-only source or upload that would unblock it

## Quality Rules

- Cite every number to a real source row.
- Do not claim incrementality from platform ROAS alone.
- Surface contradictions across sources or attribution windows.
- Check each recommendation against margin, inventory, attribution/incrementality, and freshness.

## Output

Return one self-contained Markdown report with: scope/date range, KPI snapshot, waste, winners, creative/structure read, high-confidence recommendations, tests, open questions, missing-data requests, and `Sources`.
