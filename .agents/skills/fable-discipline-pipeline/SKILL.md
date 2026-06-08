---
name: fable-discipline-pipeline
description: Use when a user wants to turn a discipline, subject system, course, theory cluster, or knowledge framework into connected fables or fable-based learning material
---

# Fable Discipline Pipeline

## Overview

Coordinate the full workflow: concept map -> writing plan -> fable draft -> objective review. Preserve the discipline's conceptual dependencies so the final stories teach a system, not a list.

## Workflow

1. Clarify the discipline scope, source materials, target reader level, writing style, and desired output folder.
2. Use `fable-concept-map` to create or update `concept-map.md`.
3. Use `fable-writing-plan` to create or update `plan.md`.
4. Use `fable-writing` for each planned chapter or concept cluster.
5. Use `fable-review` after each fable draft and revise until it passes the plan's acceptance criteria.

## Output Discipline

- Keep stage outputs in explicit files unless the user asks for chat-only output.
- Never skip the concept map when the source discipline is broad or structurally unfamiliar.
- Never write chapters as isolated concept explanations. Carry forward predecessor-successor relationships from the concept map.
- When a stage output already exists, inspect it before deciding whether to update or reuse it.
- Prefer a foldered output structure when the project has multiple chapters:
  - `concept-map.md`
  - `plan.md`
  - `drafts/chapter-01.md`
  - `reviews/chapter-01-review.md`
- Reuse concept IDs from the concept map in the plan, draft headers, and review notes.

## Handoff Checklist

Before moving to the next stage, confirm:

| Stage | Required evidence |
| --- | --- |
| Concept map | Every key concept has a summary, layer, predecessors, successors, and fable hooks. |
| Writing plan | Chapters follow conceptual dependencies and include acceptance criteria. |
| Fable draft | The story avoids direct terminology in the body and includes explanation plus check questions. |
| Review | The draft has a pass/revise decision and actionable edits. |

## Common Mistakes

- Treating the concept map as a glossary.
- Planning chapters by topic popularity instead of conceptual dependency.
- Letting characters explain the concept directly inside the fable.
- Reviewing only the prose quality and ignoring concept coverage.
