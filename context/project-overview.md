# {{PROJECT_NAME}} — Project overview

{{ONE_SENTENCE_DESCRIPTION_AND_AUDIENCE}}

<!-- Write the overview in English, even when the discussion uses another
language. Preserve required localized UI copy as examples. Use N/A for
inapplicable sections. Record open decisions and link to authoritative
code or documentation. The shared workflow lives in AGENTS.md. -->

## Problem, audience, and success

<!-- Describe the problem as it exists today, who has it, and what a good
outcome looks like. Use a real scenario. -->

- Problem and impact: {{PROBLEM_AND_CONSEQUENCE}}
- Users and constraints: {{USERS_DEVICES_LANGUAGES_AND_ACCESS_NEEDS}}
- Representative scenario: {{ACTOR_SITUATION_AND_DESIRED_OUTCOME}}

| Goal | Outcome | How and when to measure it |
| --- | --- | --- |
| G1 | {{DESIRED_OUTCOME}} | {{OBSERVABLE_RESULT_AND_VERIFICATION_POINT}} |

## Scope and roadmap

<!-- Describe visible capabilities and give each milestone a completion
condition. Use numeric milestone IDs such as M0 and M1 for feature planning.
Link feature specs as they are written. -->

- MVP: {{CAPABILITIES_AND_BOUNDARIES}}
- After the MVP: {{DEFERRED_CAPABILITIES}}
- Product non-goals and reasons: {{EXPLICIT_EXCLUSIONS_AND_REASONS}}

| Milestone | Outcome and completion criteria | Feature specs |
| --- | --- | --- |
| M0 | {{FOUNDATION_AND_DONE_CRITERIA}} | {{SPEC_IDS_OR_LINKS}} |
| M1 | {{FIRST_USABLE_FLOW_AND_DONE_CRITERIA}} | {{SPEC_IDS_OR_LINKS}} |

## Pages, user flows, and UI references

<!-- Include first use from the initial state through the first useful result.
Consider the applicable empty, loading, failure, and recovery states. -->

| Flow | Starting point and user | Steps and expected outcome | Alternate or failure path |
| --- | --- | --- | --- |
| F1 | {{ROLE_AND_STARTING_STATE}} | {{STEPS_AND_RESULT}} | {{FAILURE_AND_RECOVERY}} |

- Main pages or routes: {{ROUTES_AND_PURPOSES}}
- Design direction and responsive priorities: {{PLATFORMS_LAYOUTS_LANGUAGES_AND_ACCESSIBILITY}}
- Visual references: {{SCREENSHOT_LINKS_UNDER_SCREENSHOTS_AND_WHAT_TO_BORROW_OR_PENDING_OR_NA}}

Use screenshots for visual direction and adapt them to the product. Link each selected file from [screenshots/](screenshots/) and name the screen, state, or layout detail it illustrates. Use `Pending` while references are still being chosen, including when the visual direction is decided. If the project has no browser UI, use `N/A` and state why. For browser UI, use `N/A` only when the owner explicitly asks to proceed without screenshots. Record what they approved and the scope it covers. Keep product behavior in the overview and specs.

## Domain rules

<!-- Give each rule an ID, a concrete result, and a boundary case. Refer
to these IDs in feature specs and their verification cases. -->

- Shared conventions: {{DATES_TIME_ZONES_UNITS_OR_OTHER_RULES}}

| Rule | Condition and expected result | Example and boundary case |
| --- | --- | --- |
| R1 | {{WHEN_THEN_RULE}} | {{INPUT_EXPECTED_RESULT_AND_EDGE_CASE}} |

## Data, permissions, and interfaces

<!-- Link to existing schema or contract files when available. State where
data is owned, who can access it, and how invalid requests are handled. -->

| Entity or interface | Purpose | Ownership, permissions, or contract |
| --- | --- | --- |
| {{ENTITY_API_ACTION_OR_JOB}} | {{PURPOSE_AND_RELATIONSHIPS}} | {{INVARIANTS_ACCESS_RULES_OR_SOURCE_PATH}} |

- Sign-in, roles, and ownership: {{AUTHENTICATION_AND_AUTHORIZATION_MODEL}}
- Sensitive data and lifecycle: {{DATA_SCOPE_RETENTION_DELETION_EXPORT_AND_BACKUP_IF_APPLICABLE}}

## Stack and architecture

<!-- Record the choices and reasons that matter for this project. Use the
manifest or lockfile for exact installed versions. -->

| Area | Technology or path | Responsibility or reason |
| --- | --- | --- |
| App runtime and package manager | {{STACK}} | {{RATIONALE}} |
| UI and routes | {{PATHS_OR_STACK}} | {{RESPONSIBILITIES}} |
| Server and domain logic | {{PATHS_OR_STACK}} | {{RESPONSIBILITIES_AND_BOUNDARIES}} |
| Storage and integrations | {{PATHS_OR_SERVICES}} | {{RESPONSIBILITIES}} |

- Example data flow: {{REQUEST_TO_RESULT}}
- Architecture boundary to protect: {{BOUNDARY_AND_REASON}}
- Additional coding standards: {{LINKS_TO_APPLICABLE_GUIDES_OR_NA}}

## Integrations and operations

<!-- Fill when the app uses external services, configuration, or deployment.
Use configuration names and dummy values. Keep setup commands in the project
README or runbook and use actual package scripts for verification. -->

| Service | Purpose | What happens when it fails | Recovery |
| --- | --- | --- | --- |
| {{SERVICE}} | {{USAGE}} | {{USER_VISIBLE_BEHAVIOR}} | {{RETRY_FALLBACK_OR_MANUAL_STEPS}} |

- Setup, environments, and configuration references: {{README_RUNBOOK_OR_SAFE_CONFIG_PATHS}}
- Deployment, migrations, and rollback: {{RELEASE_AND_RECOVERY_RULES_OR_NA}}

## Quality and review priorities

<!-- Record project-specific behavior and measurable constraints. The shared
verification approach lives in coding-standards.md. -->

| Rule or quality area | Required behavior or threshold | How to verify |
| --- | --- | --- |
| {{RULE_ID_OR_AREA}} | {{OBSERVABLE_EXPECTATION}} | {{AUTOMATED_OR_MANUAL_SCENARIO}} |

- Project-specific review question: {{CHECK_A_REVIEWER_CAN_ANSWER_WITH_EVIDENCE}}

## Open questions, decisions, and references

| Topic | Status | Decision or question | Reason or next step |
| --- | --- | --- | --- |
| {{TOPIC}} | {{OPEN_ASSUMED_OR_DECIDED}} | {{CURRENT_POSITION}} | {{RATIONALE_OR_OWNER_AND_NEXT_STEP}} |

- Glossary or references: {{DOMAIN_TERMS_DESIGNS_SCHEMAS_OR_DOCUMENTATION}}
