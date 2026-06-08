---
name: fable-writing-plan
description: Use when creating a chapter plan, plan.md, acceptance criteria, or progress tracker for fables or allegorical stories based on a discipline concept map
---

# Fable Writing Plan

## Overview

Transform a concept map into an executable writing plan. Each concept corresponds to one fable, approximately 1,000 words in total, including a post-text explanation. Chapters must be ordered by prerequisite relationships among concepts: foundational concepts come first, and concepts that depend on them come later—not by loosely listing topics or copying a table of contents.

The "approximately 1,000 words" target measures the entire fable (story body + explanation) as a single deliverable unit, ensuring a consistent rhythm across the book and giving each concept adequate but not excessive coverage. At the planning stage, only write story premises and short-draft seeds, but specify this length target in each card and acceptance criteria so `fable-writing` and `fable-review` can check against it.

## Inputs

- A concept map.
- Target reader level: elementary, middle school, high school, college, or a custom reader profile.
- Writing style and length constraints.
- Specified chapter count or output scope.

## Required Sections in `plan.md`

1. **Project Overview**: reader, style, target length of approximately 1,000 words per fable (including explanation), concept-map source, and output requirements.
2. **Chapter Organization**: ordered by prerequisite relationships—each chapter first lists which prerequisite concepts have appeared in earlier chapters, then lists which subsequent concepts it lays the groundwork for, so reading order aligns with conceptual dependency order.
3. **Concept Cards**: one card per concept, including the concept, story premise, short draft, dependency relationships, and length target.
4. **Concept Coverage Table**: lists which concepts are planned for each chapter.
5. **Acceptance Criteria**: separate criteria for individual chapters and for the full book.
6. **Progress Tracker**: planned, drafted, reviewed, revised, accepted.
7. **Output Paths**: records where each chapter draft and review comments are written.

## Short-Draft Style

Each "short draft" must itself read like a real fable, not an explanatory outline disguised as a story.

- Explain the target concept indirectly through the story. Do not use concept names or disciplinary terminology in the fable body.
- Let readers gradually perceive the hidden pattern, ideally realizing it only near the end.
- Place explicit conceptual explanations after the story, not inside it.
- Be concrete, readable, and of a quality that can serve as the foundation for publication-ready text.

The target for each completed fable is approximately 1,000 words total, counting both story body and explanation. A suggested allocation: story body around 700–800 words, explanation around 200–300 words. This is a rhythm reference, not a rigid quota—the body may be longer when the concept is complex and shorter when simple, but the whole piece should not clearly exceed 1,200 words or fall below 800 words, to avoid some concepts being rushed and others overextended. The "short draft" in the plan only needs to write the story seed (core scene, conflict, twist, closing image) that can support this length; it does not need to fill 1,000 words.

## Chapter Card Template

```markdown
### Chapter N: Working Title

- Concept Group:
- Concept ID:
- Depends on:
- Lays groundwork for:
- Target Reader:
- Reference Work:
- Shared Conflict Structure:
- Borrowable Elements:
- Elements to Avoid:
- Story Premise:
- Short Draft:
- Length Target: approximately 1,000 words (story body ~700–800 words + explanation ~200–300 words)
- Concepts that must remain implicit in the body:
- Explanation points after the body:
- Acceptance Criteria:
- Status: Planned
```

## Planning Rules

- Prioritize concepts that lay groundwork for later concepts, and determine chapter order accordingly: when any concept appears, all its prerequisite concepts should already have been covered in earlier chapters; readers should never need to flip ahead or know concepts that have not yet appeared.
- In each concept’s acceptance criteria, specify the approximately 1,000-word (including explanation) length target so `fable-review` can directly check for length imbalance, not just whether the concept is explained.
- Before writing each story premise, search for a widely known work with a similar conflict. Prioritize accessible, plot-driven novels or films that require no extra background knowledge; science fiction is ideal (e.g., *The Three-Body Problem*, *Arrival*). Avoid obscure classics, works that rely mainly on abstract symbolism, or works that require understanding complex intellectual backgrounds to appreciate.
- In the concept-coverage matrix, each row corresponds to a concept ID and each column to a chapter.
- Use stable paths for chapter drafts and review comments, e.g. `drafts/chapter-01.md` and `reviews/chapter-01-review.md`.
- Reuse terminology from the concept map as much as possible so concept IDs can be reused without conversion.

## Banned Story Tropes

### Imagery

Avoid: clocks, rivers, mirrors, labyrinths, looms, maps, lighthouses, chessboards, echoes, shadows, hourglasses, wind, candles, seeds, bridges, stars, butterflies, spiderwebs.

### Locations

Do not invent overwrought literary place names like "Echo City," "Village of Memory," "Sea of Forgetting," or "Silent Valley." Use ordinary place names, or do not name them at all.

### Structures

- Traveler seeks wisdom from a sage.
- Strange phenomenon in a village → collective epiphany.
- A child’s single sentence awakens the adults.
- Master–disciple dialectical debate.
- Deathbed last words.

### Characters

Clockmaker, librarian, hermit, storyteller, old ferryman, brewer, blacksmith, scribe.

### Openings

Do not begin with "Once upon a time in a certain place…" "One day someone encountered something…" or "In a distant mountain…" Drop directly into the scene.

## Common Mistakes

- Introducing a concept in a chapter before its prerequisites have been covered, forcing readers to know concepts that have not yet appeared.
- Severely uneven lengths: some fables skimmed in only two or three hundred words, others ballooning to two or three thousand, departing from the unified approximately 1,000-word (including explanation) target.
- Planning stories around terminology rather than around conflict, choice, and consequence.
- Choosing reference works that readers are unfamiliar with and that require extensive explanation.
- The short draft explaining or naming the concept directly before the fable body has sufficiently set it up.
- Forgetting to track review status.
