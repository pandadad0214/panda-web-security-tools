# Panda Web Security Tools

<!-- mcp-name: io.github.pandadad0214/panda-web-security-tools -->

Give Claude, Cursor or any MCP client 7 site, email and agent-safety tools: SPF/DKIM/DMARC audits, AI search and SEO checks, page change monitoring, hidden prompt-injection scans, bulk domain expiry, broken links and RSS/Atom feed monitoring. Each tool runs one public-data Apify Actor on your own Apify account and is priced per result (the hidden AI instructions scanner is free). Part of the [Panda Federation](https://github.com/pandadad0214/panda-federation-tools) toolkit (40 tools in four focused servers).

[![PyPI](https://img.shields.io/pypi/v/panda-web-security-tools)](https://pypi.org/project/panda-web-security-tools/)
[![Latest Release](https://img.shields.io/github/v/release/pandadad0214/panda-web-security-tools?label=latest%20release)](https://github.com/pandadad0214/panda-web-security-tools/releases/latest)
[![Umbrella](https://img.shields.io/badge/index-panda--federation--tools-blue)](https://github.com/pandadad0214/panda-federation-tools)
[![Apify Store](https://img.shields.io/badge/Apify_Store-pandadad0214-00a3ff)](https://apify.com/pandadad0214)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

<a href="https://launchmcp.co?utm_source=badge&utm_medium=referral" target="_blank" rel="nofollow noopener noreferrer"><img src="https://launchmcp.co/featured-badge.png?v=1" alt="Featured on Launch MCP" width="200" height="52" /></a>

## Part of [Panda Federation](https://pandafederation.com/)

[![Part of Panda Federation](https://pandafederation.com/assets/badge.svg)](https://pandafederation.com/)

This project is a module of the Panda Federation — public-data tools, MCP servers, and local-first apps in one catalog. See the rest of the work, including books when they publish and the matching free or paid editions of this tool, at the [official site](https://pandafederation.com/).

## How to use this

```bash
uvx panda-web-security-tools
```

1. **Get a free Apify token** at [console.apify.com/settings/integrations](https://console.apify.com/settings/integrations) (the free plan includes $5 of monthly credit) and install [uv](https://docs.astral.sh/uv/).
2. **Add the server to your MCP client:** command `uvx`, args `["panda-web-security-tools"]`, env `APIFY_TOKEN` (Cursor JSON below).
3. **Ask in plain words**, e.g. "Audit the email security of acme.com and its three competitors and list the DNS fixes." Start with one or two inputs and read the `summary` / `agentSummary` line before widening.

```json
{"mcpServers": {"panda-web-security-tools": {"command": "uvx", "args": ["panda-web-security-tools"], "env": {"APIFY_TOKEN": "apify_api_YOUR_TOKEN"}}}}
```

## For AI agents

| Field | Value |
| --- | --- |
| Purpose | Focused MCP server with 7 site, email and agent-safety tools: SPF/DKIM/DMARC audits, AI search and SEO checks, page change monitoring, hidden prompt-injection scans, bulk domain expiry, broken links and RSS/Atom feed monitoring. |
| Use when | A task needs a read-only audit of public DNS, web pages, links or feeds: email spoofing risk, AI/SEO readiness, page changes, hidden AI instructions, domain expiry, dead links or new RSS/Atom items. |
| Do not use when | You need penetration testing or logged-in scans (not offered), or the task is research (`panda-research-tools`), funding (`panda-public-funding-tools`) or leads (`panda-leads-tools`). |
| Install | `uvx panda-web-security-tools` (stdio, Python 3.11+) |
| Auth | `APIFY_TOKEN` env var; runs bill to that Apify account. |
| Tools | 7, listed under [Tools](#tools-7) |
| Outputs | JSON rows plus a one-line `summary` / `agentSummary`; Excel/CSV files on the Apify run. |
| Side effects and cost | Starts Apify runs; pay per result; empty runs are not charged per result; `run_max_charge_usd` caps each call. Read-only toward third-party sites. |

## Other ways to install

From the umbrella package (same tools):

```bash
uvx --from panda-federation-tools panda-web-security-tools
```

From this repo instead of PyPI:

```bash
uvx --from git+https://github.com/pandadad0214/panda-web-security-tools panda-web-security-tools
```

Cursor / Claude / VS Code: command `uvx`, args `["panda-web-security-tools"]`, env `APIFY_TOKEN`.

Official MCP Registry name for this stdio package: `io.github.pandadad0214/panda-web-security-tools` ([server.json](server.json)). That name is separate from the hosted research server `io.github.pandadad0214/panda-research-mcp`. Registry clients install the PyPI package with `uvx panda-web-security-tools`. The git command above stays the install path from this repo.

## Use with Gemini CLI

Install this repo as a [Gemini CLI extension](https://geminicli.com/docs/extensions/) (adds the MCP server plus a short `GEMINI.md` context file). Needs [Gemini CLI](https://geminicli.com/), [uv](https://docs.astral.sh/uv/), and a free [Apify token](https://console.apify.com/settings/integrations).

```bash
gemini extensions install https://github.com/pandadad0214/panda-web-security-tools
```

The extension prompts for `APIFY_TOKEN` on install and launches the server with `uvx panda-web-security-tools`. Gallery listing is automatic once this public repo carries the `gemini-cli-extension` topic and a root `gemini-extension.json` (crawled daily).

## Tools (7)

- `email_domain_security_checker`
- `ai_search_seo_audit`
- `website_change_monitor`
- `hidden_ai_instructions_scanner`
- `bulk_domain_whois_expiry`
- `broken_link_checker`
- `rss_feed_monitor`

Each tool runs one Apify Actor on your account. Empty runs are not charged per result; every call is capped by `run_max_charge_usd`. Full schemas and prices: [umbrella README](https://github.com/pandadad0214/panda-federation-tools#domain-tool-lists).

## Sibling domain servers

- [`panda-research-tools`](https://github.com/pandadad0214/panda-research-tools) — Scholarly integrity and papers: citation checks, literature and PubMed search, academic experts, PDF tables, Wayback Machine snapshots, topic trends.
- [`panda-public-funding-tools`](https://github.com/pandadad0214/panda-public-funding-tools) — Public money, filings and safety monitors: grants, contracts, SAM.gov bids, SBIR/STTR topics, SEC financials, clinical trials, Federal Register, recalls, VIN decode, EU tenders.
- [`panda-leads-tools`](https://github.com/pandadad0214/panda-leads-tools) — Public leads and enrichment: NPI providers, podcasts, local businesses, hiring signals, website enrichment, team pages, trucking carriers, IRS nonprofits, building permits, new Florida, Texas, New York and Colorado businesses, H-1B sponsors, French companies.

Index / compatibility mega-server: [panda-federation-tools](https://github.com/pandadad0214/panda-federation-tools) (use only when you truly need every tool).

## TDQS standard

New tools join this domain only while the count stays in the 3–15 band. Descriptions follow the checklist in the umbrella repo. See [tdqs-standard](https://github.com/pandadad0214/panda-federation-tools) / project docs.

Built by Panda Federation. MIT licensed.
