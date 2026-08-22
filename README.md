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
- `onboarding.html` — a second, generically-useful page: what actually happens when a repo starts
  working with Bridge (App install, scoped permissions, conservative policy defaults, watched
  before trusted). Adapted from `devNalyx/bridge`'s internal
  `docs/operations/onboarding-a-repo.md` runbook, stripped of internal issue numbers and
  implementation detail — same drift rule as `index.html` applies if the two are ever both updated.
- `teammate.html` — the real-team path: connecting your own AI agent via `bridge-client`, a real,
  correctly-scoped, downloadable client — never a copy of Bridge's own daemon or sandbox. Removed
  2026-08-22 (an earlier version described the wrong architecture), rebuilt correctly 2026-08-23
  once the real client existed. Adapted from `devNalyx/bridge`'s internal
  `docs/operations/onboarding-a-teammate.md`, stripped of internal file paths and package names —
  same drift rule as `index.html` applies. Links to the real public release:
  `github.com/devNalyx/bridge-site/releases`.
- `og-image.png` — 1200×630 social share preview (`og:image`/`twitter:image`), rendered from the
  page's own dark terminal aesthetic so a shared link doesn't show a blank card.
- `robots.txt`, `sitemap.xml` — basic crawl/indexing hygiene for the single page.
- `CNAME` — points Pages at `bridge.nalyx.dev` (custom domain wired by @AliRezaTaleghani).

## Edits

Keep it boring and dependency-free. Preview locally by opening `index.html` or
`python3 -m http.server`. When copy changes, update
`devNalyx/bridge`'s `docs/website/landing-page-copy.md` to match.

The primary CTA is a plain `mailto:` link (no form backend, no third party, no dependency) — it
used to point at `devNalyx/bridge/issues`, which 404s for anyone without access since that repo is
private. If a real waitlist/form service gets adopted later, replace both the hero-adjacent and
footer `mailto:` links together so they don't drift.
