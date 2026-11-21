# Project setup for coding agents

Use this guide when the owner shares `ai-context` after discussing a project idea. Prepare the overview and shared workflow files, recommend optional coding guides, and guide the owner through design references and feature planning.

## Prepare the overview

1. Read the preceding discussion and any notes the owner provided. Use the latest agreed decisions. Ask for the discussion or a summary if neither is available.
2. Read the [project overview template](../context/project-overview.md). Preserve its headings and fill the applicable sections with the project's goals, audience, MVP scope, flows, domain rules, and agreed stack. Record unresolved choices, conflicts, and tentative ideas under **Open questions, decisions, and references**. Use `N/A` for inapplicable sections.
3. Write `context/project-overview.md` in the owner's project workspace or designated copy. When an overview already exists, keep details that still apply and update it with agreed decisions.

## Prepare the project files

1. In the project destination, copy any missing shared files from the paths listed in [the README](../README.md#set-up-your-project-repository). Include `AGENTS.md`, `context/coding-standards.md`, `context/current-feature.md`, `skills/feature/`, and the `context/features/`, `context/fixes/`, and `context/screenshots/` directories. Treat the shared template as the source and preserve the shared instructions, specs, and active feature record already in the project.
2. If the project already has an `AGENTS.md`, preserve its project-specific rules and add any missing references to the overview, coding standards, active feature record, and feature workflow. If a template rule conflicts with an existing rule, surface the conflict and ask the owner how to resolve it.
3. Create or update the destination's `.gitignore` using [the version control rules](../context/coding-standards.md#version-control-and-generated-files). Verify that team context remains trackable and that local output and private files for the actual stack are ignored.

If there is no writable project destination, return the completed overview as Markdown with its intended path, the files to copy, and any applicable `.gitignore` entries. Feature specs, app code, tool setup, and Git actions belong to later requests.

## Recommend optional guides

Inspect [context/optional/](../context/optional/) and match the guides to the agreed stack and what each target produces. Give the owner the source path, the destination directly under the project's `context/` directory, and a short reason for each suggestion. For example, a browser UI that renders HTML from JSX can use [web-ui-standards.md](../context/optional/web-ui-standards.md) at `context/web-ui-standards.md`.

The owner copies the selected template files. If neither the template's optional guides nor the project's existing documentation covers a recurring coding or verification need, propose a project-specific guide. Explain what it would cover, why the project needs it, and where it would go. Ask for explicit approval and wait for the owner's reply before drafting or creating it.

After approval, create a concise Markdown guide under the owner's project `context/` directory as a separate documentation task. Base it on the agreed stack, the project's conventions, and version-matched documentation where applicable. If there is no writable project destination, provide the guide as Markdown with its intended path.

Under **Additional coding standards**, link guides already present in the project and identify the target if the repository has several. Mark guides awaiting a copy or approval as pending. If a recommendation depends on an unresolved stack decision, state that condition. Use `N/A` when no guides apply.

## Prepare visual references with v0

1. If the project has a browser UI, ask the owner about the intended visual direction before drafting a prompt. Group the questions around palette, light or dark theme, typography, layout density, examples they like, and which screens to prototype first. Confirm preferences already discussed and ask only for decisions that are still open. Wait for their answer or an explicit request to choose the remaining details.
2. Once the direction is agreed, give the owner one self-contained prompt in a copyable text block for [v0.app](https://v0.app/). Fill it in from the agreed overview and visual preferences. Include the product and audience, the screens and their primary actions, navigation and key flows, relevant empty, loading, and error states, mobile and desktop behavior, accessibility, and applicable language or text direction. Specify the palette, theme, typography, and layout preferences. Ask for a working UI prototype with representative sample data so the owner can preview and capture the screens. [v0 prompting guide](https://v0.app/docs/text-prompting)
3. Ask the owner to capture the relevant screens from the v0 preview and save them in `context/screenshots/` with descriptive names. When they supply the images, list the filenames under **Visual references** in the overview and note what to borrow from each one. Use the screenshots for visual guidance and the overview or spec for behavior.

Skip the visual reference step for projects without a browser UI or when the owner chooses to proceed without a prototype.

## Hand off for review

Report the overview path or provide the completed Markdown. Summarize the files prepared, open decisions, and optional guides awaiting a copy or approval. If visual preferences are still open, ask about them in this handoff.

Always explain the next step after delivering the overview. Tell the owner that once they approve the overview and have the setup files on local `dev`, they can say `feature plan` to turn the agreed roadmap into ordered Markdown specs under `context/features/`. If a visual reference is still pending, say which specs can be planned now and which decisions need the reference. Wait for an explicit planning request before writing specs. Follow [AGENTS.md](../AGENTS.md) and the [feature workflow](../skills/feature/SKILL.md) for subsequent work.
