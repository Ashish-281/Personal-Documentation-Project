# Parcelly Docs: a docs-as-code portfolio

Documentation for **Parcelly**, a fictional shipment tracking API. The product is invented; the workflow is real. This repo shows how I plan, write, review, test, and publish technical documentation using the same practices engineering teams use for code.

**Live site:** `https://YOUR-USERNAME.github.io/parcelly-docs/`

## What this demonstrates

| Skill | Where to look |
|---|---|
| Information architecture ([Diátaxis](https://diataxis.fr/)) | `docs/` folders: tutorials, how-to, concepts, reference |
| API documentation from an OpenAPI spec | `docs/reference/openapi.yaml`, `docs/reference/api.md` |
| Style guide and prose linting | `docs/contributing/style-guide.md`, `.vale.ini`, `.vale/` |
| Automated quality gates (CI/CD) | `.github/workflows/docs.yml` |
| Review workflow | `.github/pull_request_template.md`, `CONTRIBUTING.md` |
| Diagrams as code | Mermaid in `docs/concepts/shipment-lifecycle.md` |
| Release communication | `docs/release-notes.md` |

## Tech stack

- **Static site generator:** MkDocs with Material theme
- **API reference:** OpenAPI 3.0 rendered with Swagger UI
- **Linting:** Vale (Google style guide, write-good, custom rules), markdownlint, Redocly CLI
- **Link checking:** `mkdocs build --strict` (internal) and lychee (external)
- **CI/CD and hosting:** GitHub Actions and GitHub Pages

## Run locally

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve          # http://127.0.0.1:8000
```

Run the linters locally:

```bash
vale sync && vale docs/
npx markdownlint-cli2 "docs/**/*.md"
npx @redocly/cli lint docs/reference/openapi.yaml
```

## Repository layout

```text
.
├── .github/workflows/docs.yml   # lint, build, deploy
├── .vale/                       # custom Vale styles and vocabulary
├── docs/
│   ├── getting-started/         # onboarding
│   ├── tutorials/               # learning-oriented
│   ├── how-to/                  # task-oriented
│   ├── concepts/                # understanding-oriented
│   ├── reference/               # information-oriented (OpenAPI, errors)
│   └── contributing/            # style guide
├── mkdocs.yml
└── requirements.txt
```

## Deploy

1. Push to GitHub and set the default branch to `main`.
2. Replace `YOUR-USERNAME` in `mkdocs.yml`, this README, and `docs/about.md`.
3. The first push to `main` builds and publishes to the `gh-pages` branch.
4. In **Settings → Pages**, set the source to the `gh-pages` branch.

## License

Content: CC BY 4.0. Code and config: MIT.
