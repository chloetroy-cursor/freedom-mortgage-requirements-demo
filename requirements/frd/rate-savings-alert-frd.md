# Functional Requirements Document: Rate Savings Alert

## Document control

- **Status:** Draft for functional review
- **Parent BRD:** Rate Savings Alert BRD
- **Parent PRDs:** Freedom Account PRD; Notifications PRD
- **Decision incorporated:** DEC-001
- **Unresolved decisions:** DEC-002; DEC-003

## Approved functional scope

This draft decomposes the proposed email-only phase-one scope. It does not
represent technical architecture, delivery approval, or an LOE estimate.

## Functional requirements

### FR-001 — Capture enrollment

- **Parents:** PR-ACC-001
- **Behavior:** Present an authenticated enrollment action, require an explicit
  customer choice, record the outcome, and display confirmation.
- **Input:** Authenticated customer context and explicit enrollment choice.
- **Output:** Current enrolled state and enrollment event.
- **Exceptions:** Do not report success when the preference cannot be recorded.
- **Verification:** Demonstrate successful enrollment and a handled failure.
- **Primary epic:** EPIC-RSA-1.

### FR-002 — Display current preference

- **Parents:** PR-ACC-002
- **Behavior:** Retrieve and display the customer's current Rate Savings Alert
  preference whenever the preference experience is opened.
- **Input:** Authenticated customer context.
- **Output:** Enrolled or not-enrolled state.
- **Exceptions:** Show a non-committal error state if the preference is
  unavailable; do not assume enrollment.
- **Verification:** Verify both states and the unavailable-state experience.
- **Primary epic:** EPIC-RSA-1.

### FR-003 — Capture withdrawal

- **Parents:** PR-ACC-005; PR-NOT-005
- **Behavior:** Let an enrolled customer withdraw, update the current preference,
  confirm the change, and make it effective for later alert evaluation.
- **Input:** Authenticated customer context and explicit withdrawal choice.
- **Output:** Not-enrolled state and withdrawal event.
- **Exceptions:** Do not confirm withdrawal when the preference update fails.
- **Verification:** Verify confirmation and exclusion from a later alert.
- **Primary epic:** EPIC-RSA-1.

### FR-004 — Validate alert conditions

- **Parents:** PR-ACC-003; PR-NOT-001; PR-NOT-005
- **Behavior:** Before delivery, validate current enrollment and the
  authoritative current-offer indicator.
- **Input:** Current preference, offer indicator, and offer-status timestamp.
- **Output:** Approved-for-email or not-approved outcome with reason.
- **Business rule:** The workflow must not create or reinterpret offer status.
- **Exceptions:** Missing, stale, or unrecognized inputs do not approve delivery.
- **Verification:** Test valid, withdrawn, missing, and invalid conditions.
- **Primary epic:** EPIC-RSA-2.

### FR-005 — Apply frequency and suppression

- **Parents:** PR-NOT-001; PR-NOT-005
- **Behavior:** Apply the approved maximum frequency and repeat-alert
  suppression rule before email delivery.
- **Input:** Approved-for-email outcome and prior initiative delivery history.
- **Output:** Continue or suppress with a reason.
- **Business rule:** Values remain blocked by DEC-002.
- **Exceptions:** Until DEC-002 is approved, this requirement is not ready for
  delivery implementation.
- **Verification:** To be completed after DEC-002.
- **Primary epic:** EPIC-RSA-2.

### FR-006 — Send approved email

- **Parents:** PR-NOT-002; PR-NOT-003
- **Behavior:** Render and send the approved email template with non-sensitive
  variables and the authenticated Freedom Account destination.
- **Input:** Approved template identifier, destination email, secure account
  destination, and non-sensitive initiative reference.
- **Output:** Delivery request reference or handled failure.
- **Business rule:** The message must not include personalized financial detail.
- **Exceptions:** Missing required input does not send an email.
- **Verification:** Review rendered content and successful/failed requests.
- **Primary epic:** EPIC-RSA-2.

### FR-007 — Prevent SMS delivery

- **Parents:** PR-NOT-006
- **Behavior:** Phase-one execution exposes no path that requests or sends SMS
  for this initiative.
- **Input:** Any Rate Savings Alert request.
- **Output:** Email-only processing or a rejected unsupported-channel request.
- **Business rule:** DEC-001 governs phase-one channel scope.
- **Exceptions:** None; SMS requires a separately approved future change.
- **Verification:** Confirm every phase-one path excludes SMS.
- **Primary epic:** EPIC-RSA-2.

### FR-008 — Resolve authenticated destination

- **Parents:** PR-ACC-004; PR-NOT-003
- **Behavior:** Direct an alert-originated customer through authentication before
  presenting current personalized-offer details.
