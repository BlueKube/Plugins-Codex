# BlueKube Codex Plugins

These plugins are made for BlueKube team members to use with their Codex app. They should install them with Codex, as well as the required MCP connections needed.

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
