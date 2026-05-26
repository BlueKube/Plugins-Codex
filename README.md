# BlueKube Codex Plugins

These plugins are made for BlueKube team members to use with their Codex app. They should install them with Codex, connect the built-in Codex plugins they already have access to, and use approved MCP/export routes for source tools that Codex does not provide natively.

Current plugin:

- `porch-potty-marketing`: recommend-only marketing reports and audits for Porch Potty.

## Install In Codex

Use **Plugins** -> **Add More** -> **Add marketplace**.

For the GitHub install, use this repository as the source:

```text
https://github.com/BlueKube/Plugins-Codex
```

Set:

```text
Git ref: main
Sparse paths: leave blank
```

For local testing, use this folder as the source:

```text
C:\Users\bkenn\codex-marketplaces\porch-potty-marketing
```

This repository uses the repo marketplace layout:

```text
.agents/plugins/marketplace.json
plugins/porch-potty-marketing/.codex-plugin/plugin.json
plugins/porch-potty-marketing/skills/*/SKILL.md
```

## Included Skills

- `weekly-marketing-audit`
- `standard-report`
- `paid-media-audit`
- `ecommerce-kpi-audit`
- `check-what-i-can-run`

The plugin is recommend-only. It uses uploaded exports, pasted data, existing reports, and connected read-only sources; missing sections must be marked missing or degraded rather than invented.

## Source Connections

When a teammate runs a skill and required data is missing, the skill actively works through safe ways to unblock the source. The best starting prompt is:

```text
@porch-potty-marketing check-what-i-can-run

Use my connected Google Drive, shared Porch Potty folders, uploaded files, pasted data, and any read-only Codex sources available in this session. Tell me which reports are runnable now and which built-in plugins, approved MCP routes, or exports are needed next. Do not make live changes.
```

The plugin should then:

1. Check whether a relevant built-in Codex plugin or connector is already installed and usable.
2. If it is not installed, tell the teammate which built-in Codex plugin to install or connect, when one exists.
3. Prefer the shared Porch Potty / BlueKube Google Drive evidence layer so every teammate gets a consistent baseline.
4. Recommend approved official/vendor MCP routes when a native Codex plugin is not available.
5. Ask for an uploaded export, pasted table, or existing report when that is the fastest or safest route.
6. Use visible-browser or OAuth-based access only with explicit human approval. The human completes login, MFA, OAuth consent, account selection, or export clicks. Codex never asks for or handles secrets.
7. If no connector/export/browser path is available, mark the source `missing` or `degraded` and continue only with supported sections.

Built-in Codex routes to prefer when available:

- Google Drive / Google Sheets / Spreadsheets for shared evidence, exports, and weekly packets.
- Supabase for BlueKube KPI memory or source-run rows, only when connected and intended for the report.
- Browser or Chrome only for approved visible account checks or exports.
- Slack only for prior actions or discussion context, when connected and relevant.

Approved source routes to consider outside native Codex plugins:

- Google Analytics MCP for GA4 read-only reporting.
- Google Ads MCP for Google Ads API reporting, with admin-managed setup outside chat.
- Amazon Ads MCP for Amazon Ads API reporting, with admin-managed setup outside chat.
- Klaviyo MCP with read-only mode for lifecycle reporting.
- Triple Whale Moby MCP for blended attribution and Triple Whale data.
- Shopify, Search Console, Meta Ads, TikTok Ads, Amazon Seller Central, inventory, and unit economics should use shared reports/exports by default unless BlueKube has approved a read-only API/MCP path.

The detailed source map lives in:

```text
plugins/porch-potty-marketing/references/source-connections.md
```
