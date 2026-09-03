# Freedom Mortgage: 60-Minute Live Demo Click Path

## The one thing to prove

A nontechnical product lead can turn an approved Intake Request into a
traceable BRD → team-owned PRDs → FRD while remaining in control of every scope
decision.

Use this sentence near the beginning:

> Your process has the right shape: governed intake, progressive detail,
> cross-team ownership, and human approval. Today we are not redesigning it; we
> are showing those steps in action.

Do not describe this as a coding demo. It is a product-workflow demo.

## Ten-minute rehearsal card

1. **Slide 3:** “We are showing steps 9–14 in action; Cursor proposes, you
   decide.”
2. **GitHub:** Show the central requirements repo, then the two team-context
   repos. Macro plan in the center; team-owned micro plans around it.
3. **Cursor:** `File → Open Workspace from File…` and choose
   `freedom-mortgage-demo.code-workspace`.
4. **Ask:** Attach the two inputs plus both team READMEs. Run Prompt 1 and point
   to the SMS conflict before any file is written.
5. **Agent:** Run Prompt 2. Review the BRD diff, IDs, sources, open questions,
   and signoff checkpoint.
6. **Agent:** Run Prompt 3. Review the two team PRDs and their parent BRD IDs.
7. **Ask:** Run Prompt 4. Let Cursor propose the smallest cross-team scope
   change without editing files.
8. **Human decision:** Approve email-only phase one aloud. Run Prompt 5 and
   review the synchronized BRD/PRD/decision-log diffs.
9. **Agent:** Run Prompts 6 and 7. Show FRD traceability, Jira-ready work, and
   blank Snowflake estimate fields.
10. **Git:** Open Source Control and show the review set. Close with: “The value
    is connected judgment and traceability, not more pages.”

## Before attendees join

1. Confirm all three repositories are on `main` and have no local changes:
   - `freedom-mortgage-requirements-demo`
   - `freedom-mortgage-account-context-demo`
   - `freedom-mortgage-notifications-context-demo`
