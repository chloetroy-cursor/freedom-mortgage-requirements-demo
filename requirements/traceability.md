# Rate Savings Alert Traceability

## Coverage

| Business requirement | Product requirements | Functional requirements | Epic | Status |
| --- | --- | --- | --- | --- |
| BR-001 Customer-controlled enrollment | PR-ACC-001; PR-ACC-002 | FR-001; FR-002 | EPIC-RSA-1 | Covered |
| BR-002 Existing offer decision | PR-ACC-003; PR-NOT-001 | FR-004 | EPIC-RSA-2 | Covered; technical input validation open |
| BR-003 Phase-one email alert | PR-ACC-003; PR-NOT-001; PR-NOT-002; PR-NOT-006 | FR-004; FR-006; FR-007 | EPIC-RSA-2 | Covered |
| BR-004 Protected customer details | PR-ACC-004; PR-NOT-002; PR-NOT-003 | FR-006; FR-008 | EPIC-RSA-2 | Covered; content approval open |
| BR-005 Preference control | PR-ACC-002; PR-ACC-005; PR-NOT-005 | FR-002; FR-003; FR-005 | EPIC-RSA-1; EPIC-RSA-2 | Covered; DEC-002 open |
| BR-006 Measurable pilot | PR-ACC-006; PR-NOT-004 | FR-009; FR-010 | EPIC-RSA-3 | Covered; DEC-003 open |

## Decision impact

DEC-001 changed the initial Intake Request from email-and-SMS scope to
email-only phase one. It is reflected in:

- BR-003 and the BRD scope boundaries.
- PR-ACC-003.
- PR-NOT-001, PR-NOT-002, and PR-NOT-006.
- FR-004, FR-006, and FR-007.
- EPIC-RSA-2 and story RSA-203.

## Remaining review gates

- **DEC-002:** blocks completion of FR-005 and story RSA-202.
- **DEC-003:** blocks numeric pilot-evaluation acceptance criteria.
- **Customer-language approval:** blocks release of PR-NOT-002 and FR-006.
- **Technical-context validation:** required before implementation planning.
- **BRD, PRD, and FRD signoffs:** not represented by these drafts.

## Orphan check

- Business requirements without product coverage: none.
- Product requirements without a parent business requirement: none.
- Functional requirements without a parent product requirement: none.
- Functional requirements without a primary epic: none.
