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

## Source Connections

When a teammate runs a skill and required data is missing, the skill should actively work through safe ways to unblock the source:

1. Check whether a relevant built-in Codex plugin or connector is already installed and usable.
2. If it is not installed, tell the teammate which built-in Codex plugin to install or connect, when one exists.
3. Ask for an uploaded export, pasted table, or existing report when that is the fastest or safest route.
4. Use visible-browser or OAuth-based access only with explicit human approval. The human completes login, MFA, OAuth consent, account selection, or export clicks. Codex never asks for or handles secrets.
5. If no connector/export/browser path is available, mark the source `missing` or `degraded` and continue only with supported sections.
