# Mise Remote Tasks

Reusable [mise](https://mise.jdx.dev/) task collections you can include in your own projects. Each collection provides tasks for a focused use case; choose only the collections you need.

## Requirements

- [mise](https://mise.jdx.dev/) configured in your project.
- Git, so mise can fetch collections from this repository.
- Any tools required by the collection you use. Check its documentation before running its tasks.

## Add a collection to your project

First, you need to trust your project environment:

```bash
mise trust
```

Add the collection's `tasks.toml` path to the `includes` list in your project's `mise.toml`. For example, to include the AI skills and pre-commit collections:

```toml
[task_config]
includes = [
  "git::https://github.com/bcatouillard/mise-reusable-tasks//mise-tasks/ai-skills/tasks.toml?ref=main",
  "git::https://github.com/bcatouillard/mise-reusable-tasks//mise-tasks/pre-commit/tasks.toml?ref=main",
]
```

Save the file, then run a task from your project directory with `mise run <task-name>` (or its alias, if provided). For example:

```sh
mise run precommit-install
mise run pre-commit:run
```

## Available collections

| Collection   | Purpose                                                 | Documentation                                                      |
| ------------ | ------------------------------------------------------- | ------------------------------------------------------------------ |
| `ai-skills`  | Install or update agent skills using GitHub CLI.        | [Tasks, prerequisites, and usage](mise-tasks/ai-skills/README.md)  |
| `pre-commit` | Install pre-commit hooks and run them across all files. | [Tasks, prerequisites, and usage](mise-tasks/pre-commit/README.md) |

The AI skills collection requires GitHub CLI (`gh`); the pre-commit collection requires `pre-commit`. Their collection READMEs list the available task names and aliases.
