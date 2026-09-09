# Create PRD

## Role
You are an experienced product manager who has wriiten PRD documents for similar software applications. 
You have good knowledge of functional and non-functional requirements of software applications. - None
You ask questions to stakeholders that remove ambiguity, and clarify expectations. - None
You have enough technical and business knowledge to formulate a well-rounded PRD document. - TC 3, 4, 5

## Task
Given a product description, create a comprehensive PRD document. - Helped pass TC 1,2
Given a feature in the product, create a detailed feature specification. - Helped pass TC 1
Given a feature, create functional and non-functional requirements, as applicable. - Helped pass TC 1,2,3

## Context
You are a product manager who has been tasked with creating a PRD document for a new product. 
You have had meetings with at least 1 stakeholder, possiblly more, to gather requirements.
You have a good understanding of the product and the feature. - TC 3
You know about the target users, their needs, and their pain points. - TC 1
You may have some gaps in your knowledge or the business domain, which you need to fill in or mark as open questions.
You need to create a comprehensive PRD document that includes the product description, feature specification, and functional and non-functional requirements.

## Constraints
The PRD document should have the following sections:
1. Product Description - Helped pass TC1,2
2. Feature Specification - Helped pass TC1,2
3. Functional Requirements - Helped pass TC1,2
4. Non-Functional Requirements - Helped pass TC1,2
5. Open Questions
The PRD should not have vague qualifiers like "good", "bad", "fast", etc. - Passed all Tests
The PRD should have measurable and testable requirements. - Helped pass TC 3
The PRD should have clear section boundaries and headings. - Helped pass TC 1
The PRD should be a living document that can be updated as new information becomes available. - None
The PRD should contain any software/hardware/3rd party/system/infrastructure dependencies - Helped pass TC 5
The PRD should not contain any implementation details or detailed design specifications - Helped pass TC 1

## Assistant's independent marking

I re-evaluated each RTCC prompt sentence independently. The table below shows which test criterion would likely fail if that sentence were removed.

| # | RTCC instruction (sentence) | Test criterion that would fail if removed |
|---|-----------------------------|-------------------------------------------|
| 1 | You are an experienced product manager who has wriiten PRD documents for similar software applications. | None |
| 2 | You have good knowledge of functional and non-functional requirements of software applications. | TC3 (measurable timer accuracy/precision/drift/timezone), TC4 (storage response time), TC2 (notification duration/platform), TC5 (dependencies) — enables detailed NFRs |
| 3 | You ask questions to stakeholders that remove ambiguity, and clarify expectations. | None |
| 4 | You have enough technical and business knowledge to formulate a well-rounded PRD document. | TC3, TC4, TC5 — technical depth for measurable NFRs and dependencies |
| 5 | Given a product description, create a comprehensive PRD document. | All test cases (foundational; without it, no PRD) |
| 6 | Given a feature in the product, create a detailed feature specification. | None (indirectly supports TC1 benefits) |
| 7 | Given a feature, create functional and non-functional requirements, as applicable. | TC2 (notification type/duration/scenarios), TC3 (timer accuracy/drift/timezone), TC4 (storage response/data stored), TC5 (dependencies) |
| 8 | You are a product manager who has been tasked with creating a PRD document for a new product. | None |
| 9 | You have had meetings with at least 1 stakeholder, possiblly more, to gather requirements. | None |
| 10 | You have a good understanding of the product and the feature. | None |
| 11 | You know about the target users, their needs, and their pain points. | TC1 (personas, primary goal, user benefits) |
| 12 | You may have some gaps in your knowledge or the business domain, which you need to fill in or mark as open questions. | TC1 (open questions / uncertainties) |
| 13 | You need to create a comprehensive PRD document that includes the product description, feature specification, and functional and non-functional requirements. | None (redundant with Constraints section list) |
| 14 | The PRD document should have the following sections: | None |
| 15 | 1. Product Description | TC1 (personas, primary goal, benefits, out of scope) |
| 16 | 2. Feature Specification | None |
| 17 | 3. Functional Requirements | TC2 (notification type and scenarios), TC4 (which data is stored) |
| 18 | 4. Non-Functional Requirements | TC2 (notification duration/platform), TC3 (accuracy/precision/drift/timezone), TC4 (storage response), TC5 (dependencies) |
| 19 | 5. Open Questions | TC1 (open questions / uncertainties) |
| 20 | The PRD should not have vague qualifiers like "good", "bad", "fast", etc. | TC2 (notification min/max duration), TC3 (timer accuracy/drift/timezone), TC4 (storage response time) |
| 21 | The PRD should have measurable and testable requirements. | TC2 (notification min/max duration), TC3 (timer accuracy/drift/timezone), TC4 (storage response time) |
| 22 | The PRD should have clear section boundaries and headings. | None (covered by explicit section list) |
| 23 | The PRD should be a living document that can be updated as new information becomes available. | None |
| 24 | The PRD should contain any software/hardware/3rd party/system/infrastructure dependencies | TC5 (dependencies) |
| 25 | The PRD should not contain any implementation details or detailed design specifications | TC1 (must NOT contain design-specific details like UI, color, typography) |

## ex1 → ex2 pass causes

The instructions below are the strongest direct causes of the previously-failed ex1 test cases now passing in ex2:

- **TC1 (Primary app goal):** `5. Open Questions`, `You know about the target users...`, `You may have some gaps... mark as open questions`, and the constraint `...not contain...design specifications` removed the UI/UX design details and ensured personas/goal/benefits/open questions.
- **TC2 (Notification specifications):** `4. Non-Functional Requirements`, `The PRD should have measurable and testable requirements`, and `Given a feature, create...non-functional requirements` produced the measurable notification type, duration, and platform requirements.
- **TC3 (DateTime and timer):** `4. Non-Functional Requirements` and `The PRD should have measurable and testable requirements` produced NFR-03/04/05/06.
- **TC4 (Data storage):** `4. Non-Functional Requirements` and `The PRD should have measurable and testable requirements` produced NFR-07/08/09/10/11.
- **TC5 (Dependencies):** `The PRD should contain any software/hardware/3rd party/system/infrastructure dependencies` and `4. Non-Functional Requirements` produced DEP-01/02/03/04.