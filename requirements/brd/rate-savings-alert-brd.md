# Business Requirements Document: Rate Savings Alert

## Document control

- **Status:** Draft for business-scope signoff
- **Owner:** Freedom Account product lead
- **Source intake:** Synthetic Jira reference BRP-247
- **Decision incorporated:** DEC-001
- **Data classification:** Synthetic demo content only

## Executive summary

The Rate Savings Alert initiative would let authenticated existing customers
enroll to receive an email when the existing offer service indicates that a
personalized offer is available. The email directs the customer to authenticated
Freedom Account details without exposing personalized financial information.

Cursor supports drafting and traceability; it does not decide offer eligibility,
calculate savings, approve customer language, or approve this BRD.

## Business problem and opportunity

Customers may not know that a personalized offer is present unless they sign in
and navigate to it. A permission-based alert can improve awareness while keeping
the existing offer decision and authenticated account as the authoritative
experience.

Sources: `inputs/intake-request.md`; `inputs/discovery-notes.md`.

## Business outcomes and success measures

Desired outcomes:

- Improve awareness of relevant personalized offers.
- Increase qualified visits to authenticated offer details.
- Give customers direct control over enrollment and withdrawal.
- Preserve governance, privacy boundaries, and team ownership.

Measures to report:

- Completed enrollments.
- Successful email deliveries.
- Authenticated offer-detail visits originating from an alert.

Numeric success thresholds remain open under DEC-003.

## Scope

### In scope

- Authenticated existing customers.
- Enrollment and withdrawal inside Freedom Account.
- Use of the existing offer-service decision.
- Email notification for a current personalized offer.
- Secure navigation to authenticated offer details.
- Enrollment, delivery, and engagement reporting.

### Out of scope

- SMS in phase one.
- New pricing, eligibility, savings, or underwriting logic.
- Displaying personalized financial information in an email.
- Unauthenticated enrollment or offer details.
- A commitment to phase-two SMS.

SMS was removed from phase one by the synthetic human decision DEC-001 after the
Notifications team constraint was reviewed.

## Stakeholders and impacted teams

- Executive sponsor: business-scope and success-threshold approval.
- Freedom Account product lead: requirements owner.
- Freedom Account team: enrollment and authenticated experience.
- Notifications team: email delivery and delivery reporting.
- Offer-service owner: authoritative offer-status dependency.
- Legal/Compliance reviewer: customer-language review.
- Analytics partner: measurement definition and reporting.

## Business requirements

### BR-001 — Customer-controlled enrollment

- **Requirement:** An authenticated existing customer must be able to enroll in
  the Rate Savings Alert experience.
- **Outcome:** Interested customers can request proactive awareness.
- **Source:** Intake Request; Discovery Notes.
- **Status:** Proposed.

### BR-002 — Existing offer decision

- **Requirement:** An alert may be initiated only from the existing
  personalized-offer decision; the initiative must not create or reinterpret an
  offer.
- **Outcome:** Existing offer governance remains authoritative.
- **Source:** Intake Request; Discovery Notes; Freedom Account context.
- **Status:** Proposed.

### BR-003 — Phase-one email alert

- **Requirement:** Phase one must support email and must not send SMS.
- **Outcome:** The pilot uses the channel supported by current team context.
- **Source:** DEC-001; Notifications context.
- **Status:** Proposed following approved synthetic decision.

### BR-004 — Protected customer details

- **Requirement:** An alert must omit personalized financial details and direct
  the customer to authenticated Freedom Account content.
- **Outcome:** Personalized information remains behind authentication.
- **Source:** Intake Request; both team-context repositories.
- **Status:** Proposed.

### BR-005 — Preference control

- **Requirement:** An enrolled customer must be able to leave the alert program,
  and future alerts must respect the current preference.
- **Outcome:** Customers retain control over communications.
- **Source:** Discovery Notes; Notifications context.
- **Status:** Proposed.

### BR-006 — Measurable pilot

- **Requirement:** The initiative must report enrollment completion, email
  delivery, and authenticated offer-detail visits originating from an alert.
- **Outcome:** The sponsor can evaluate the pilot after thresholds are approved.
- **Source:** Intake Request; Discovery Notes; both team contexts.
- **Status:** Proposed; numeric thresholds open.

## Constraints and dependencies

- The offer service is authoritative for personalized-offer presence.
- Email content requires the applicable business and Legal/Compliance review.
- Maximum frequency and repeat-alert suppression remain unresolved.
- Delivery depends on a verified email address and Notifications capability.
- The requirements repository must contain no customer or production data.

## Assumptions

- The existing offer service can provide a usable status to the impacted teams.
- A secure authenticated destination for offer details exists.
- The pilot can report the three named measures.

These assumptions require validation; they are not approvals.

## Risks

- Undefined frequency rules could create an unacceptable customer experience.
- Undefined success thresholds could prevent an objective pilot decision.
- Team interpretations may drift unless parent requirement IDs are preserved.
- Customer language may require changes after review.

## Open questions

- DEC-002: maximum alert frequency and repeat-alert suppression window.
- DEC-003: numeric thresholds for pilot success.
- Whether enrollment expires.
- Operational owner and response for failed deliveries.
- Final customer-facing language.

## Approval checkpoint

This draft becomes the business-scope baseline only after review by the product
owner, executive sponsor, impacted team owners, and required customer-language
reviewer. No such signoff is represented by this file.
