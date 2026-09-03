# Live Demo Prompts

Attach the named files through Cursor's `@` context picker. Keep the two context
repositories open in the workspace.

## 1. Discover before drafting — Ask mode

> Read `inputs/intake-request.md`, `inputs/discovery-notes.md`, and the README
> from each team-context repository. Do not draft a requirements document yet.
> Return: confirmed facts, contradictions, missing decisions, impacted teams,
> dependencies, and your recommended document split. Cite the source file for
> every finding. Stop for my answers.

Expected moment: Cursor finds that the Intake Request asks for email and SMS,
while the Notifications team says SMS is not ready for phase one.

## 2. Draft the BRD — Agent mode

> Using only the approved inputs and `templates/brd-template.md`, create
> `requirements/brd/rate-savings-alert-brd.md`. Use stable IDs beginning at
> `BR-001`. Preserve open questions, label assumptions, and do not represent
> discovery approval as final scope signoff. Stop after creating the BRD so I
> can review the diff.

For the rehearsed path, tell Cursor that SMS remains a pending scope decision.

## 3. Create team-owned PRDs — Agent mode

> Using the reviewed BRD, `templates/prd-template.md`, and both team-context
> READMEs, create one PRD for the Freedom Account team and one for the
> Notifications team under `requirements/prds/`. Every product requirement must
> include its parent `BR-###` ID. If team context changes business scope, report
> the impact instead of silently editing the BRD. Stop for team review.

## 4. Validate scope across teams — Ask mode

> Compare the BRD and both PRDs against all source context. Show only uncovered
> business requirements, contradictions, cross-team dependencies, and proposed
> BRD changes. For each proposed change, list every affected requirement and
> document. Do not edit files.

## 5. Record the human decision — Agent mode

Use this after verbally choosing email-only for phase one:

> Record DEC-001 as approved: phase one supports email; SMS is explicitly
> deferred pending a separately approved consent and messaging capability.
> Update the BRD and both PRDs with the smallest consistent change. Preserve
> requirement IDs, update source/status fields, and summarize the diffs. Do not
> resolve DEC-002 or DEC-003.

## 6. Produce the FRD — Agent mode

> Using the approved BRD, both reviewed PRDs, the decision log, and
> `templates/frd-template.md`, create
> `requirements/frd/rate-savings-alert-frd.md`. Map each `FR-###` requirement to
> parent PRD IDs and one primary epic. Include stories, acceptance criteria,
> dependencies, exceptions, and verification methods. Do not invent technical
> architecture or estimates. Stop for functional review.

## 7. Check traceability and prepare handoffs — Agent mode

> Create `requirements/traceability.md`, `handoffs/jira-ready.md`, and
> `handoffs/snowflake-loe-input.csv`. Show BRD → PRD → FRD → epic/story coverage.
> Flag gaps rather than inventing requirements. The Snowflake file may contain
> scope and dependency inputs but no effort, cost, points, sprint, or date
> estimates.
