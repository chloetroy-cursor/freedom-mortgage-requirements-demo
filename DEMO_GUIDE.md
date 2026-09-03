# Freedom Mortgage Live Demo Guide

## Thesis

An approved Intake Request can become a governed and traceable BRD → team PRDs
→ FRD while product people remain responsible for every scope decision.

## What the audience should remember

- Cursor accelerates drafting, comparison, and change propagation.
- GitHub preserves shared context, versions, and review history.
- The product owner—not the model—resolves ambiguity and approves scope.
- Team discoveries flow back to the BRD instead of creating silent drift.

## 50-minute demonstrated flow

1. **Orient (2 minutes):** Show Freedom's process slide 3 and focus on steps
   9–14. Steps 1–8 have already approved detailed discovery.
2. **Context (4 minutes):** Open the three-repository workspace. Explain that
   the central repository owns shared requirements while teams retain their own
   context.
3. **Discovery (6 minutes):** Run prompt 1 in Ask mode. Let Cursor find the SMS
   conflict and open decisions before it writes anything.
4. **BRD (7 minutes):** Run prompt 2. Review business outcomes, boundaries,
   stable IDs, assumptions, and the explicit signoff checkpoint.
5. **PRDs (8 minutes):** Run prompt 3. Show one BRD becoming two team-owned
   product plans with parent IDs.
6. **Feedback loop (8 minutes):** Run prompt 4, make the human decision to defer
   SMS, then run prompt 5. Review the synchronized diffs.
7. **FRD and handoffs (8 minutes):** Run prompts 6 and 7. Show direct mapping to
   epics/stories and structured inputs for Jira and refined LOE.
8. **Review (3 minutes):** Show the Git diff. Reinforce that a reviewed commit or
   PR—not a Cursor checkpoint—is the shared record.
9. **Questions (remaining time):** Invite attendees to connect the pattern to a
   current or dummy initiative.

## Opening sentence

> Your process has the right shape: governed intake, progressive detail,
> cross-team ownership, and human approval. Today we are not redesigning it; we
> are showing those steps in action.

## Language to use

- “Cursor proposes; the product owner decides.”
- “This is a synthetic example with no customer data.”
- “GitHub is the versioned source of truth.”
- “This question stays open until the named owner answers it.”
- “We preserve traceability as requirements become more detailed.”

## Avoid

- Do not demonstrate steps 1–8, coding, AWS deployment, or the future hackathon.
- Do not claim that opening GitHub grants Cursor access to every repository.
- Do not claim that generated content is automatically approved or audited.
- Do not improvise a live Jira or Snowflake integration.
- Do not let Cursor invent metrics, legal conclusions, or delivery estimates.
- Do not explain repository mechanics longer than the product workflow itself.

## Recovery path

If generation is slow or an output diverges:

1. Stop the request.
2. Explain that probabilistic drafts are why review gates exist.
3. Switch to the `demo-complete` branch.
4. Continue from the corresponding completed artifact.

The recovery reinforces the human-in-the-loop message rather than breaking it.
