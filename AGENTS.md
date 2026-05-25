# AGENTS.md — Working on home-tech

Authoring conventions for Claude Code sessions editing this repo. Read before adding or restructuring content.

## What this repo is

A personal knowledge base for the home technology stack — network gear, servers, self-hosted services, and the choices behind them. It is **not** a code project. There is no build, no test suite, no generators. Every file under `docs/` is hand-edited markdown.

## Content kinds

The site has three top-level sections, each with its own conventions:

| Section | Lives in | Purpose |
|---------|----------|---------|
| **Diagrams** | `docs/diagrams/` | Mermaid diagrams (topology, service maps, data flows) |
| **Inventory** | `docs/inventory/` | Endpoint devices and cloud services (network gear stays under Diagrams) |

When adding content, pick the kind first. If it doesn't fit, propose a new section before sprinkling files into the wrong one.

## Diagrams

- All Mermaid diagrams use the hand-drawn look. Every diagram starts with `%%{ init: { 'look': 'handDrawn' } }%%`.
- Use the latest Mermaid (CDN is pinned by the shared hub JS; do not override).
- No `\n` or `<br>` line breaks in node labels — they don't render. Use separate nodes or shorter labels.
- Sankey diagrams are fine for "what depends on what" views; see the docsify skill for the syntax.

## Docsify wiring

- This repo follows the **chris-peterson hub pattern**: `docs/index.html` loads `https://chris-peterson.github.io/js/docsify-shared.js` and calls `initProject(...)`. No local CSS, no theme files. Do **not** add standalone docsify scaffolding.
- `code_languages` in `initProject` should match what's actually in fenced code blocks. Add languages there as content grows; don't speculatively load plugins.
- Sidebar links are absolute (`/decisions/`, `/notes/foo`) per the `use-absolute-paths-for-docsify` rule.
- The `**Section**` + `[Section](/path/)` pattern in `_sidebar.md` is intentional — bold for grouping, link-no-children for sections with dedicated index pages.

## Audience: README vs. docs

- Root `README.md` — for someone cloning the repo to work on it. Repo layout, preview command, deployment.
- `docs/README.md` — landing page for the published site. End-user perspective.

Do not duplicate content between them.

## When making changes

- **New diagram** — Drop the file in `docs/diagrams/`, link it from `docs/diagrams/README.md`.
- **New inventory entry** — Add a row to the relevant table in `docs/inventory/devices.md` or `docs/inventory/services.md`. Match the date format already in the table.
- **Restructure** — If a section grows past ~10 entries, consider sub-grouping in the sidebar (see the docsify skill's *Long-list pattern*).

## Preview before pushing

```bash
just docs
```

If the change is visual (sidebar restructure, new diagram, layout edit), open it in a browser before committing.
