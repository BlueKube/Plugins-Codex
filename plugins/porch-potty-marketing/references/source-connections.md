# Porch Potty Source Connections

Use this reference when a Porch Potty marketing skill needs to decide how to get data for a teammate after the plugin is installed.

## Connection Rules

- Prefer sources the teammate already has connected in Codex: uploaded files, pasted data, Google Drive, Sheets, Spreadsheets, Supabase, or other visible read-only tools.
- Prefer the shared Porch Potty / BlueKube Google Drive evidence layer for team consistency. Use live platform connections only when they add fresher or more complete data.
- Do not ask for secrets, passwords, tokens, OTPs, API keys, passkeys, billing credentials, or permission changes in chat.
- Do not configure third-party MCP servers from arbitrary search results. Prefer built-in Codex plugins first, then official/vendor MCPs, then BlueKube-approved MCPs, then exports.
- If a connector exposes write tools, use only read/report/list/get/search tools. Never call mutate, create, update, delete, pause, publish, budget, bid, billing, permission, or payment tools.
- If setup needs OAuth, login, MFA, account selection, browser export, or app approval, ask for explicit human approval and let the human complete those steps.
- If no safe route exists, mark the source `missing` or `degraded` and continue with supported sections.

## First-Run Flow

When a teammate runs any Porch Potty marketing skill and sources are missing:

1. Check current chat files, pasted data, screenshots, and named reports.
2. Check available Codex tools/plugins. Use tool discovery when available.
3. Test Google Drive first when available: get the profile, list shared drives if useful, and search for `Porch Potty`, the requested date range, `weekly-scorecard`, `shopify`, `ga4`, `google ads`, `meta ads`, `source-gap`, and `CURRENT_CONTEXT`.
4. Check Spreadsheets/Google Sheets exports if available.
5. Check Supabase only when the user expects BlueKube KPI memory/source-run rows and the Supabase connector is installed and connected.
6. For each missing source, recommend the best route in this order:
   - built-in Codex plugin/connector already installed and connected;
   - built-in Codex plugin/connector to install/connect;
   - official/vendor MCP or BlueKube-approved MCP setup outside chat;
   - smallest export/upload/pasted table;
   - approved visible-browser/OAuth export;
   - mark `missing` or `degraded`.
7. Return a readiness matrix before running a full report when source coverage is weak.

## Current Codex Built-In Routes

These are the safe built-in routes to prefer when visible in the current Codex session:

| Source need | Built-in route | Use for | Notes |
|---|---|---|---|
| Shared reports, exports, Docs, Sheets, Slides | Google Drive plugin / Google Sheets skill | Team evidence layer, weekly packets, source-gap reports, uploaded exports stored in Drive | Best first route for all teammates with shared folder access. |
| Local CSV/XLSX analysis | Spreadsheets plugin | Uploaded exports, local workbooks, normalized data | Use for deterministic spreadsheet reads and summaries. |
| Browser-only account checks | Browser or Chrome plugin | Visible account UI checks or exports | Use only with explicit human approval. Human handles login, MFA, OAuth, and export clicks. |
| KPI memory / warehouse rows | Supabase plugin | BlueKube source-runs, normalized KPI tables, report memory | Use only if installed, connected, and intended for this report. Never ask for database credentials in chat. |
| Prior action context | Google Drive, Slack plugin | Prior recommendations, action logs, approvals, discussion context | Use read-only search/fetch where available. |

Do not claim a native Codex source plugin exists unless it is visible in the active session.

## Platform Source Map

