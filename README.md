# ai-context

Use this repository as the shared template when the owner gives you its link after discussing a project idea. Turn the decisions from that discussion into a project overview and recommend the optional coding guides that fit the project.

## Prepare the project overview

1. Use the preceding discussion and any notes the owner supplied. Ask for the discussion or a summary if neither is available. Use the latest agreed decisions and record unresolved choices, conflicts, and tentative ideas in **Open questions, decisions, and references**.
2. Read the [project overview template](context/project-overview.md). Fill its applicable sections with the project's goals, audience, MVP scope, flows, domain rules, and agreed stack. Preserve the headings. Use `N/A` for inapplicable sections and record missing decisions as open questions.
3. Write only `context/project-overview.md` in the owner's project workspace or designated local copy of the template. If that project already has an overview, update it with the agreed decisions and preserve existing details that still apply. Treat the linked repository as the template source. If the owner has provided only a repository URL and no writable destination, return the completed Markdown so they can save it as `context/project-overview.md`.

Treat [AGENTS.md](AGENTS.md), [coding-standards.md](context/coding-standards.md), [current-feature.md](context/current-feature.md), and [skills/](skills/) as shared workflow files. Product decisions belong in the overview.

## Recommend optional standards

Inspect [context/optional/](context/optional/) and choose guides that match the project's agreed stack and targets. For each recommendation, give the source path, the destination directly under the project's `context/` directory, and a short reason it applies. For example, recommend [web-ui-standards.md](context/optional/web-ui-standards.md) for a project that renders HTML in a browser, including HTML generated from JSX or templates.

The owner copies the selected files. Under **Additional coding standards** in the overview, link guides already present in the project and identify the target when several targets share a repository. Mark recommendations awaiting a copy as pending and use `N/A` when no guides apply.

## Hand off for review

Report the overview path or provide its Markdown, summarize the remaining decisions, and list the recommended guides. Stop there for the owner's review. After the overview is agreed, use `feature plan` when the owner requests feature specs. Follow [AGENTS.md](AGENTS.md) and the [feature workflow](skills/feature/SKILL.md) for implementation.
