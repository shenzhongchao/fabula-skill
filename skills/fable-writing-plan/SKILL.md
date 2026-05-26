---
name: fable-writing-plan
description: Use when creating a chapter plan, plan.md, acceptance criteria, or progress tracker for fables or allegorical stories based on a discipline concept map
---

# Fable Writing Plan

## Overview

Turn `concept-map.md` into a practical writing plan. Chapters must follow conceptual dependencies, not a loose list of topics.

## Inputs

- `concept-map.md` or equivalent concept map.
- Target reader level: elementary school, middle school, high school, university, or a custom reader profile.
- Writing style and length constraints.
- Desired chapter count or output scope, if specified.

## Required `plan.md` Sections

1. Project brief: reader, style, length, source concept map, and output expectations.
2. Chapter sequence: ordered by predecessor-successor relationships.
3. Chapter cards: one card per chapter with concept cluster, story premise, short draft, and dependencies.
4. Concept coverage table: every planned concept and where it appears.
5. Narrative continuity: recurring setting, characters, motifs, and constraints across chapters.
6. Acceptance criteria: per chapter and whole project.
7. Progress tracker: planned, drafted, reviewed, revised, accepted.
8. Output paths: where each chapter draft and review will be written.

## Chapter Card Template

```markdown
### Chapter N: Working Title

- Concept cluster:
- Concept IDs:
- Depends on:
- Enables:
- Target reader:
- Story premise:
- Short draft:
- Concepts that must stay implicit in the body:
- Explanation points after the body:
- Acceptance criteria:
- Status: planned
```

## Planning Rules

- Start with concepts that unlock later concepts.
- Combine concepts only when their relationship can be dramatized in one scene.
- Split concepts when combining them would force explanation inside the story.
- Write acceptance criteria that `fable-review` can judge directly.
- Add continuity notes whenever multiple chapters share characters, setting, or cause-effect history.
- Include a concept coverage matrix with one row per concept ID and one column per chapter.
- Use stable output paths for chapter drafts and review notes, such as `drafts/chapter-01.md` and `reviews/chapter-01-review.md` when a foldered workflow is desired.
- Prefer the same terminology as `fable-concept-map` so IDs can be reused without translation.

## Common Mistakes

- Treating chapter order as a table of contents copied from the source.
- Omitting acceptance criteria.
- Planning stories around terminology instead of conflicts, choices, and consequences.
- Forgetting to track review status.
