# Contributing

Docs changes follow the same flow as code changes.

1. Create a branch: `docs/<short-description>`.
2. Make your change. Follow the [style guide](docs/contributing/style-guide.md).
3. Run `mkdocs serve` and check the rendered page.
4. Run `vale docs/` and fix errors.
5. Open a pull request. CI must pass before merge.
6. Request review from a subject-matter expert for technical accuracy.

Commit messages use the imperative mood: `Add webhook retry guide`, not `Added`.
