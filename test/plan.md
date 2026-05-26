# Smoke Test Writing Plan

## Project Brief

- Source concept map: `test/concept-map.md`
- Target reader: high school
- Style: Wang Zengqi-style plain description, clear explanation, gentle imagery
- Output expectation: one compact smoke-test chapter plus review
- Draft path: `test/drafts/chapter-01.md`
- Review path: `test/reviews/chapter-01-review.md`

## Chapter Sequence

1. Chapter 1 covers C01, C02, and C03. These form one story because the same scene can show failed proof, risky testing, and provisional trust.
2. A later chapter could cover C04, C05, and C06. This smoke test does not draft it.

## Chapter Cards

### Chapter 1: The Receipt Shelf

- Concept cluster: C01 Induction Problem; C02 Falsifiability; C03 Corroboration
- Concept IDs: C01, C02, C03
- Depends on: None
- Enables: C04, C05, C06
- Target reader: high school
- Story premise: A small delivery shelf has a clerk who wants to know whether a supplier is reliable. Repeated good receipts are not enough. A harsher check gives the supplier provisional standing without proving perfection.
- Short draft: A clerk sorts lunch boxes at a delivery station. Every morning's records are neat, but one heavy rainy day reveals whether the supplier's promise has real teeth.
- Concepts that must stay implicit in the body: induction, falsifiability, corroboration, proof, hypothesis
- Explanation points after the body: finite successes do not prove future reliability; a rule must risk failure to be tested; passing a severe test grants provisional trust.
- Acceptance criteria:
  - Body does not name C01, C02, or C03.
  - Story uses one concrete scene and no more than three major characters.
  - Explanation maps story elements to all three concept IDs.
  - Questions include one understanding check and one transfer check.
- Status: planned

## Concept Coverage Matrix

| Concept ID | Chapter 1 body | Chapter 1 explanation | Chapter 1 questions |
| --- | --- | --- | --- |
| C01 | Repeated clean receipts cannot guarantee tomorrow. | Explicitly mapped. | Understanding check. |
| C02 | Supplier makes a promise that can fail under a harsh condition. | Explicitly mapped. | Understanding check. |
| C03 | Clerk trusts the supplier for now after the harsh check. | Explicitly mapped. | Transfer check. |
| C04 | Not covered. | Not covered. | Not covered. |
| C05 | Not covered. | Not covered. | Not covered. |
| C06 | Not covered. | Not covered. | Not covered. |

## Narrative Continuity

Use an ordinary delivery station. If expanded, later chapters can keep the same station and introduce a claims desk for statistical inference.

## Acceptance Criteria

- The chapter body stays indirect and concrete.
- The explanation names and accurately defines all covered concepts.
- The output uses the required three-part format from `fable-writing`.
- The review can make a pass/revise decision from evidence in the draft.

## Progress Tracker

| Item | Status | Notes |
| --- | --- | --- |
| Concept map | accepted | Minimal smoke-test scope. |
| Chapter 1 plan | accepted | Ready for draft. |
| Chapter 1 draft | planned | Write to `test/drafts/chapter-01.md`. |
| Chapter 1 review | planned | Write to `test/reviews/chapter-01-review.md`. |
