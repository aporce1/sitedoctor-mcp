# Site Doctor — read-only WordPress diagnosis for your AI

> Connect your own AI (Claude, ChatGPT, Cursor, Codex…) to any WordPress site through a **100% read-only** MCP connector and ask what's wrong — security, performance, forms, logs, downtime — with evidence. The connector never writes to the site, and your AI never sees the site's credentials.

**Website:** https://sitedoctor.syswp.pro · **Docs:** https://sitedoctor.syswp.pro/docs

---

## What it is

Site Doctor is the neutral, **read-only diagnosis layer for WordPress**. Ask your AI why a site is broken and get the root cause with evidence — without giving any AI permission to write to the site. Built for agencies and freelancers maintaining 5–100 client WordPress sites.

Three parts:
- **SaaS dashboard** — six monitors, alerts, findings and a durable intervention timeline per site.
- **One-file WordPress connector** — read-only, HMAC-signed.
- **MCP server (OAuth 2.1)** — so your own AI can reach it.

## Connect your AI to WordPress (MCP)

1. Create a free account at https://sitedoctor.syswp.pro and add a site.
2. Install the one-file read-only connector plugin (upload it, paste the connection key from the panel). It exposes **no write operations**.
3. Add Site Doctor as an **MCP server** in your AI client using **OAuth 2.1 / PKCE**. Tested with Claude, Claude Code, ChatGPT, Codex, Cursor, Trae and VS Code — or use the built-in "Doc" chat in the dashboard.
4. Ask about any site you manage in plain language. The AI reads only the evidence needed to answer; secrets are redacted before anything reaches the model.

## Why read-only (the trust model)

- The connector exposes **no write operations** — it physically cannot modify, clean or break a site.
- Your AI **never receives credentials** — wp-config constants (DB password, salts), password hashes and the connector's own key are redacted before any output reaches a model.
- Every request is **HMAC-SHA256 signed** with a nonce and ±5-minute skew; SQL is read-only; the MCP uses **OAuth 2.1 (PKCE)**; tenants are isolated per organization.
- On the **Agency** plan and above, a fix is prepared as a one-click activatable mu-plugin — a logged-in admin turns it on from wp-admin. Never a silent write.

## What it diagnoses (read-only, on real client sites)

- **Security & compromise** — skimmers, backdoors, tampered core, ghost admins; the cleanup prepared.
- **False-positive triage** — tells a real injection from a harmless file.
- **Performance** — real coverage, render-blocking scripts, the cause of slow loads.
- **Downtime** — root cause found from *outside* the site, because the uptime check and auto-investigation run externally.
- **Cron / scheduled posts**, **lost ad attribution**, **forms & leads**, **change tracking**, and **managed-host blind spots** (WP Engine / Pantheon / Kinsta, where you usually can't read debug.log).
- Offline **CVE matching** against a mirror of the Wordfence vulnerability database.

## Pricing

| Plan | Price | Sites |
|---|---|---|
| Free | $0 | 1 |
| Personal | $9/mo | 3 |
| Solo | $19/mo | 10 |
| Agency | $79/mo | 50 · one-click activatable fixes |
| Fleet | $119/mo | 100 |

Self-serve at https://sitedoctor.syswp.pro/#precios

## Links

- **Home:** https://sitedoctor.syswp.pro
- **Docs:** https://sitedoctor.syswp.pro/docs
- **Use-case library:** https://sitedoctor.syswp.pro/casos
- **Free outside-in scan** (no account): https://sitedoctor.syswp.pro/scan

---

Built by [SysWP](https://syswp.pro). Questions and trials: **aporce@syswp.com.br**
