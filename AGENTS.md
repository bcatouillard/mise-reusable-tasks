# Repository Guidelines

This repository packages reusable [mise](https://mise.jdx.dev/) tasks for use in other projects. Keep task definitions portable and independent of the repository that consumes them.

## Task layout and documentation

- Put every task collection in `mise-tasks/<folder-name>/tasks.toml`. Use a short folder name for a related task group; do not put task definitions in the root `mise.toml`.
- Every task folder must also contain a `README.md` documenting **all** tasks in its `tasks.toml`.
- Keep each folder's README in sync whenever its tasks change. Use a table with these columns: `Name`, `Description`, and `Alias`. Show `—` when a task has no alias.
- Use each task's TOML table name as `Name`; copy its description and alias exactly into the table.

## Reusable task design

- A task must be useful across projects, not tailored to this repository or one consuming project. Avoid project-specific names, fixed repository paths, assumptions about a project's layout or configuration, and machine-specific paths or credentials.
- Make project-dependent values configurable through task arguments or environment variables where appropriate. State required tools and other prerequisites in the task description or its README.
- Keep tasks focused and use mise's native task configuration. Add aliases only when they provide a useful alternate name.

## Validation

- Before finishing a task change, check that the TOML is valid and that the README table lists every task with matching names, descriptions, and aliases.
- Execute tasks only when their side effects are understood and safe in the current environment.
