# bridge-site

Landing page for **Bridge** — an MCP server that runs inside the AI harness you already use
(Claude Code, OpenCode, and others), giving hybrid human/AI teams live presence, recent events, and
a way to act back on GitHub, with zero AI or decision-making of Bridge's own — served at
`bridge.nalyx.dev` via GitHub Pages.

This repo is intentionally **public** and holds only the marketing/landing page. Product
foundation, architecture, decisions, and roadmap live in the private
[`devNalyx/bridge`](https://github.com/devNalyx/bridge) repo; the canonical copy for this page is
[`docs/website/landing-page-copy.md`](https://github.com/devNalyx/bridge/blob/main/docs/website/landing-page-copy.md)
there — if the two drift, that file wins.

## Stack

- Static single-page site (HTML/CSS, no framework), dark terminal aesthetic.
- Served by GitHub Pages from `main` (root).

## Layout

- `index.html` — the landing page: what Bridge is (a harness-invoked MCP server, ADR-0022),
  the problem it solves, who it's for, its four real tools, and proof it's real.
- `connect.html` — the real onboarding path: registering `bridge-mcp` with your own harness's MCP
  config, with an honest per-client verification-tier table (live-verified vs. documented) inlined
  on the page itself — `devNalyx/bridge` (where the fuller onboarding runbook lives) is private, so
  it isn't linked directly; same standing rule as `index.html`'s. Replaces `teammate.html`, which described
  a standalone downloadable client (`bridge`/`internal/thinclient`) — a real, shipped architecture
  that was itself later rejected and deleted in favor of the current harness-invoked model; see
  `devNalyx/bridge`'s ADR-0022 for that history. Nothing about that back-and-forth is reflected
  here — this page describes only the current, real, live-verified shape.
- `og-image.png` — 1200×630 social share preview (`og:image`/`twitter:image`), rendered from the
  page's own dark terminal aesthetic so a shared link doesn't show a blank card.
- `robots.txt`, `sitemap.xml` — basic crawl/indexing hygiene for the two pages.
- `CNAME` — points Pages at `bridge.nalyx.dev` (custom domain wired by @AliRezaTaleghani).

## Edits

Keep it boring and dependency-free. Preview locally by opening `index.html` or
`python3 -m http.server`. When copy changes, update
`devNalyx/bridge`'s `docs/website/landing-page-copy.md` to match.

The primary CTA is a plain link to `connect.html`, and the footer's contact is a plain `mailto:`
link (no form backend, no third party, no dependency). Neither page links into
`devNalyx/bridge/issues`, which 404s for anyone without access since that repo is private.
