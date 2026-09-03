# Product Requirements Document: Notifications

## Document control

- **Status:** Draft for team review
- **Owning team:** Notifications
- **Parent BRD:** `requirements/brd/rate-savings-alert-brd.md`
- **Decision incorporated:** DEC-001

## Product objective

Deliver an approved email to an enrolled customer after an authoritative offer
event, without exposing personalized financial details, and report delivery and
engagement outcomes to the product initiative.

## Users and jobs to be done

- As an enrolled customer, I want a clear, trustworthy alert that takes me to my
  authenticated account.
- As a product owner, I want channel scope and customer preferences respected.
- As an operations partner, I want delivery outcomes visible for the pilot.

## Product scope

### Included

- Phase-one email delivery.
- Approved non-sensitive template content.
- Secure authenticated destination.
- Preference, frequency, and suppression checks.
- Delivery and engagement reporting.

### Excluded

- SMS delivery, consent, opt-out, or quiet-hours behavior in phase one.
- Personalized financial details in an email.
- Offer eligibility or savings calculation.

## Parent business requirements

This PRD owns or supports BR-002, BR-003, BR-004, BR-005, and BR-006.

## Product requirements

### PR-NOT-001 — Accept approved alert request

- **Parent:** BR-002; BR-003
- **Behavior:** The notification workflow accepts an email-alert request only
  when it represents an enrolled customer and an authoritative current offer.
- **Acceptance signal:** Incomplete or ineligible requests do not send an email
  and produce a reviewable outcome.
- **Source:** Intake Request; Discovery Notes; both team contexts.
- **Status:** Proposed; exact inputs require functional review.

### PR-NOT-002 — Use approved email template

- **Parent:** BR-003; BR-004
- **Behavior:** The workflow sends an approved email template using only
  non-sensitive variables.
- **Acceptance signal:** No personalized financial detail appears in the message.
- **Source:** Notifications context; Freedom Account context.
- **Status:** Proposed; final language remains open.

### PR-NOT-003 — Link to authenticated details

- **Parent:** BR-004
- **Behavior:** The email directs the customer to the secure Freedom Account
  destination supplied by the product workflow.
- **Acceptance signal:** Personalized details require authentication.
- **Source:** Both team contexts.
- **Status:** Proposed.

### PR-NOT-004 — Report delivery outcome

- **Parent:** BR-006
- **Behavior:** The workflow reports email delivery, failure, open, and link
  selection using a non-sensitive initiative reference.
- **Acceptance signal:** The pilot report can distinguish these outcomes.
- **Source:** Discovery Notes; Notifications context.
- **Status:** Proposed.

### PR-NOT-005 — Respect current preference

- **Parent:** BR-005
- **Behavior:** The workflow checks the current alert preference before sending
  and stops future alerts after withdrawal.
- **Acceptance signal:** A withdrawn customer does not receive a later alert.
- **Source:** Discovery Notes; Notifications context.
- **Status:** Proposed.

### PR-NOT-006 — Exclude SMS

- **Parent:** BR-003
- **Behavior:** Phase-one execution must not request or send an SMS for this
  initiative.
- **Acceptance signal:** No phase-one path invokes SMS delivery.
- **Source:** DEC-001; Notifications context.
- **Status:** Proposed following approved synthetic decision.

## Experience and workflow

1. Receive an approved request representing current enrollment and offer status.
2. Apply current preference and approved suppression rules.
3. Reject or record requests that do not meet required conditions.
4. Render the approved non-sensitive email template.
5. Send the email with the authenticated destination.
6. Report delivery and engagement outcomes.

## Dependencies and sequencing

- Freedom Account supplies the current preference and authenticated destination.
- Offer status remains authoritative outside this team's scope.
- DEC-002 must define frequency and repeat-alert suppression.
- Customer-language review is required before release.

## Analytics and operational needs

- Delivery, failure, open, and link-selection outcomes.
- A non-sensitive reference that supports initiative reporting.
- Failed-delivery ownership and response remain open.

## Assumptions

- The delivery capability can accept the required non-sensitive inputs.
- The approved template can be configured before release.

## Open questions

- DEC-002 frequency and suppression.
- Final approved template language.
- Operational owner for failed delivery.
- Retention period for initiative-level delivery events.

## BRD impact review

The repository constraint originally conflicted with email-and-SMS scope.
DEC-001 approved email-only phase one and explicit SMS exclusion. The BRD and
both PRDs now reflect that decision. No additional BRD change is proposed.

## Team review checkpoint

Notifications, Freedom Account, Analytics, and applicable customer-language
reviewers must validate this draft before FRD approval.
