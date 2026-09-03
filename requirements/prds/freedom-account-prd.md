# Product Requirements Document: Freedom Account

## Document control

- **Status:** Draft for team review
- **Owning team:** Freedom Account
- **Parent BRD:** `requirements/brd/rate-savings-alert-brd.md`
- **Decision incorporated:** DEC-001

## Product objective

Give an authenticated existing customer a clear way to enroll in or leave the
Rate Savings Alert experience, and take an alerted customer securely to current
offer details supplied by the existing offer service.

## Users and jobs to be done

- As an authenticated customer, I want to choose whether to receive an alert.
- As an enrolled customer, I want the alert to take me safely to the relevant
  account experience.
- As a product owner, I want measurable enrollment and engagement without
  changing the offer decision.

## Product scope

### Included

- Authenticated enrollment and withdrawal.
- Current enrollment-state display.
- Use of existing offer status.
- Secure offer-detail destination.
- Enrollment and alert-originated engagement events.

### Excluded

- SMS preferences or delivery in phase one.
- Creating, ranking, or changing personalized offers.
- Showing personalized offer details outside authentication.

## Parent business requirements

This PRD owns or supports BR-001, BR-002, BR-003, BR-004, BR-005, and BR-006.

## Product requirements

### PR-ACC-001 — Present enrollment choice

- **Parent:** BR-001
- **Behavior:** An eligible authenticated customer can see and intentionally
  select an option to enroll in Rate Savings Alert.
- **Acceptance signal:** Enrollment completes and the current state is visible.
- **Source:** Intake Request; Discovery Notes.
- **Status:** Proposed.

### PR-ACC-002 — Preserve current preference

- **Parent:** BR-001; BR-005
- **Behavior:** The account experience reflects the customer's current
  enrollment state and makes duplicate enrollment unnecessary.
- **Acceptance signal:** Reopening the experience shows the current state.
- **Source:** Discovery Notes; Freedom Account context.
- **Status:** Proposed; storage behavior requires functional review.

### PR-ACC-003 — Respect authoritative offer status

- **Parent:** BR-002; BR-003
- **Behavior:** The account-side workflow uses the existing offer-service status
  without creating or reinterpreting eligibility.
- **Acceptance signal:** Only the authoritative offer state can begin the
  approved email-alert workflow.
- **Source:** Intake Request; Discovery Notes; Freedom Account context.
- **Status:** Proposed.

### PR-ACC-004 — Provide authenticated destination

- **Parent:** BR-004
- **Behavior:** The product provides a secure authenticated destination for the
  customer to view current offer details.
- **Acceptance signal:** An alert-originated visit requires authentication
  before personalized content appears.
- **Source:** Both team-context repositories.
- **Status:** Proposed.

### PR-ACC-005 — Allow withdrawal

- **Parent:** BR-005
- **Behavior:** An enrolled customer can leave the program from Freedom Account,
  and the current preference becomes available to the notification workflow.
- **Acceptance signal:** Withdrawal is confirmed and subsequent workflows
  respect the updated preference.
- **Source:** Discovery Notes; Notifications context.
- **Status:** Proposed.

### PR-ACC-006 — Measure account interactions

- **Parent:** BR-006
- **Behavior:** The experience records enrollment completion, withdrawal, and
  authenticated offer-detail visits attributed to an alert.
- **Acceptance signal:** Analytics can distinguish these events without storing
  customer data in the requirements repository.
- **Source:** Discovery Notes; Freedom Account context.
- **Status:** Proposed; success thresholds open under DEC-003.

## Experience and workflow

1. Customer signs in to Freedom Account.
2. Customer views the Rate Savings Alert enrollment option.
3. Customer confirms enrollment and sees the current state.
4. The existing offer status later initiates the approved notification workflow.
5. The email link brings the customer through authentication to offer details.
6. Customer may withdraw; future workflows respect the current preference.

## Dependencies and sequencing

- Offer-service status must be defined before alert initiation can be finalized.
- Notifications must define accepted inputs and delivery status.
- Frequency and suppression rules under DEC-002 affect both teams.
- Customer-language review precedes pilot release.

## Analytics and operational needs

- Enrollment completion and withdrawal.
- Alert-originated authenticated offer-detail visit.
- Correlation with a non-sensitive notification reference.
- Operational handling for an unavailable destination remains open.

## Assumptions

- Current enrollment state can be made available to the alert workflow.
- A secure authenticated offer-details route exists.

## Open questions

- DEC-002 frequency and suppression.
- Whether enrollment expires.
- Eligibility for displaying the enrollment option.
- Error experience when offer details are unavailable.

## BRD impact review

The Notifications context made the Intake Request's email-and-SMS scope
unachievable for phase one. DEC-001 approved email-only scope, and BR-003 plus
this PRD were updated consistently. No additional BRD change is proposed.

## Team review checkpoint

Freedom Account, Notifications, offer-service, Analytics, and applicable
customer-language reviewers must validate this draft before FRD approval.
