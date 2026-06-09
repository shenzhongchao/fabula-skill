---
name: fable-review
description: Use when evaluating, scoring, accepting, or giving revision advice for fables or allegorical stories against a writing plan, concept map, reader level, or acceptance criteria
---

# Fable Review

## Overview

Judge whether a fable teaches the intended concepts accurately while remaining a real fable. Review concept coverage, story discipline, story logic, expression clarity, reader fit, continuity, and plan acceptance criteria.

## Required Inputs

- Fable draft.
- Relevant chapter card or acceptance criteria from `plan.md`.
- Relevant concept entries from `concept-map.md`.
- Target reader level and style, if not already in the plan.
- `fable-writing/SKILL.md` when checking style, trope bans, and output shape.

## Review Procedure

1. Restate the target concept cluster and acceptance criteria.
2. Check whether every required concept is represented accurately.
3. Check whether the body avoids concept names and field terminology until the explanation section.
4. Run a story logic and clarity pass:
   - Causal chain: each major event should follow from a visible prior condition or choice.
   - Motivation chain: important character decisions should have enough pressure, goal, or constraint to make them credible.
   - Transition chain: scene shifts, time jumps, and conclusion turns should not skip the step readers need to understand.
   - Expression clarity: pronouns, metaphors, technical substitutes, and key sentences should have unambiguous referents.
5. Check narrative continuity with earlier chapters when applicable.
6. Check target reader fit: vocabulary, sentence complexity, image clarity, and explanation level.
7. Check the two questions: one must test understanding, one must test transfer.
8. Return pass/revise decision with specific edits.

## Review Checklist

- Is the body one concrete scene rather than a stitched summary?
- Does the body stay indirect and avoid direct concept naming?
- Does the explanation section map story elements to concept parts?
- Do events connect by cause, choice, and consequence rather than coincidence or authorial convenience?
- Are character motives legible before their decisions matter?
- Are there missing intermediate steps that make a realization, reversal, or ending feel abrupt?
- Are any sentences unclear because of vague subjects, ambiguous pronouns, overloaded images, or compressed transitions?
- Are the questions specific, answerable, and non-overlapping?
- Does the draft avoid the banned tropes, openings, roles, and images in `fable-writing`?

## Score Table

Use a 1-5 score for each dimension:

| Dimension | What to inspect |
| --- | --- |
| Concept accuracy | Does the mapping match the concept-map summary and relationships? |
| Concept completeness | Are required concepts and dependencies covered? |
| Fable indirectness | Does the body teach through scene and consequence instead of explanation? |
| Story logic | Do events, decisions, reversals, and consequences form a credible causal chain without hidden steps? |
| Expression clarity | Are sentences, referents, transitions, and images clear enough that readers can follow the story on first reading? |
| Style fit | Does it match the requested Wang Zengqi-style plain description, clear explanation, and gentle imagery? |
| Reader fit | Can the target reader understand the story and explanation? |
| Continuity | Does it preserve shared setting, character memory, and cause-effect links? |
| Prompt discipline | Does it avoid banned images, roles, structures, places, and openings? |
| Question quality | Are understanding and transfer questions specific and answerable? |

## Output Format

```markdown
## Review Conclusion

- Decision: Pass / Revise
- Main reason:

## Score Table

| Dimension | Score | Evidence | Required edit |
| --- | ---: | --- | --- |

## Concept Mapping Check

## Acceptance Criteria Check

## Story Logic and Clarity Check

## Revision Advice
```

## Common Mistakes

- Giving only literary feedback.
- Accepting a pleasant story with weak concept mapping.
- Missing terminology leaked inside the body.
- Ignoring plot holes because the concept explanation is correct.
- Calling a passage "unclear" without identifying the exact sentence, missing step, or ambiguous referent.
- Treating abrupt realizations, unexplained choices, or convenient coincidences as style rather than revision problems.
- Giving vague advice such as "make it clearer" without naming exact edits.
