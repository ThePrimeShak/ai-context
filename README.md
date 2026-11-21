# ai-context

ai-context is a reusable template for planning and building web apps with a coding agent. It gives each project a place to record product decisions, shared coding standards, and a feature workflow with explicit review points.

**Using this repo after discussing an idea with an agent?** Start with the [agent project setup guide](docs/project-setup.md).

## From idea to project overview

1. Discuss your idea with Codex or another coding agent. Start with the problem, who has it, what belongs in the MVP, and any stack choices you've already made.
2. Share this repository in the same conversation. A short prompt like the one below points the agent to the setup guide. If you start a new conversation, include a summary of your decisions.
3. Review the overview and the recommended coding guides. With access to your project folder, the agent writes `context/project-overview.md` there. Without a writable project folder, it returns the Markdown for you to save. Open decisions go in **Open questions, decisions, and references**.

> Use https://github.com/ThePrimeShak/ai-context and the decisions from our conversation to prepare my project overview. Follow the agent project setup guide.

## Set up your project repository

Copy the following paths from this template to the same locations in your project. If your project already has an instruction file, review how its rules fit before merging the instructions.

| Path | What it does |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Defines the coding, review, verification, and Git workflow. |
| [context/project-overview.md](context/project-overview.md) | Holds your product decisions. Use the completed overview from your conversation. |
| [context/coding-standards.md](context/coding-standards.md) | Defines the shared coding standards. |
| [context/current-feature.md](context/current-feature.md) | Tracks the active feature and completion history. |
| [context/features/](context/features/), [context/fixes/](context/fixes/), and [context/screenshots/](context/screenshots/) | Hold feature specs, fix specs, and optional visual references. |
| [skills/feature/](skills/feature/) | Contains the instructions for each feature action. |

When you ask the agent to prepare your overview, it updates only `context/project-overview.md`. Keep the shared workflow files as the baseline. The agent updates specs and the active feature record later as you use the workflow.

Choose the relevant guides from [context/optional/](context/optional/). Copy each selected file directly into your project's `context/` folder and link it under **Additional coding standards** in `project-overview.md`. For example, copy [web-ui-standards.md](context/optional/web-ui-standards.md) for a browser UI, including one built with JSX. If a recurring coding or verification need has no suitable guide, the agent can propose one and write it in your project after you approve. Use `N/A` when no guides apply.

### Configure Context7

The coding workflow in [AGENTS.md](AGENTS.md) requires Context7 before code changes and package installs. For Codex, merge the Context7 server entry from the [MCP example](context/codex-mcp.toml) into `.codex/config.toml` in your trusted project. From that project, run `codex mcp login context7` and check that `codex mcp list` includes `context7`. To confirm the connection, ask the agent to look up documentation for a library you use. The example also includes a read-only Neon entry for projects that use Neon. [Codex MCP setup](https://developers.openai.com/codex/mcp)

## Plan and build a feature

After reviewing the overview, commit the setup files on your project's local `dev` branch. If `dev` does not exist, create it from the intended starting point. Request the actions below in plain language as you need them. The [feature workflow](skills/feature/SKILL.md) defines the details.

Feature specs in `context/features/` are named by milestone, sequence, and a short kebab-case slug. For example, `m0-01-baseline-check.md` is the first spec in `M0`, and `m1-02-date-only-conversion.md` is the second in `M1`. Numbering starts at `01` in each milestone. To load a spec, use its full filename stem.

| Request | What happens |
| --- | --- |
| `feature plan` | Generates specs from the approved overview. Record the specs on `dev` so the agent can load them. |
| `feature load m0-01-baseline-check` | Loads `context/features/m0-01-baseline-check.md` into the active feature record and waits for you to start. |
| `feature start` | Creates or resumes the work branch. The agent pauses after each goal and continues when you confirm your review. |
| `feature test` / `feature review` | Runs the relevant checks or reviews the changes against the spec. |
| `feature explain` | Explains the result and how the main changes work. |
| `feature complete` | Verifies the reviewed work, records completion, commits it, and merges it into local `dev`. |

## Contribute to this template

Open a pull request against `main` for changes to the shared template.

## License

This template is released under the [MIT License](LICENSE).
