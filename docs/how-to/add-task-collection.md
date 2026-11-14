# Add a task collection

This guide explains how to add a reusable mise task collection to this repository.

## Choose a collection

Group related tasks under a short, descriptive folder name in `mise-tasks/`. Put the task definitions in that folder's `tasks.toml`; do not add collection tasks to the repository's root `mise.toml`.

For example, a collection named `formatting` has this structure:

```text
mise-tasks/formatting/
├── README.md
└── tasks.toml
```

## Define the tasks

Use mise's native task configuration in `tasks.toml`. Each task needs a useful description and a command that works across projects. Add an alias only when it gives users a useful alternative name.

```toml
["format"]
description = "Format project files"
run = "formatter --write ."

["check"]
alias = "lint"
description = "Check project files"
run = "formatter --check ."
```

Keep the tasks independent of this repository and of any one consuming project:

- Avoid consumer-specific names, fixed repository or machine paths, credentials, and assumptions about a project's layout or configuration.
- Make project-dependent values configurable through task arguments or environment variables where appropriate.
- Include prerequisites in the task descriptions or README so users know which tools they need.
- Keep each task focused, and use aliases only when they help users discover or invoke it.

## Document the collection

Add a `README.md` beside `tasks.toml`. Include a table with one row for every task and these columns: `Name`, `Description`, and `Alias`. Copy the task table name, description, and alias exactly from `tasks.toml`. Use `—` when a task has no alias. Also explain the collection's prerequisites and how consumers can use its tasks.

## Validate the changes

Before submitting the collection:

1. Check that `tasks.toml` is valid TOML.
2. Compare the README table against `tasks.toml`: every task must appear, and its name, description, and alias must match exactly.
3. Confirm that examples and prerequisites in the README describe the actual tasks and required tools.
4. Run tasks only when their side effects are understood and safe in the current environment.

When changing an existing collection, update its README whenever its tasks change. Update the root [collection list](../../README.md) when adding a collection so consumers can discover it.
