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

## Source Connection Reference

When source access, first-run setup, missing connections, MCP routes, or team onboarding matters, read `../../references/source-connections.md` and follow its source map. Prefer built-in Codex routes visible in the current session before recommending exports, official/vendor MCPs, or approved browser/OAuth paths.

## Inputs

Use any paid media export or read-only source for the review period:

- Spend, revenue/conversion value, purchases/leads/conversions, CPA/CAC, ROAS, MER, CTR, CPC, CPM, CVR.
- Campaign, ad set/ad group, ad, creative, audience, placement, search term, product group, and budget pacing data.
- Learning status, delivery constraints, attribution window, conversion action, and account structure where available.
- Optional brand context: voice, value propositions, customer profiles, prior paid-media tests, margin, inventory, and competitor notes.

If required data is missing, ask for the smallest read-only export that unblocks the question.

## Source Unblocking Workflow

Before declaring paid media data blocked, work through every safe option:

1. Check current files, pasted data, existing reports, and connected read-only sources.
2. Check whether a relevant built-in Codex plugin is installed and usable. Use Google Drive/Sheets/Spreadsheets for shared exports and reports; use browser/Chrome only when the user explicitly approves visible account access.
3. If a useful built-in plugin is not installed or connected, tell the user exactly which Codex plugin or connector to install/connect and why.
4. If no native Codex route exists, recommend a BlueKube-approved official/vendor MCP route where one is known, or state that no approved connector is visible. For paid media, this may include Google Ads MCP, Amazon Ads MCP, Klaviyo/Triple Whale for supporting data, or approved Meta/TikTok routes.
5. Offer the export fallback: ask for the smallest platform export that unlocks the audit, such as campaign/ad/ad set performance, search terms, creative performance, or placement/network data.
6. Offer visible-browser/OAuth fallback only after explaining the read-only goal and getting human approval. The human completes login, MFA, OAuth consent, account selection, and export/download clicks. Stop at credentials, billing, permissions, payment, settings changes, PII, or live-change boundaries.
7. If no route is available, mark the affected analysis `missing` or `degraded` and continue with supported sections only.

Include the attempted source path and remaining blocker in missing-data requests.

## Steps

1. Confirm platform, date range, comparison period, and source freshness.
2. Preflight performance, structure, creative, budget, margin, inventory, and attribution/incrementality inputs. For missing inputs, run the Source Unblocking Workflow.
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
- **Next step:** smallest built-in plugin/connector, read-only source, upload, pasted table, or approved visible-browser/OAuth path that would unblock it

## Quality Rules

- Cite every number to a real source row.
- Do not claim incrementality from platform ROAS alone.
- Surface contradictions across sources or attribution windows.
- Check each recommendation against margin, inventory, attribution/incrementality, and freshness.

## Output

Return one self-contained Markdown report with: scope/date range, KPI snapshot, waste, winners, creative/structure read, high-confidence recommendations, tests, open questions, missing-data requests, and `Sources`.
