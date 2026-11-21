# Project setup for coding agents

Use this guide when the owner shares `ai-context` after discussing a project idea. Prepare the project overview from that conversation and recommend optional coding guides that fit the project's targets.

## Prepare the overview

1. Read the preceding discussion and any notes the owner provided. Use the latest agreed decisions. Ask for the discussion or a summary if neither is available.
2. Read the [project overview template](../context/project-overview.md). Preserve its headings and fill the applicable sections with the project's goals, audience, MVP scope, flows, domain rules, and agreed stack. Record unresolved choices, conflicts, and tentative ideas under **Open questions, decisions, and references**. Use `N/A` for inapplicable sections.
3. Write only `context/project-overview.md` in the owner's project workspace or designated copy of the template. When an overview already exists, keep details that still apply and update it with the agreed decisions. If the owner supplied only the template URL and there is no writable project destination, return the completed Markdown with its intended path.

Use the shared repository as the source for this setup. Leave [AGENTS.md](../AGENTS.md), [coding-standards.md](../context/coding-standards.md), [current-feature.md](../context/current-feature.md), and [feature workflow files](../skills/feature/) intact. This step ends with the overview and guide recommendations. Feature specs, app code, tool setup, and Git actions belong to later requests.

## Recommend optional guides

Inspect [context/optional/](../context/optional/) and match the guides to the agreed stack and what each target produces. Give the owner the source path, the destination directly under the project's `context/` directory, and a short reason for each suggestion. For example, a browser UI that renders HTML from JSX can use [web-ui-standards.md](../context/optional/web-ui-standards.md) at `context/web-ui-standards.md`.

The owner copies the selected template files. If neither the template's optional guides nor the project's existing documentation covers a recurring coding or verification need, propose a project-specific guide. Explain what it would cover, why the project needs it, and where it would go. Ask for explicit approval and wait for the owner's reply before drafting or creating it.

After approval, create a concise Markdown guide under the owner's project `context/` directory as a separate documentation task. Base it on the agreed stack, the project's conventions, and version-matched documentation where applicable. If there is no writable project destination, provide the guide as Markdown with its intended path.

Under **Additional coding standards**, link guides already present in the project and identify the target if the repository has several. Mark guides awaiting a copy or approval as pending. If a recommendation depends on an unresolved stack decision, state that condition. Use `N/A` when no guides apply.

## Hand off for review

Report the overview path or provide the completed Markdown, summarize the open decisions, and list the recommended guides. Call out any proposed guide that needs approval. Wait for the owner's review. Once the overview is agreed, run `feature plan` only when the owner asks for feature specs. Follow [AGENTS.md](../AGENTS.md) and the [feature workflow](../skills/feature/SKILL.md) for subsequent work.