2. Keep the repositories private.
3. Open these browser tabs:
   - [Requirements repository](https://github.com/chloetroy-cursor/freedom-mortgage-requirements-demo)
   - [Freedom Account context](https://github.com/chloetroy-cursor/freedom-mortgage-account-context-demo)
   - [Notifications context](https://github.com/chloetroy-cursor/freedom-mortgage-notifications-context-demo)
   - [Completed recovery branch](https://github.com/chloetroy-cursor/freedom-mortgage-requirements-demo/tree/demo-complete)
4. Open Freedom's process deck to slide 3, “Definition & Planning.”
5. Open Cursor with `freedom-mortgage-demo.code-workspace`.
6. Expand all three repository roots in the Explorer.
7. Open `prompts/demo-prompts.md` in a background tab for copy/paste.
8. Increase editor and browser zoom enough for screen sharing.
9. Close terminals, personal tabs, notifications, and unrelated repositories.
10. Start a fresh Cursor conversation so the audience sees context added
    deliberately.

The exact label for accepting an Agent diff can vary slightly by Cursor build
(`Keep`, `Accept`, or `Accept All`). The action is the same: review the proposed
file change before retaining it.

## 0:00–0:04 — Set expectations and reduce anxiety

### Screen

Freedom's process deck, slide 3.

### Click

Point only to steps 9–14:

- Project Setup
- Detailed Discovery
- BRD
- PRD
- PRD Validation & Feedback
- FRD

### Say

> You have already seen the full process, so I am not going to reteach it. We
> will start where an initiative has been approved for detailed discovery and
> show these steps in action.

> AI can produce different drafts, which is why the human review points in your
> process matter. Cursor proposes; you decide. You are always in control.

### Do not cover

- Intake governance, executive approval, or the initial Snowflake LOE in detail.
- Coding, deployment, AWS, or the future hackathon.
- A generic Cursor feature tour.

## 0:04–0:09 — Show GitHub as the shared context store

### Screen

Open the requirements repository in GitHub on `main`.

### Click path

1. Click `inputs`.
2. Open `intake-request.md`.
3. Return to the repository root.
4. Click `templates`.
5. Point to the BRD, PRD, and FRD templates.
6. Return to the root and point to `.cursor/rules`, `decisions`, `requirements`,
   and `handoffs`.
7. Open the Freedom Account repository in the next browser tab.
8. Point to its README without reading every constraint.
9. Open the Notifications repository and point to its README without revealing
   the SMS conflict yet.

### Say

> This first repository is the initiative's shared product record: source
> material, decisions, requirements, and handoffs. GitHub gives the team one
> versioned source of truth rather than separate copies in inboxes.

> The other repositories represent context owned by individual teams. The
> shared initiative is the macro plan; each team's PRD is its micro plan. We
> bring the relevant repositories into one Cursor workspace without removing
> team ownership.

> GitHub stores and versions the information. Cursor works from the repositories
> we open and the context we explicitly provide; it does not automatically read
> every repository in the organization.

### Show how a repository connects, without recloning live

1. In GitHub, click **Code**.
2. Select **Local** and **HTTPS**.
3. Point to the copy button.
4. Say:

> The one-time setup is: copy this URL, open Cursor's Command Palette, run
> `Git: Clone`, paste the URL, and choose a local folder. I prepared that step so
> we can spend our time on the product workflow.

If they ask for the exact keys: press `⌘⇧P`, type `Git: Clone`, select it, paste
the HTTPS URL, choose the parent folder, and click **Open** when cloning finishes.

If they ask how the repository itself is created: GitHub's top-right **+ → New
repository**, choose the approved owner, enter the repository name, select the
required visibility, and follow Freedom's internal provisioning rules. Do not
create a fourth repository during this session.

## 0:09–0:13 — Add the three repositories to Cursor

### Recommended live path

1. Switch to Cursor.
2. Click **File → Open Workspace from File…**
3. Choose `freedom-mortgage-demo.code-workspace`.
4. In the Explorer, point to the three top-level roots:
   - Requirements and decisions
   - Freedom Account team context
   - Notifications team context
5. Open `freedom-mortgage-demo.code-workspace` and briefly show that it contains
   three folder paths.

### Explain the manual equivalent

1. **File → Open Folder…** and choose the requirements repository.
2. **File → Add Folder to Workspace…** and choose the Freedom Account context
   repository.
3. Repeat **File → Add Folder to Workspace…** for Notifications.
4. Optionally use **File → Save Workspace As…** so the same collection opens
   together next time.

Do not perform the manual equivalent after opening the prepared workspace. Show
the menu path or explain it; avoid creating an unnecessary second workspace.

### Say

> Product owns the shared requirements repository. Each delivery team keeps its
> own context. Cursor can now compare the shared plan with the relevant team
> constraints in one place.

> This is usually a one-time setup. A product person can partner with an
> engineering teammate for the initial repository access, then work in this
> saved workspace day to day.

> In this workflow, the saved folder collection is the Cursor project. There is
> no separate BRD system or “Create BRD” button inside Cursor; Agent creates a
> Markdown file in the shared repository for human and Git review.

## 0:13–0:19 — Analyze the Intake Request before writing

### Click path

1. Open `inputs/intake-request.md`.
2. Open `inputs/discovery-notes.md`.
3. Open Cursor Agent by clicking the Agent icon or pressing `⌘I`.
4. Click the mode selector beside the prompt box and choose **Ask**.
5. Type `@` and attach:
   - `inputs/intake-request.md`
   - `inputs/discovery-notes.md`
   - `README.md` from **Freedom Account team context**
   - `README.md` from **Notifications team context**
6. Confirm all four context pills show the intended repository.
7. Paste the prompt below and submit.

### Prompt 1 — discovery

> Read the attached Intake Request, discovery notes, and both team-context
> documents. Do not create or edit files. Return only: confirmed facts,
> contradictions, missing decisions, impacted teams, dependencies, and your
> recommended BRD/PRD document split. Cite the source file for every finding.
> Treat plausible answers as open questions and stop for my decisions.

### Expected result

Cursor should identify:

- One shared BRD.
- Separate Freedom Account and Notifications PRDs.
- Cross-team offer-service and analytics dependencies.
- The Intake Request asks for email and SMS.
- Notifications context says SMS is not ready for phase one.
- Frequency, suppression, and success thresholds remain open.

### Point out

> We did not ask Cursor to start writing. We asked it to find what the product
> owner needs to decide. Ask mode is read-only, so this is a safe first step for
> learning a new initiative.

Do not resolve SMS yet. Say:

> Keep SMS visible as a pending scope decision. We will let the team-level work
> demonstrate why that feedback loop exists.

## 0:19–0:27 — Create and review the BRD

### Click path

1. In the same Agent conversation, change the mode selector from **Ask** to
   **Agent**.
2. Type `@` and attach `templates/brd-template.md`.
3. Paste the prompt and submit.

### Prompt 2 — BRD

> Using only the attached sources and `templates/brd-template.md`, create
> `requirements/brd/rate-savings-alert-brd.md`. Define business outcomes,
> in-scope and out-of-scope boundaries, impacted teams, constraints, risks, and
> open questions. Use stable IDs beginning with `BR-001` and include a source
> and status for every requirement. Preserve email and SMS as the initial
> requested scope, but mark SMS as an unresolved cross-team decision. Do not
> invent metrics, policy, approvals, dates, or system behavior. Do not represent
> discovery approval as final BRD signoff. Create only the BRD and stop for my
> review.

### Review clicks

1. Click **Review changes** in the Agent response.
2. Select `requirements/brd/rate-savings-alert-brd.md`.
3. Scroll the diff and point out:
   - Business outcome rather than implementation.
   - Stable `BR-###` IDs.
   - Sources and statuses.
   - Explicit assumptions and open questions.
   - The approval checkpoint.
4. Keep/accept the file if it follows the prompt.
5. Open the new BRD from the Explorer.

If Cursor invents a numeric target or approval, do not accept it. In the prompt
box say:

> Remove the unsupported target or approval. Mark it as an open question owned
> by the product owner or sponsor, then show me the corrected diff.

### Say

> High quality here does not mean “long.” It means the reader can distinguish
> evidence, assumptions, unresolved questions, and approved scope.

## 0:27–0:35 — Turn one macro BRD into two team PRDs

### Click path

1. Keep **Agent** mode selected.
2. Attach:
   - The new BRD.
   - `templates/prd-template.md`.
   - Both team-context READMEs.
3. Paste the prompt and submit.

### Prompt 3 — team PRDs

> Create `requirements/prds/freedom-account-prd.md` and
> `requirements/prds/notifications-prd.md` from the reviewed BRD,
> `templates/prd-template.md`, and each team's context. Each PRD must define the
> team's product behavior and rationale, preserve parent `BR-###` IDs, name
> dependencies, and keep unresolved questions visible. Do not silently change
> BRD scope. If a team constraint affects requested business scope, document the
> impact and proposed smallest change, then stop for team review.

### Review clicks

1. Click **Review changes**.
2. Open the Freedom Account PRD diff.
3. Point from one `PR-ACC-###` requirement to its parent `BR-###`.
4. Open the Notifications PRD diff.
5. Point from one `PR-NOT-###` requirement to its parent.
6. Show the Notifications constraint and BRD impact-review section.
7. Keep/accept the two PRD files only after the parent IDs and open decision are
   visible.

### Say

> The BRD is the shared macro plan. The PRDs give each team an owned micro plan
> without losing the reason the work exists.

## 0:35–0:42 — Demonstrate cross-team validation and human control

### Click path

1. Change the mode selector to **Ask**.
2. Attach the BRD and both PRDs.
3. Paste Prompt 4.

### Prompt 4 — impact analysis

> Compare the BRD and both PRDs against the original inputs and team context.
> Do not edit files. Show only: uncovered business requirements,
> contradictions, cross-team dependencies, and proposed BRD changes. For every
> proposed change, list the affected requirement IDs and documents. Recommend
> the smallest consistent change and stop for a human decision.

### Expected result

Cursor should recommend email-only phase one and explicit SMS deferral because
the Notifications repository does not establish the required SMS capability.

### Make the decision aloud

> I am the product owner for this exercise. I approve email-only for phase one.
> SMS is deferred until consent and messaging capability are separately
> approved. I am making that decision; Cursor is not.

### Apply the decision

1. Change back to **Agent** mode.
2. Paste Prompt 5.

### Prompt 5 — propagate the approved decision

> Record DEC-001 in `decisions/decision-log.md` as a human-approved synthetic
> demo decision: phase one supports email; SMS is deferred pending separately
> approved consent and messaging capability. Update the BRD and both PRDs with
> the smallest consistent change. Preserve existing requirement IDs, update
> source and status fields, list every affected document, and summarize the
> diffs. Do not resolve DEC-002 or DEC-003. Stop for my review.

### Review clicks

1. Click **Review changes**.
2. Verify only the decision log, BRD, and two PRDs changed.
3. Open each diff from the review list.
4. Confirm the same decision appears consistently while IDs remain stable.
5. Keep/accept the four files.

### Say

> This is the feedback loop in Freedom's process. A team discovery did not
> quietly change business scope. Cursor showed the impact, a human approved the
> smallest change, and the connected documents were updated together.

## 0:42–0:49 — Create the FRD

### Click path

1. Keep **Agent** mode selected.
2. Attach:
   - Updated BRD.
   - Both updated PRDs.
   - `decisions/decision-log.md`.
   - `templates/frd-template.md`.
3. Paste the prompt and submit.

### Prompt 6 — FRD

> Create `requirements/frd/rate-savings-alert-frd.md` from the updated BRD,
> both reviewed PRDs, the decision log, and `templates/frd-template.md`. Use
> stable `FR-###` IDs and map every functional requirement to its parent PRD
> IDs and one primary epic. Include functional behavior, exceptions,
> dependencies, initial user stories, acceptance criteria, and verification
> methods. Keep unresolved decisions visible. Do not invent technical
> architecture, legal conclusions, estimates, points, sprints, or dates. Stop
> for functional review.

### Review clicks

1. Click **Review changes**.
2. Open the FRD diff.
3. Point out one chain:
   - `BR-###` business need.
   - `PR-ACC-###` or `PR-NOT-###` team behavior.
   - `FR-###` functional behavior.
   - Epic and story.
4. Point out that unresolved frequency/suppression behavior remains blocked
   rather than guessed.
5. Keep/accept the FRD.

### Say

> The FRD makes the approved product behavior executable, but it still does not
> invent the answers owned by product, engineering, compliance, or estimation.

## 0:49–0:53 — Create traceability and downstream handoffs

### Click path

1. Keep **Agent** mode selected.
2. Paste Prompt 7.

### Prompt 7 — traceability, Jira, and Snowflake inputs

> Create `requirements/traceability.md`, `handoffs/jira-ready.md`, and
> `handoffs/snowflake-loe-input.csv`. Show BRD → PRD → FRD → epic/story
> coverage and explicitly list gaps or blockers. The Jira handoff must be
> review-ready but must not claim synchronization or approval. The Snowflake
> file may contain scope, dependency, uncertainty, and readiness inputs, but no
> effort, cost, points, sprint, or date estimates. Stop for my review.

### Review clicks

1. Review and keep/accept the three files.
2. Open `requirements/traceability.md` and point to one end-to-end chain.
3. Open `handoffs/jira-ready.md` and point to epics, stories, dependencies, and
   blockers.
4. Open `handoffs/snowflake-loe-input.csv` and point out the deliberately empty
   estimate fields.

### Say

> Cursor prepares governed inputs for the systems in your process. It does not
> replace Jira ownership, Snowflake estimation, or human approval.

Do not attempt a live Jira or Snowflake integration. Freedom's supplied process
describes an initially manual Cursor-to-Jira handoff.

## 0:53–0:56 — Show Git review as the shared record

### Click path

1. Click the **Source Control** icon in Cursor's activity bar.
2. Point to the list of changed and newly created files.
3. Click one file to open its Git diff.
4. Point to additions and removals from the approved SMS decision.
5. Return to the Explorer.

### Say

> Cursor checkpoints can help during an individual session, but the shared
> review record is Git: commits, branches, and pull requests. The team would
> commit these changes only after the relevant review checkpoints.

Do not commit or push the live-generated files during the session. Leave them as
a visible review set.

## 0:56–1:00 — Close and open questions

### Closing recap

> We started with an approved Intake Request, found missing decisions before
> writing, created one BRD and two team-owned PRDs, sent a team constraint back
> through human approval, produced the FRD, and prepared Jira and LOE inputs.

> The value is not that AI wrote more pages. The value is that product judgment,
> sources, dependencies, decisions, and traceability stayed connected.

### Invite questions

> What part of this flow feels hardest to apply to one of your current projects:
> getting context together, asking the first question, reviewing the output, or
> coordinating across teams?

## Questions to expect

### “Can Cursor see every GitHub repository?”

No. Cursor works with the repositories opened in the workspace and context
provided to the conversation. Show the three Explorer roots and the attached
context pills.

### “How do we stop it from making things up?”

Use source files, rules, explicit “do not invent” constraints, open-question
labels, read-only analysis first, and human diff review. Show the project rule
and a missing decision that remained open.

### “What if two teams disagree?”

Ask Cursor for an impact analysis without edits. The accountable human decides;
then Agent propagates the approved change while preserving IDs. Show DEC-001.

### “Does it automatically update Jira or Snowflake?”

Not in this demo. Cursor prepares structured, reviewable handoffs consistent
with Freedom's supplied process. Any future integration depends on approved
administration, authentication, and permissions.

### “Is GitHub required?”

Cursor can work with local files, but Freedom's multi-team design uses GitHub to
share, version, and review durable project context. Avoid presenting local
Cursor checkpoints as a substitute for shared Git history.

### “Is our content used to train models?”

With Cursor Privacy Mode enabled, code is not used to train Cursor or model
providers. Context still leaves the device for inference, so never say “no data
leaves the laptop.” Refer detailed security questions to the approved Cursor
security and privacy documentation and the account team.

### “Will this replace the product or BA role?”

No. This flow depends on product judgment to define outcomes, resolve ambiguity,
approve scope, and validate customer needs. The SMS decision is the concrete
example.

## Recovery path

### If an Agent response is slow

1. Stop the request.
2. Say:

> Drafts can vary, which is exactly why we work from sources and review them.
> I have the approved exercise output ready so we can keep moving.

3. Switch to the pre-opened
   [completed recovery branch](https://github.com/chloetroy-cursor/freedom-mortgage-requirements-demo/tree/demo-complete)
   in the browser.
4. Open the artifact for the current stage and continue the click path from its
   review points.

### If a generated file is wrong

1. Do not keep/accept the incorrect diff.
2. Point to the unsupported statement.
3. Ask Cursor to remove it, label it as an assumption/open question, or cite the
   source.
4. Review the corrected diff.

This is a successful human-in-the-loop moment, not a demo failure.

### If the Cursor workspace is lost

1. Click **File → Open Workspace from File…**
2. Select `freedom-mortgage-demo.code-workspace`.
3. Reopen Agent and continue from the current files.

## Support documentation

- [Cursor context](https://cursor.com/help/customization/context)
- [Cursor rules](https://cursor.com/docs/rules)
- [Git and version control](https://cursor.com/help/integrations/git)
- [Privacy](https://cursor.com/help/security-and-privacy/privacy)

## Final guardrails

- Use “Intake Request” verbally; Freedom's deck alternates between IIR and IRR.
- Never show or enter real customer, borrower, employee, or production data.
- Do not claim the synthetic team constraints describe production systems.
- Do not claim the generated documents are approved because they exist.
- Do not invent policy, customer-language approval, metrics, or estimates.
- Do not spend more than five minutes on repository mechanics.
- Do not demonstrate conceded ground such as autocomplete or generic IDE polish.
- Keep returning to: **Cursor proposes; the product owner decides.**
