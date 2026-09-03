# Live Demo Prompts

Attach the named files through Cursor's `@` context picker. Keep the two context
repositories open in the workspace.

## 1. Discover before drafting — Ask mode

> Read the attached Intake Request, discovery notes, and both team-context
> documents. Do not create or edit files. Return only: confirmed facts,
> contradictions, missing decisions, impacted teams, dependencies, and your
> recommended BRD/PRD document split. Cite the source file for every finding.
> Treat plausible answers as open questions and stop for my decisions.

Expected moment: Cursor finds that the Intake Request asks for email and SMS,
while the Notifications team says SMS is not ready for phase one.

## 2. Draft the BRD — Agent mode

> Using only the attached sources and `templates/brd-template.md`, create
> `requirements/brd/rate-savings-alert-brd.md`. Define business outcomes,
> in-scope and out-of-scope boundaries, impacted teams, constraints, risks, and
> open questions. Use stable IDs beginning with `BR-001` and include a source
> and status for every requirement. Preserve email and SMS as the initial
> requested scope, but mark SMS as an unresolved cross-team decision. Do not
> invent metrics, policy, approvals, dates, or system behavior. Do not represent
> discovery approval as final BRD signoff. Create only the BRD and stop for my
> review.

## 3. Create team-owned PRDs — Agent mode

> Create `requirements/prds/freedom-account-prd.md` and
> `requirements/prds/notifications-prd.md` from the reviewed BRD,
> `templates/prd-template.md`, and each team's context. Each PRD must define the
> team's product behavior and rationale, preserve parent `BR-###` IDs, name
> dependencies, and keep unresolved questions visible. Do not silently change
> BRD scope. If a team constraint affects requested business scope, document the
> impact and proposed smallest change, then stop for team review.

## 4. Validate scope across teams — Ask mode

> Compare the BRD and both PRDs against the original inputs and team context.
> Do not edit files. Show only: uncovered business requirements,
> contradictions, cross-team dependencies, and proposed BRD changes. For every
> proposed change, list the affected requirement IDs and documents. Recommend
> the smallest consistent change and stop for a human decision.

## 5. Record the human decision — Agent mode

Use this after verbally choosing email-only for phase one:

> Record DEC-001 in `decisions/decision-log.md` as a human-approved synthetic
> demo decision: phase one supports email; SMS is deferred pending separately
> approved consent and messaging capability. Update the BRD and both PRDs with
> the smallest consistent change. Preserve existing requirement IDs, update
> source and status fields, list every affected document, and summarize the
> diffs. Do not resolve DEC-002 or DEC-003. Stop for my review.

## 6. Produce the FRD — Agent mode

> Create `requirements/frd/rate-savings-alert-frd.md` from the updated BRD,
> both reviewed PRDs, the decision log, and `templates/frd-template.md`. Use
> stable `FR-###` IDs and map every functional requirement to its parent PRD
> IDs and one primary epic. Include functional behavior, exceptions,
> dependencies, initial user stories, acceptance criteria, and verification
> methods. Keep unresolved decisions visible. Do not invent technical
> architecture, legal conclusions, estimates, points, sprints, or dates. Stop
> for functional review.

## 7. Check traceability and prepare handoffs — Agent mode

> Create `requirements/traceability.md`, `handoffs/jira-ready.md`, and
> `handoffs/snowflake-loe-input.csv`. Show BRD → PRD → FRD → epic/story
> coverage and explicitly list gaps or blockers. The Jira handoff must be
> review-ready but must not claim synchronization or approval. The Snowflake
> file may contain scope, dependency, uncertainty, and readiness inputs, but no
> effort, cost, points, sprint, or date estimates. Stop for my review.
