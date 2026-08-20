# bridge-site

Landing page for **Bridge** — the operational orchestration layer for hybrid software teams —
served at `bridge.nalyx.dev` via GitHub Pages.

This repo is intentionally **public** and holds only the marketing/landing page. Product
foundation, architecture, decisions, and roadmap live in the private
[`devNalyx/bridge`](https://github.com/devNalyx/bridge) repo; the canonical copy for this page is
[`docs/website/landing-page-copy.md`](https://github.com/devNalyx/bridge/blob/main/docs/website/landing-page-copy.md)
there — if the two drift, that file wins.

## Stack

- Static single-page site (HTML/CSS, no framework), dark terminal aesthetic.
- Served by GitHub Pages from `main` (root).

## Layout

- `index.html` — the landing page, rebuilt around Bridge's orchestration/control-plane
  positioning (tracked in `devNalyx/bridge` issue #37, shipped).
- `CNAME` — points Pages at `bridge.nalyx.dev` (custom domain wired by @AliRezaTaleghani).

## Edits

Keep it boring and dependency-free. Preview locally by opening `index.html` or
`python3 -m http.server`. When copy changes, update
`devNalyx/bridge`'s `docs/website/landing-page-copy.md` to match.
