# Fable Discipline Skills Design

## Goal

Create a repository-local skill suite that helps Codex turn a discipline's key concepts into connected fable stories. The workflow must preserve conceptual structure instead of flattening the discipline into a list.

## Architecture

Use one orchestrator skill plus four focused sub-skills:

- `fable-discipline-pipeline`: coordinates the full workflow from discipline materials to reviewed fable output.
- `fable-concept-map`: builds a concept map from discipline materials.
- `fable-writing-plan`: turns the concept map into a chapter-level writing plan.
- `fable-writing`: writes fable text from the plan.
- `fable-review`: evaluates each fable against the plan and concept map.

Each skill lives under `skills/<skill-name>/SKILL.md`. Skills that need heavier guidance may use `references/`, but no extra README or unrelated documentation should be created.

## Skill Responsibilities

### fable-discipline-pipeline

Trigger when the user asks to explain, teach, or transform a discipline through fables or寓言故事. It should guide Codex through:

1. Build or locate a concept map.
2. Build or update a writing plan.
3. Write fable chapters or concept stories.
4. Review and revise the fables.

The orchestrator must keep outputs traceable by asking each stage to write or update explicit files.

### fable-concept-map

Input: discipline name, scope, source notes, books, articles, or reference files.

Output: a Markdown concept map, usually `concept-map.md`.

The output must include:

- Global question or organizing theme of the discipline.
- Historical or logical layers.
- Key concepts grouped by layer or branch.
- Time order where relevant.
- Predecessor and successor relationships.
- Cross-branch relationships.
- A summary for every concept.

Each concept entry should use this shape unless the task requires a better local format:

```markdown
### Concept Name

- Summary: 2-4 sentences explaining what problem this concept solves, its core meaning, and why it matters.
- Layer:
- Predecessors:
- Successors:
- Historical or logical position:
- Key relationships:
- Common misunderstandings:
- Fable hooks:
```

The skill should explicitly forbid simple unordered concept lists.

### fable-writing-plan

Input: `concept-map.md`, target reader level, desired writing style, and optional length constraints.

Output: `plan.md`.

The plan must include:

- Target reader and style.
- Chapter sequence based on predecessor-successor relationships.
- A short draft or synopsis for each chapter.
- Concept coverage table.
- Narrative continuity notes.
- Acceptance criteria for each chapter and the whole work.
- Writing progress and review status.

The plan must organize story progression through conceptual dependencies, not by arbitrary listing.

### fable-writing

Input: `plan.md`, target chapter or concept cluster, and any specific constraints.

Output: fable正文, concept explanation, and two check questions.

The skill should carry forward the reference prompt from `dev_notes/refs/寓言prompt.md`, especially:

- Under 1000 characters for a focused fable unless the plan says otherwise.
- No direct use of the concept name or domain terminology inside the fable正文.
- No more than three major characters, preferably two.
- Avoid the listed stale images, openings, roles, places, and structures.
- Prefer concrete scenes, non-human perspectives, modern occupations, or micro-scale events.
- Output three parts: fable正文, concept explanation, and check questions.

The required language style is:

> Plain description + clear explanation + gentle imagery.

Operationally: short concrete sentences for story scenes, clear and smooth explanatory paragraphs, gentle imagery that younger readers can understand.

The skill must also preserve continuity across stories in the same project.

### fable-review

Input: fable text, `plan.md`, and `concept-map.md`.

Output: objective evaluation and revision advice.

The review must check:

- Whether the fable satisfies the chapter acceptance criteria.
- Whether concept mapping is accurate and complete.
- Whether concept names or field terms are leaked too early.
- Whether the fable avoids banned tropes from the writing prompt.
- Whether the target reader level is appropriate.
- Whether narrative continuity is maintained across the larger work.
- Whether the explanation and check questions actually test understanding and transfer.

The review should produce a pass/revise decision, a concise score table, and specific actionable edits.

## Validation

After implementation:

- Run the skill validation script on each skill folder if available.
- Verify all skill names use lowercase letters, digits, and hyphens only.
- Verify every `SKILL.md` has valid YAML frontmatter with `name` and `description`.
- Verify descriptions start with "Use when..." and are trigger-focused.
- Inspect the generated files to ensure no placeholder TODOs remain.

## Constraints

- Keep skill bodies concise and action-oriented.
- Use references only for heavier reusable writing constraints.
- Do not create unrelated documentation files.
- The repository is currently not a git repository, so commit steps are not applicable unless git is initialized later.
