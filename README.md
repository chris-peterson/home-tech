# home-tech

📖 **[Read the docs →](https://chris-peterson.github.io/home-tech/)**

Notes, diagrams, and decision records for the technology stack running my home.

The docs site is the primary surface — this README only covers how to work on the repo itself.

## Repo layout

```text
docs/
├── README.md          # docs site landing page
├── _sidebar.md        # docsify navigation
├── index.html         # docsify shell (uses chris-peterson.github.io shared JS)
├── favicon.svg
├── decisions/         # ADRs
├── notes/             # setup walkthroughs, configs
└── diagrams/          # Mermaid diagrams
.github/workflows/docs.yml   # Pages deployment
AGENTS.md                    # authoring conventions for Claude Code sessions
```

## Preview locally

```bash
just docs
```

Runs `docsify serve docs --open`.

## Publishing

`docs/**` changes on `main` deploy to GitHub Pages via `.github/workflows/docs.yml`.
