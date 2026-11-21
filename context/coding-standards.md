# Shared coding standards

These rules apply across projects. Use [the project overview](project-overview.md) for product requirements and chosen technologies. Use the repository's manifests, lockfile, scripts, and CI for installed versions and runnable checks.

## Code organization

- Follow existing naming, formatting, and module boundaries. Reuse nearby components, helpers, and patterns before introducing new ones.
- Keep business rules separate from rendering, routing, and storage when the behavior can be tested independently. Keep HTTP handling and persistence details at their boundaries.
- Use the project's type system and configuration. Narrow uncertain input at its boundary and keep interface contracts explicit.
- Prefer small changes with clear names and one responsibility per function or component. Add a dependency or abstraction when the task has a concrete need for it.
- For a fix, trace the cause, test the corrected behavior, and keep unrelated cleanup outside the change.

## UI

- Follow the existing design system and tokens. Consult [the screenshot references](screenshots/) for relevant ideas about visual hierarchy, composition, and density. Adapt those ideas to the product. Use the spec for interactions.
- Use controls suited to the target platform. Provide accessible names and support the expected input methods with visible focus where applicable. Keep content usable at the supported screen sizes and text directions.
- Cover relevant loading, empty, success, and failure states. Make errors actionable and keep user input when a failed action can be retried.
- For UI changes, run the app and verify the affected flow when the environment permits. Check representative screen sizes and applicable states from the spec. Verify the input and focus behavior of changed controls.

## Data and server boundaries

- Validate external input and enforce authentication and resource-level authorization on the server wherever access is required. Apply ownership constraints in data access.
- Return useful client-facing errors and keep sensitive values out of responses, logs, source, and docs. Use placeholders in example configuration.
- Change persistent schemas through the repository's migration process. Account for existing data and safe retry behavior when a request or job can run again.

## Verification

- Discover commands in the project README, manifests, and CI. Use the package manager indicated by the repo. Follow the Context7 and version checks in [AGENTS.md](../AGENTS.md) when writing code, including tests and scripts, or installing packages.
- Link tests to the acceptance criteria and [domain rules](project-overview.md#domain-rules). Cover relevant success, boundary, failure, and permission cases. Use test data and configured test environments.
- Before `complete`, run the checks required by the spec and the project's relevant configured checks, such as lint, type check, test, and build. Execute a check only when the repo defines it or a documented equivalent.
- Report the commands and actual results. Call out unavailable checks and what remains for manual verification.
