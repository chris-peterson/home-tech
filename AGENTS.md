# AGENTS.md — Working on home-tech

Operating instructions for Claude Code sessions editing this repo. Read before adding or restructuring content.

## What this repo is

A personal knowledge base for the home technology stack — network gear, servers, self-hosted services, and the choices behind them. It is **not** a code project. There is no build, no test suite, no generators.

## Authoring conventions live in the README

[README.md](README.md) holds the conventions for this repo: which section content belongs in, the current-state vs. decisions split, the Mermaid rules, and the docsify hub wiring. It is the maintainer-facing surface and the single home for that material — read it before writing, and update it there rather than restating it here.

The rest of this file is the operating direction that has no reader outside a Claude Code session.

## Audience

Three surfaces, three audiences. Content belongs to exactly one:

- **`README.md`** — someone cloning the repo to work on it.
- **`docs/`** — someone reading the published site. No authoring guidance here.
- **`AGENTS.md`** — this file.

When the same paragraph wants to exist in two of them, pick the owner and link from the other.

## When making changes

- **New diagram** — Drop the file in `docs/diagrams/`, link it from `docs/diagrams/README.md`.
- **New inventory entry** — Add a row to the relevant table in `docs/inventory/`. Match the date format already in the table.
- **New decision** — Drop the file in `docs/decisions/`, link it from `docs/decisions/README.md`. Leave `docs/diagrams/` and `docs/inventory/` describing what is installed until the change lands, then update them in a separate pass.
- **Power figures** — Rated draw comes from the manufacturer's tech specs and gets a source. Measured draw comes from a meter at the outlet and gets a date. Keep the two in separate columns; a rated figure is not a measurement.
- **Restructure** — If a section grows past ~10 entries, consider sub-grouping in the sidebar (see the docsify skill's *Long-list pattern*).

## Preview before pushing

```bash
just docs
```

If the change is visual (sidebar restructure, new diagram, layout edit), open it in a browser before committing. The shared theme CSS and `projects.yml` 404 under local preview — expected, since they come from the hub rather than this repo.
