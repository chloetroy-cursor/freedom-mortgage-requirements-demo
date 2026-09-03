# Freedom Mortgage Requirements Demo

This private, synthetic demo shows how a product lead can move from an approved
Intake Request to a governed, traceable BRD → team-owned PRDs → FRD in Cursor.
It contains no customer, borrower, underwriting, or production data.

## Demo scenario

**Rate Savings Alert:** Let an authenticated Freedom Account customer enroll in
an alert that directs them to a personalized offer when the existing offer
service indicates there may be an opportunity to lower their payment.

The scenario is fictional but grounded in public Freedom Mortgage experiences.
Cursor does not calculate eligibility, rates, savings, or underwriting outcomes.

## Workspace

Open `freedom-mortgage-demo.code-workspace` to load:

- This repository: the shared product-documentation and decision record.
- `freedom-mortgage-account-context-demo`: Freedom Account team context.
- `freedom-mortgage-notifications-context-demo`: notification-team context.

GitHub is the versioned source of truth. Cursor works from the repositories open
in the workspace and from context explicitly attached to a conversation.

## Repository contents

- `inputs/`: synthetic Intake Request and discovery evidence.
- `templates/`: lightweight BRD, PRD, and FRD templates.
- `requirements/`: documents created during the live workflow.
- `decisions/`: approved scope decisions.
- `handoffs/`: Jira-ready work and Snowflake LOE inputs.
- `prompts/`: the exact live-demo prompts.
- `.cursor/rules/`: reusable quality and governance instructions.

Start the live demo from `main`. The `demo-complete` branch is the recovery path
and shows the intended final requirements package.
