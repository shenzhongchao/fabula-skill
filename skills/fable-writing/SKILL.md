---
name: fable-writing
description: Use when drafting, revising, or continuing fables or allegorical stories for teaching discipline concepts, either from a direct concept prompt, a writing plan, a concept map, or both a plan and concept map
---

# Fable Writing

## Overview

Write fables that teach concepts indirectly through concrete scenes. Use plain description, clear explanation, and restrained imagery. Prefer economical strokes and transparent prose: show events plainly and let structure carry the meaning.

## Required Context

First choose the input mode. Do not block standalone requests just because `plan.md` or `concept-map.md` is missing.

| Mode | Use when | Required action |
| --- | --- | --- |
| Standalone | The user gives a concept, topic, or rough teaching goal without project files. | Build a working card from the prompt and reasonable assumptions. Ask only if the target concept is unclear. |
| Plan only | A `plan.md` or chapter card is available, but no concept map is provided. | Follow the chapter card, acceptance criteria, target reader, style, continuity, and output expectations. |
| Concept map only | A `concept-map.md` is available, but no writing plan is provided. | Use the target concept entry, predecessor-successor links, common misunderstandings, and fable hooks to build a working card. |
| Plan + concept map | Both files are available. | Use the plan for scope and continuity; use the concept map for conceptual accuracy and relationships. |

When available, inspect only the relevant `plan.md` chapter card and relevant `concept-map.md` concept entries.

Always make a brief working card before drafting. Use it as internal preparation; do not output it unless the user asks for planning notes.

- Target concept and discipline.
- Input mode and source files used.
- Core relation to dramatize, in one sentence.
- Common misunderstanding to avoid.
- Target reader and body length.
- Continuity or acceptance criteria, if any.
- Output destination, if the plan or user gives one.
- Body-banned words: concept name, translations, abbreviations, close synonyms, formulas, famous examples, field terms, and field-native roles or settings.

## Source Precedence

Use this order when inputs conflict:

1. User's explicit request and constraints.
2. `plan.md` for chapter scope, target reader, style, continuity, output path, and acceptance criteria.
3. `concept-map.md` for definitions, dependencies, concept relationships, and common misunderstandings.
4. This skill's defaults for length, structure, style, and reveal discipline.

If a plan's short draft conflicts with a concept-map definition, keep the plan's scene only if it can still teach the concept accurately. Otherwise revise the scene while preserving the plan's scope.

If the plan names concept IDs, preserve those IDs in the explanation mapping. If the concept map includes predecessor concepts, use them to avoid contradictions, but do not expand the fable body beyond the planned scope.

## Style Profile

Use a blend of:

- Wang Zengqi-style plain, concrete description.
- Clear, unforced explanation.
- Gentle, child-readable imagery.

Avoid decorative flourish that weakens causality or hides the concept mapping.

## Drafting Workflow

1. Choose the input mode and fill the working card.
2. Identify the concept cluster, target reader, acceptance criteria, and source constraints.
3. Build the body-banned word list before drafting. Include concept names, translations, abbreviations, close synonyms, field terms, formulas, famous examples, and source-field roles or settings.
4. Choose one concrete carrier scene and no more than three major characters. Prefer a scene outside the concept's original field unless the plan requires continuity.
5. Plan the reveal ladder: the opening and middle must read as an ordinary surface problem; only the final turn should make the reader faintly recognize the hidden pattern.
6. Draft the fable body with short sentences, visible objects, and minimal explanation.
7. Run a leakage scan on the body and revise any early reveal.
8. Add a clear concept explanation after the body.
9. Add one understanding question and one transfer question.
10. Check continuity and acceptance criteria when using `plan.md`.

## Mode-Specific Guidance

### Standalone

- Infer a reader level and body length when the user does not specify them; default to a compact, high-school-readable body.
- Use a single concept unless the user asks for a cluster.
- Create the concept summary from general knowledge, then keep all explicit teaching out of the body.
- Return the standard markdown output directly unless the user asks to write a file.
- State assumptions in the explanation only when they matter for interpretation.

### Plan Only

- Treat the chapter card as the contract for scope, continuity, character reuse, target reader, and acceptance criteria.
- Use the card's implicit-concept list as the start of the body-banned word list.
- If the plan gives a story premise, preserve its practical conflict unless doing so would force terminology or early reveal.
- Do not add extra concepts outside the chapter card.
- If the plan gives an output path and the user asks for file output, write the draft there; otherwise return the standard markdown output.

### Concept Map Only

- Start from the requested concept entry or concept IDs. If no target is specified, choose the earliest dependency that unlocks later entries.
- Use predecessor-successor links to decide what must be explained before or after the fable body.
- Use common misunderstandings as negative tests: the story must not accidentally teach the mistaken version.
- Use fable hooks as inspiration, not as mandatory scenes.
- If multiple adjacent concepts are requested, combine them only when one scene can show their relationship without adding explanation inside the body.