| Platform/source | Best route for team members | Fallback route | Blocks when missing | Setup notes |
|---|---|---|---|---|
| Shopify commerce | Shared Drive/Sheets Shopify exports or existing Shopify weekly digest | Approved visible Shopify export, or BlueKube-approved read-only Admin API/MCP | Revenue truth, orders, AOV, product sales, returns, discounts | Shopify AI Toolkit/Dev MCP is useful for docs/API/schema/dev work, but do not treat it as store reporting truth unless BlueKube has approved a store-data connector. |
| GA4 | Official Google Analytics MCP if installed/configured, or Drive/Sheets GA4 exports | Approved GA4 browser/OAuth export | Traffic, acquisition, landing pages, funnel diagnostics | Google says its GA MCP server is read-only. Still cite all queried rows and avoid settings changes. |
| Google Search Console | Drive/Sheets GSC exports or Search Console API/report export | Approved browser/OAuth export | SEO query/page reads, clicks, impressions, CTR, position | No native Codex/GSC route should be assumed. Do not use unapproved third-party MCPs. |
| Google Ads | Official `googleads/google-ads-mcp` or Drive/Sheets exports | Approved browser export from Google Ads | Spend, ROAS/CAC, campaign/search-term/PMax diagnostics | Requires Google Ads API/OAuth/developer-token setup outside chat. Treat as admin setup; never request tokens in chat. Use read/report queries only. |
| Meta Ads | BlueKube-approved official/vendor Meta Ads MCP if available, or Drive/Sheets exports | Approved browser export from Meta Ads Manager | Spend, ROAS/CAC, creative/ad set/campaign diagnostics | Meta MCP availability and scopes can vary. Verify current connector availability and use reporting only. |
| TikTok Ads | Drive/Sheets exports or BlueKube-approved TikTok Ads MCP/API route | Approved browser export | Spend, ROAS/CAC, creative diagnostics | Do not assume a native Codex connector. Verify any MCP/vendor route before recommending it. |
| Amazon Ads | Official Amazon Ads MCP open beta if BlueKube has approved API access, or exports | Approved browser export | Amazon Ads spend, sales, ACOS/TACOS, campaign/target diagnostics | Partner/API credentials and profiles are admin-controlled; no secrets in chat. |
| Amazon Seller Central | Seller Central exports or approved SP-API/report route | Approved browser export | Amazon marketplace sales, units, fees, inventory, returns | SP-API setup is developer/admin-controlled and may include restricted data. Keep PII out of reports unless explicitly allowed and necessary. |
| Klaviyo / lifecycle | Official Klaviyo remote MCP with `read-only=true` when configured, or exports | Campaign/flow CSV, Drive/Sheets report, approved browser export | Email/SMS revenue, campaign/flow performance, deliverability | Prefer `https://mcp.klaviyo.com/mcp?read-only=true&disable-tools-with-user-generated-content=true` when BlueKube approves MCP use. |
| Triple Whale / Moby | Triple Whale Moby MCP if approved, or exported reports | Drive/Sheets report, approved browser export | Blended attribution, MER, contribution context | API-key setup must happen outside chat by a human/admin. |
| Margin / unit economics | Finance/ops sheet or report in Drive/Sheets | Pasted table from finance owner | Profit, CAC/LTV, payback, scale, discount recommendations | Missing margin blocks scale and profit claims. |
| Inventory | Ops/inventory sheet or report in Drive/Sheets | Pasted table from ops owner | Scale, promo, SKU recommendations | Missing inventory blocks scale/promo recommendations. |
| Prior changes/action log | Drive report, Slack context, pasted tracker | Human summary | Follow-up on prior recommendations | If absent, mark prior-action read `missing`. |

## Official/Vendor References To Cite In Setup Advice

- Google Analytics MCP: https://developers.google.com/analytics/devguides/MCP
- Google Ads MCP: https://github.com/googleads/google-ads-mcp
- Amazon Ads MCP: https://advertising.amazon.com/en-us/library/news/amazon-ads-mcp-server-open-beta/
- Klaviyo MCP: https://developers.klaviyo.com/en/docs/klaviyo_mcp_server
- Triple Whale Moby MCP: https://kb.triplewhale.com/en/articles/12461115-the-moby-mcp
- Shopify AI Toolkit / Dev MCP: https://shopify.dev/docs/apps/build/ai-toolkit
- Shopify Storefront MCP context: https://shopify.dev/docs/apps/build/storefront-mcp

Use these links as setup citations only. Report metrics still need citations to the actual exported file, connected query, or report row used.

## Readiness Output Pattern

For each source, report:

- source and role;
- status: `ready`, `ready_with_caveats`, `partial`, `stale`, `missing_data`, `not_connected`, `needs_install`, `needs_admin_setup`, `needs_browser_approval`, or `blocked`;
- access route tested;
- evidence for the readiness claim;
- smallest next step;
- decision impact.

End with:

- reports runnable now;
- reports runnable degraded;
- reports blocked;
- top 3 source unblocks;
- exact exports or connector/MCP setup needed next.
