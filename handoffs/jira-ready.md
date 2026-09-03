# Jira-Ready Requirements Handoff

> Synthetic review artifact. Copy manually only after BRD, PRD, and FRD approval.
> This file does not represent Jira synchronization or delivery authorization.

## EPIC-RSA-1 — Enrollment and preference control

**Outcome:** Authenticated customers can enroll, see their current preference,
and withdraw.

**Parent requirements:** BR-001; BR-005  
**Functional requirements:** FR-001; FR-002; FR-003  
**Dependencies:** Freedom Account preference capability  
**Initial stories:** RSA-101; RSA-102

### RSA-101 — Enroll in Rate Savings Alert

- Present authenticated enrollment choice.
- Require explicit confirmation.
- Record and display the current enrolled state.
- Report enrollment completion.
- Do not claim success when recording fails.

### RSA-102 — View and change alert preference

- Display current preference without assuming an unavailable state.
- Allow an enrolled customer to withdraw.
- Confirm a successful change.
- Make withdrawal effective for later alert evaluation.

## EPIC-RSA-2 — Offer-to-email workflow

**Outcome:** An authoritative offer event can produce an approved email for a
currently enrolled customer, subject to contact controls.

**Parent requirements:** BR-002; BR-003; BR-004; BR-005  
**Functional requirements:** FR-004; FR-005; FR-006; FR-007; FR-008  
**Dependencies:** Offer service; Notifications; customer-language review  
**Blocker:** DEC-002 frequency and suppression  
**Initial stories:** RSA-201; RSA-202; RSA-203; RSA-204

### RSA-201 — Validate an alert request

- Validate current enrollment.
- Use the authoritative offer indicator without reinterpretation.
- Reject missing, stale, withdrawn, or invalid conditions with a reason.

### RSA-202 — Apply frequency and repeat-alert suppression

- Apply the maximum frequency and repeat-alert window.
- Record a suppression reason.
- Acceptance criteria remain blocked until DEC-002 is approved.

### RSA-203 — Deliver approved email safely

- Use the approved template and non-sensitive variables.
- Include the secure authenticated destination.
- Do not include personalized financial details.
- Do not request or send SMS in phase one.

### RSA-204 — Open authenticated offer details

- Require authentication before personalized content appears.
- Handle an unavailable destination without exposing stale information.

## EPIC-RSA-3 — Pilot measurement and operations

**Outcome:** Sponsors can review enrollment, delivery, and authenticated
engagement for the pilot.

**Parent requirements:** BR-006  
**Functional requirements:** FR-009; FR-010  
**Dependencies:** Freedom Account analytics; Notifications reporting  
**Blocker:** DEC-003 success thresholds  
**Initial stories:** RSA-301

### RSA-301 — Report pilot events

- Report enrollment and withdrawal.
- Report email delivery, failure, open, and link selection.
- Report authenticated offer-detail visits originating from an alert.
- Keep success evaluation open until DEC-003 is approved.

## Handoff checks

- [ ] BRD baseline approved.
- [ ] Both PRDs reviewed by owning teams.
- [ ] DEC-002 resolved.
- [ ] Customer language approved.
- [ ] FRD functionally reviewed.
- [ ] Jira owners, labels, sequencing, and target dates assigned by accountable
      humans.
- [ ] Refined LOE run through Freedom Mortgage's separate process.