### Plan + Concept Map

- Read the chapter card first, then read only the matching concept entries and direct predecessor-successor links.
- Keep the plan's chapter cluster, but use the concept map to sharpen definitions and story mapping.
- Preserve planned continuity unless it causes early reveal, terminology leakage, or concept inaccuracy.
- Explanation must map each planned concept ID to concrete story elements.
- Use plan acceptance criteria as the final checklist after the leakage scan.

## Style Rules

- Use concrete nouns and actions before abstractions.
- Keep the body indirect; put explicit teaching in the explanation section.
- Make causality visible through what characters try, notice, lose, or gain.
- Prefer one strong scene over a tour of examples.
- Keep language smooth enough for the target reader level.
- Use a mundane carrier outside the source field when possible: kitchen, shop, workshop, station, garden, clinic desk, repair counter, storage shelf, or household errand.
- For abstract concepts, show one changed condition and one changed consequence. Do not explain the contrast in the body.
- Keep abstract nouns sparse in the body. Words like value, order, belief, meaning, evidence, system, rule, signal, and structure can make the explanation arrive too early.

## Fable Feel

- Length: within the limit in `plan.md`; if none is given, keep the body compact and scene-bound.
- World: fictional, concrete, and small enough to hold in one scene or a few turns.
- Characters: no more than three major characters, preferably two.
- Reveal rhythm: avoid concept names and field terminology in the body; let the reader infer the idea near the end.
- Narrative discipline: details and consequences carry meaning; characters should not become lecturers.

## Prompt Constraints

Apply these rules when drafting or revising:

- Do not name the target concept in the fable body.
- Do not use field terminology in the fable body unless the plan explicitly allows it.
- Do not use translated names, abbreviations, formulas, famous examples, or near-synonyms that point directly to the concept.
- Do not choose a source-field setting when it would reveal the domain too early. A court story for a legal concept or a computer story for a computing concept may be too obvious unless continuity requires it.
- Keep the fable body centered on one concrete scene.
- Use no more than three major characters.
- Reveal the concept indirectly, then explain it explicitly in the concept explanation.

## Reveal Discipline

Use this rhythm for the fable body:

1. Surface setup: ordinary objects and a practical trouble. The reader should not know the discipline yet.
2. Pressure turn: a small action changes what happens. The body still avoids concept language.
3. Near-end recognition: one concrete sentence lets the reader sense the hidden pattern without naming it.
4. Stop. Put all naming, definitions, and explicit mapping in `Concept Explanation`.

If the reader can identify the concept before the final turn, revise the opening or setting. If the final turn explains the lesson in abstract terms, make it concrete again.

## Leakage Scan

Before final output, inspect only the fable body:

- Remove direct names, translations, abbreviations, formulas, and famous examples.
- Remove field terms and source-field roles or places that reveal the discipline too early.
- Replace near-synonyms with concrete objects or actions.
- Check that no character explains the concept, moral, or rule.
- Check that the first two thirds still work as a plain scene.
- Check that recognition happens only through the final consequence or image, not through explanation.

## Banned Tropes

### Images

Avoid: bell, river, mirror, maze, loom, map, lighthouse, chessboard, echo, shadow, hourglass, wind, candle, seed, bridge, stars, butterfly, spiderweb.

### Places

Avoid names like Echo City, Village of Memory, Sea of Oblivion, Silent Valley. Use ordinary geography or no named place.

### Structures

- Traveler seeks wisdom from a sage
- Village anomaly -> crowd epiphany
- Child's one sentence awakens adults
- Master-disciple dialectic
- Dying last words

### Roles

Clockmaker, librarian, hermit, storyteller, old boatman, brewer, blacksmith, scribe.

### Openings

Avoid "Once upon a time in a place," "One day someone met something," or "In a distant mountain." Start inside the scene.

## Output Format

```markdown
[Fable body only]

## Concept Explanation

- Concept Name:
- Discipline or School:
- Core Definition:
- Story Mapping:

## Check Questions

1. Understanding Check:
2. Transfer Check:
```

## Common Mistakes

- Naming the concept inside the fable body.
- Hiding the exact name but leaking the idea through a synonym, formula, famous case, or source-field setting.
- Turning a character into a teacher who explains the concept.
- Letting the story begin in the original discipline, so the reader guesses the concept too early.
- Using abstract nouns in the body until it reads like a disguised essay.
- Using banned stock images from the reference prompt.
- Breaking continuity with earlier chapters.
- Writing beautiful prose that no longer maps to the planned concept.

## Review Lens

Use the same rules when editing an existing draft:

- Check that the body still reads like a fable, not an essay.
- Check that the explanation maps specific story elements to concept parts.
- Check that the two questions are specific, answerable, and different in kind.
