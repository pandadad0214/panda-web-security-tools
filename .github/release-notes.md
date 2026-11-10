**Install** from [PyPI](https://pypi.org/project/panda-web-security-tools/) (needs [uv](https://docs.astral.sh/uv/) and a free [Apify token](https://console.apify.com/settings/integrations)):

```bash
uvx panda-web-security-tools@{{VERSION}}
```

- **Cursor / Claude / VS Code:** command `uvx`, args `["panda-web-security-tools"]`, env `APIFY_TOKEN`.
- Official MCP Registry name: `io.github.pandadad0214/panda-web-security-tools`.

### Added
- `rss_feed_monitor`. This server now has 7 tools.

### Changed
- Syncs with panda-federation-tools 1.8.0 (40 tools across four focused servers). Requires `panda-federation-tools>=1.8.0,<2`.

Full docs: [README](https://github.com/pandadad0214/panda-web-security-tools#readme).