- **Input:** Secure account destination and customer authentication state.
- **Output:** Authenticated offer-details experience or handled unavailable state.
- **Exceptions:** Never expose personalized details before authentication.
- **Verification:** Verify signed-out, signed-in, and unavailable paths.
- **Primary epic:** EPIC-RSA-2.

### FR-009 — Report delivery outcomes

- **Parents:** PR-NOT-004
- **Behavior:** Record delivery, failure, open, and link-selection outcomes using
  a non-sensitive initiative reference.
- **Input:** Delivery and engagement outcomes.
- **Output:** Initiative-level reporting events.
- **Exceptions:** Reporting failure must be observable; operational response is
  still an open question.
- **Verification:** Verify each named event and failed reporting.
- **Primary epic:** EPIC-RSA-3.

### FR-010 — Report account outcomes

- **Parents:** PR-ACC-006
- **Behavior:** Record enrollment, withdrawal, and authenticated
  alert-originated offer-detail visits.
- **Input:** Account interaction and non-sensitive initiative reference.
- **Output:** Initiative-level reporting events.
- **Exceptions:** Do not store customer data in this requirements repository.
- **Verification:** Verify each named event and attribution.
- **Primary epic:** EPIC-RSA-3.

## End-to-end workflow

1. Authenticated customer enrolls and sees confirmation.
2. Existing offer status later indicates that an offer is present.
3. Workflow validates current enrollment and authoritative offer status.
4. Workflow applies the approved frequency and suppression rules.
5. Notifications sends an approved non-sensitive email.
6. Customer follows the link and authenticates before seeing offer details.
7. Delivery and authenticated engagement outcomes are reported.
8. A later withdrawal prevents subsequent alerts.

## Dependencies and sequencing

1. Approve DEC-002 frequency and suppression.
2. Validate offer-status input and preference availability.
3. Approve message content and authenticated destination.
4. Complete enrollment and preference functions.
5. Complete email delivery and SMS exclusion.
6. Complete measurement and operational handling.
7. Validate the end-to-end workflow across impacted teams.

## Epic mapping

- **EPIC-RSA-1 — Enrollment and preference control:** FR-001, FR-002, FR-003.
- **EPIC-RSA-2 — Offer-to-email workflow:** FR-004, FR-005, FR-006, FR-007,
  FR-008.
- **EPIC-RSA-3 — Pilot measurement and operations:** FR-009, FR-010.

## User stories and acceptance criteria

### RSA-101 — Enroll in alerts

As an authenticated customer, I can explicitly enroll and see confirmation.

- Given I am authenticated and not enrolled, when I confirm enrollment, then my
  current state becomes enrolled and an enrollment event is recorded.
- If recording fails, the experience does not claim that I am enrolled.

### RSA-102 — View and change preference

As an enrolled customer, I can see my current state and withdraw.

- Current state is displayed when available.
- Successful withdrawal is confirmed and blocks a later alert.
- An unavailable preference is not interpreted as enrolled.

### RSA-201 — Validate an alert request

As the product owner, I want email considered only for a currently enrolled
customer with an authoritative current offer.

- Missing, stale, withdrawn, or invalid conditions do not approve delivery.
- Each non-approved outcome has a reviewable reason.

### RSA-202 — Apply contact controls

As an enrolled customer, I receive no more alerts than the approved rule allows.

- Acceptance criteria are blocked until DEC-002 is approved.

### RSA-203 — Deliver an email safely

As an enrolled customer, I receive approved non-sensitive email content that
links to authenticated details.

- Missing required inputs do not send.
- Personalized financial details do not appear in the message.
- No phase-one path requests or sends SMS.

### RSA-204 — Open authenticated details

As an alerted customer, I authenticate before viewing current offer details.

- Signed-out customers authenticate first.
- Unavailable details do not expose stale or personalized information.

### RSA-301 — Measure the pilot

As a sponsor, I can review enrollment, delivery, and authenticated engagement.

- Named events can be distinguished and attributed to the initiative.
- Numeric evaluation remains blocked until DEC-003 is approved.

## Non-functional and operational requirements

- Accessibility, retention, monitoring, and operational-response details require
  validation by their accountable teams; this draft does not invent them.
- The demo repositories contain no customer or production data.
- Customer-facing content requires applicable review before release.

## Traceability and coverage gaps

All proposed BRD requirements map to a PRD and functional requirement. Delivery
remains blocked by DEC-002, final customer-language approval, technical-context
validation, and functional review. DEC-003 blocks objective pilot evaluation but
not requirements drafting.

## Inputs for refined LOE

- Three epics and seven initial stories.
- Cross-team dependencies: Freedom Account, Notifications, offer service,
  Analytics, and customer-language review.
- Uncertainty: frequency/suppression, operational failure ownership, technical
  interfaces, final content, and success thresholds.
- No effort, cost, points, sprints, or dates are estimated here.

## Approval checkpoint

This FRD requires functional review by the impacted teams after the BRD and PRDs
are approved. This draft does not represent that approval.
