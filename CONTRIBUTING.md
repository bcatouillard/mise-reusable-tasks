# Contributing

To add or update a reusable task collection, follow the [contributor how-to guide](docs/how-to/add-task-collection.md). The [documentation index](docs/README.md) describes the documentation structure.

Install the Git hooks with `pre-commit install`. They lint Markdown and YAML files, including GitHub Actions workflows, before each commit. The repository's `mise.toml` pins the hook tools; run `mise install` to install them. Run all hooks across the repository with `pre-commit run --all-files`.
