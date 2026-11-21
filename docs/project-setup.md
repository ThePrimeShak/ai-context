# Project setup for coding agents

Use this guide when the owner shares `ai-context` after discussing a project idea. Follow the scope of the current request. Treat the project description, examples, and statements about what the eventual app should do as inputs to the overview.

Write new files and new content in English, including the overview, feature and fix specs, coding guides, comments, and filenames. This applies even when the owner speaks another language. Preserve required localized UI strings and exact names or quoted values. Reply to the owner in the conversation language.

| Owner request | Authorized work |
| --- | --- |
| Review this template | Read the repository and explain the relevant workflow. |
| Prepare `project-overview.md` | Read the template and write only `context/project-overview.md` in the destination project. |
| Set up the workspace | Prepare the requested overview and shared workflow files, including `.gitignore`. |
| `feature plan` | Produce English specs from the agreed overview and, where applicable, approved visual references. |
| `feature start` or an explicit request to implement a loaded feature | Follow the feature workflow for implementation. |

If the owner asks you to review the repository so you can create an overview, follow the overview scope. During overview preparation and workspace setup, leave app code, scaffolding, dependencies, builds, and Git state alone. A product description or repo link does not authorize implementation.

Use the deliverable and scope agreed in the conversation to interpret a general request to apply the template. If it remains unclear whether the owner wants an overview or workspace setup as well, ask one focused question before editing. An explicit workspace setup request includes the shared files listed below.

## Prepare the overview

1. Read the preceding discussion and any notes the owner provided. Use the latest agreed decisions. Ask for the discussion or a summary if neither is available.
2. Read the [project overview template](../context/project-overview.md). Preserve its headings and fill the applicable sections with the project's goals, audience, MVP scope, flows, domain rules, and agreed stack. Walk through the first usable flow from a new user's starting state. Record unresolved choices, conflicts, and tentative ideas under **Open questions, decisions, and references**. For each decision that blocks a milestone, identify the affected flow, such as how a new user gets access when the first milestone requires sign-in. Use `N/A` for inapplicable sections.
3. Write only `context/project-overview.md` in the owner's project workspace or designated copy. When an overview already exists, keep details that still apply and update it with agreed decisions. If there is no writable project destination, return the completed Markdown and its intended path.
4. Report the overview and ask the owner to review it. For a browser UI, use the visual reference handoff below as the next step in the conversation. For an overview-only request, keep filesystem edits limited to the overview and wait for the owner's reply.

## Prepare the project files

Follow this section only when the owner explicitly requests workspace setup.

