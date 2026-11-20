# A Template for Building Web Apps with Coding Agents

## Start a project

1. Copy `AGENTS.md`, `context/`, and `skills/` to the root of your project. If a file with the same name already exists, take its instructions into account when merging the files. Use this README as a guide to the template.
2. Fill in [project-overview.md](context/project-overview.md) with your project's goal, MVP scope, pages, domain rules, and tech stack. The shared instructions, including [coding-standards.md](context/coding-standards.md), are ready to use. The agent finds the commands for running and testing the app in your repository.
3. Add screenshots to [context/screenshots/](context/screenshots/) as needed. For example, take a screenshot of a v0.app prototype and note in the overview which visual ideas you want to borrow. The agent uses the screenshots as a reference for layout, visual hierarchy, and overall style, then adapts those ideas to your project.
4. Commit the setup files on `dev`. If `dev` doesn't exist yet, choose a starting point and create the branch from it.

## Workflow

| Command | Result |
| --- | --- |
| `feature plan` | The agent turns the overview into feature specs in `context/features/`. You can narrow the scope by asking it to "write the specs for milestone M1," for example. |
| `feature load export-report` | The agent reads the specified spec and records its goals in `context/current-feature.md`. |
| `feature start` | The agent creates a work branch from `dev` and starts implementation. |
| `feature test`, `feature review` | The agent tests or reviews the implementation. |
| `/explain` or `feature explain` | The agent explains what the feature does and how the main changes work. |
| `feature complete` | The agent verifies and commits the work, then merges the work branch into local `dev`. |

Once the specs are ready, commit them on `dev` so `load` can use that version. The template includes `current-feature.md`, and the agent updates it as work progresses.

Merging into `main` requires a separate, explicit request, such as "Merge `dev` into `main` now." Pushing also requires a separate request.

## Use with different tools

If your tool doesn't read `AGENTS.md` automatically, start with "Read `AGENTS.md` and run `feature plan`." You can request any action in a regular message. Slash command support depends on the tool.

If your Claude Code setup only reads `CLAUDE.md`, add the following reference to `AGENTS.md` in that file. [Claude Code documentation](https://code.claude.com/docs/en/memory#share-one-file-with-other-coding-tools)

```markdown
@AGENTS.md
```
