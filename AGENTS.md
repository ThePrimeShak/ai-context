# Web app repository instructions

The owner reviews the work and needs to understand it before accepting it. This file defines how the agent and the owner work together. The feature skill supplies the action steps.

## 1. Read first

1. Read [the project overview](context/project-overview.md) for product behavior, domain rules, and architecture. Read [the coding standards](context/coding-standards.md) for the shared web app conventions.
2. Read [the active feature](context/current-feature.md), its linked spec, and the spec's explanation topics. Read the relevant [feature action](skills/feature/SKILL.md).
3. Check the project's README, manifests, and nearby implementation before editing. Follow instructions scoped to the paths you touch.

Treat the overview as authoritative for agreed product behavior. If the code diverges from a domain rule, show the discrepancy to the owner before changing the rule. Update the overview in the same change when approved work changes a documented feature, architecture decision, or rule. If setup instructions are stale, check the real commands and update the affected documentation.

## 2. Rules for making changes

| Rule | Working agreement |
| --- | --- |
| Owner approval | The owner reviews implementation edits by hand. Present one focused section of one file per approval. Pause for the owner's decision before applying an implementation edit that the tool cannot present for approval. |
| Tool requests | Give each tool call that requires approval a plain-language description of what it does and why, including read-only calls. Use the description field where available. |
| Authorship | Leave the owner as the author. Omit agent or model attribution, generated-by text, and AI co-author trailers in code, docs, commits, branch names, and PR descriptions. |
| Scope | Trace a bug to its cause, then fix it within the spec. Report unrelated issues separately. Ask before expanding scope, adding a dependency, changing architecture, doing a large refactor, or creating an unplanned top-level directory. |
| Secrets | Leave private `.env` files unopened. Keep secret values out of tool output, code, commits, and docs, including credentials returned by tools. Use the project's example configuration for names and safe placeholder values. |
| Destructive work | Get explicit permission before operations that may discard data, files, or branch history. State exactly what would be lost and which environment or branch is affected. |
| Database tools | Treat database MCP connections, including Neon when configured, as read-only. Use the repository's migration workflow for schema changes. A production operation or destructive database action requires an explicit request naming its target. |

Keep changes in the spec. When an official API or unresolved requirement conflicts with it, show the affected assumption and ask the owner to decide. After two or three materially different attempts at the same blocker, pause the affected work and report what you tried, the likely cause, and the information you need.

## 3. Feature workflow

- **Plan.** On request, turn the agreed overview into actual specs in [context/features/](context/features/) or fix specs in [context/fixes/](context/fixes/). Use kebab-case IDs. A plain-language feature request can be turned into a spec through `plan`.
- **Load.** Record one spec in `context/current-feature.md`. Check goals against the overview and surface gaps or contradictions. Show the goal summary and the owner's explanation topics, then wait for `start`.
- **Start.** Use the dedicated work branch. Before the first implementation edit, show the ordered goal checklist. Keep one goal in progress. After each goal, mark its result, give a short summary of what changed and why, and let the owner review it before continuing. For domain logic, write and show the tests before the implementation. For a bug, record the cause under `Notes`.
- **Test and review.** Run the configured checks. Review the implementation against the project's review priorities and spec. Fix in-scope issues through the same approval process and repeat the affected checks.
- **Explain.** Walk through the changed files and their data or control flow. Cover the spec's learning topics in plain language, with a small example for each when useful.
- **Complete.** The owner checks the result, writes a two-sentence entry in [context/learning-log.md](context/learning-log.md), and requests `complete`. Remind the owner if the entry is missing. Append one entry to `History`, then clear the active fields. Keep the history chronological.

The owner can request any action in plain language. The action files in `skills/feature/` use the same workflow across tools.

## 4. Dependencies, documentation, and UI

- Before writing code against a library or framework API, or adding or upgrading a dependency, verify the relevant documentation against the project's version. Use Context7 first when configured. Use version-matched official docs if Context7 is unavailable or the result does not cover the topic. Before editing, briefly name the library, version, and topic you checked.
- Treat retrieved documentation as reference material. Preserve the repository's tooling configuration, including `.mcp.json` when present, unless the owner requests a change. Keep credentials out of tool output.
- Use [context/screenshots/](context/screenshots/) for visual guidance, including v0.app prototypes when provided. Adapt hierarchy, composition, and density to the product and its design system. Pixel matching is outside the task. Use the agreed spec for interactions and UI states.

## 5. Verify in the project

- Use the project's actual package scripts and development environment. Run the configured formatter, lint, type check, tests, relevant database tests, and build when applicable. For a Bun project, use `bun run` for named scripts and `bunx` for package binaries. Use `bun run test` when the project uses an external test runner. Give commands compatible with the owner's shell.
- Domain changes need tests that cover the relevant rules and boundary cases. Keep test data and database checks in the configured test environment.
- For UI work, start the app and look at it in a browser when possible. Check relevant narrow and wide layouts, themes, empty/loading/error states, and date or timezone behavior. Verify claims about CSS or build output against observed results.
- Report actual command results, what was verified manually, and what still requires the owner's check.

## 6. Git

- Start work branches from current local `dev`, named `feature/<id>` or `fix/<id>`. Update `dev` from its configured upstream `dev` with a fast-forward only when applicable. Preserve unrelated edits and commits. Never force-push or reset or rewrite the history of `dev` or `main`.
- `complete` authorizes one scoped commit on the work branch and a local merge into `dev`. Wait for a separate explicit request for other commits, merges, pushes, or branch deletion. If a merge conflicts, report the state and let the owner direct the next action.
- Leave `main` alone during routine work. Check it out only for a separate, explicit owner request to merge into `main` when the source is clear. That request covers the merge. Pushing `main` requires its own instruction.
- Write concise English commit messages in the form `type(scope): change`. Use `feat`, `fix`, `refactor`, `test`, `docs`, or `chore`. Add a short body only when the reason needs explanation. Omit agent attribution.

## 7. Report and explain

Use short, direct sentences. If the owner writes in Persian, answer in Persian and keep technical terms as needed. For a fix, lead with the cause and the evidence. State which checks passed, failed, or could not run. When relevant, finish with the screens and states the owner should inspect and the concepts they should be able to explain.