1. In the project destination, copy any missing shared files from the paths listed in [the README](../README.md#set-up-your-project-repository). Include `AGENTS.md`, `context/coding-standards.md`, `context/current-feature.md`, `skills/feature/`, and the `context/features/`, `context/fixes/`, and `context/screenshots/` directories. Treat the shared template as the source and preserve the shared instructions, specs, and active feature record already in the project.
2. If the project already has an `AGENTS.md`, preserve its project-specific rules and tool-generated sections. Add a short section with only the missing references to the overview, coding standards, active feature record, and feature workflow.
   - If the shared workflow rules are neither present nor linked, put them in `context/agent-workflow.md` and add a direction to read it from `AGENTS.md`. Use the template's `AGENTS.md` as the source. Rebase its relative Markdown links to the new file and verify that they resolve. Keep paths shown as code relative to the project root.
   - Reuse an existing shared workflow file or reference where it already covers the same rules. If a template rule conflicts with an existing rule, surface the conflict and ask the owner how to resolve it.
   - When the owner asks to refresh an existing setup, compare its linked workflow rules and action files with the current template. Apply the requested shared updates in place and preserve the project's own rules and existing specs.
3. Create or update the destination's `.gitignore` using [the version control rules](../context/coding-standards.md#version-control-and-generated-files). Verify that team context remains trackable and that local output and private files for the actual stack are ignored.

If there is no writable project destination, give the owner the files to copy and any applicable `.gitignore` entries. Provide the completed overview as Markdown if they requested it. Feature specs, app code, tool setup, and Git actions belong to later requests.

## Recommend optional guides

Inspect [context/optional/](../context/optional/) and match the guides to the agreed stack and what each target produces. Give the owner the source path, the destination directly under the project's `context/` directory, and a short reason for each suggestion. For example, a browser UI that renders HTML from JSX can use [web-ui-standards.md](../context/optional/web-ui-standards.md) at `context/web-ui-standards.md`.

The owner can copy the selected template files or ask you to do it. Copy a guide during workspace setup when the owner has requested it or authorized you to choose and copy relevant guides. Preserve existing guides in the destination. For overview-only work, suggest guides in the reply and link existing guides in the overview.

If neither the template's optional guides nor the project's existing documentation covers a recurring coding or verification need, propose a project-specific guide. Explain what it would cover, why the project needs it, and where it would go. Ask for explicit approval and wait for the owner's reply before drafting or creating it.

After approval, create a concise Markdown guide under the owner's project `context/` directory as a separate documentation task. Base it on the agreed stack, the project's conventions, and version-matched documentation where applicable. If there is no writable project destination, provide the guide as Markdown with its intended path.

Under **Additional coding standards**, link guides already present in the project and identify the target if the repository has several. Mark guides awaiting a copy or approval as pending. If a recommendation depends on an unresolved stack decision, state that condition. Use `N/A` when no guides apply.

## Prepare visual references with v0

For a project with a browser UI, complete the visual reference step before inviting the owner to plan the full roadmap or UI features. Use existing screenshots if the owner selects them as references. Skip this step for work without browser UI or if the owner explicitly chooses to proceed without references.

1. If approved references are missing, ask about visual direction in the overview handoff. Group the questions around palette, light or dark theme, typography, layout density, examples they like, and which screens to prototype first. Confirm preferences already discussed and ask only about open choices. Wait for the owner's answer or their explicit request to choose the remaining details.
2. Once the direction is agreed, give the owner one self-contained English prompt in a copyable text block for [v0.app](https://v0.app/). Fill it in from the agreed overview and visual preferences. Include the product and audience, screens and primary actions, navigation and key flows, relevant empty, loading, and error states, mobile and desktop behavior, accessibility, and applicable UI language or text direction. Specify the palette, theme, typography, and layout preferences. Ask for a working UI prototype with representative sample data so the owner can preview and capture the screens. [v0 prompting guide](https://v0.app/docs/text-prompting)
3. End the prompt handoff by asking the owner to capture the relevant screens, save them in `context/screenshots/` with descriptive names, and tell you when they are ready. Wait for the screenshots or an explicit choice to continue without them before offering full roadmap or UI spec planning.
4. Inspect the selected screenshots. Link each actual file under **Visual references** in the overview and note which screen, state, or design detail it illustrates. If the owner has supplied files but their intended use is unclear, ask what to carry into the specs. Use the screenshots for visual guidance and the overview for behavior. Record `N/A` if the owner explicitly skips references.

## Hand off for review

Report the overview path or provide the completed Markdown. Summarize the files prepared, open decisions, and optional guides awaiting a copy or approval. Give the next action for the current stage. For a browser UI with no approved references, ask the visual questions or deliver the v0 prompt and request screenshots, depending on which step is ready.

Once the overview is approved and the visual reference step is complete or explicitly skipped, ask the owner whether to run `feature plan`. Explain that it creates ordered English Markdown specs under `context/features/` and links the applicable screenshot files. Check whether local `dev` exists and tell the owner what must be recorded there first, including the overview, setup files, and selected references. Wait for an explicit planning request before writing specs.

During workspace setup, report whether Context7 is usable for this project. If it is missing or the connection is unverified, point the owner to [Configure Context7](../README.md#configure-context7). Keep that separate from the prerequisites for documentation-only planning. Follow [AGENTS.md](../AGENTS.md) and the [feature workflow](../skills/feature/SKILL.md) for subsequent work.
