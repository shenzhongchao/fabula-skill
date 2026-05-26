---
name: fable-concept-map
description: Use when building a Markdown concept map for a discipline, subject system, theory cluster, course, or knowledge framework before writing fables or allegorical stories
---

# Fable Concept Map

## Overview

Build a concept map that lets a reader see the discipline's whole structure: origin questions, layers, time order, predecessor-successor relationships, and cross-branch dependencies.

## Required Output

Write a Markdown file, usually `concept-map.md`, with these sections:

1. Discipline scope and central question.
2. Global structure: historical periods, logical layers, or major branches.
3. Dependency overview: short explanation of how the layers connect.
4. Concept entries grouped by layer or branch.
5. Cross-branch relationship table.
6. Coverage notes: important omissions, uncertain areas, and source limits.
7. Concept ID index: stable IDs for use by `plan.md` and chapter cards.

## Concept Entry Contract

Every concept must include a summary. Use this shape unless a better local structure is clearly needed:

```markdown
### C01 - Concept Name

- ID: C01
- Summary: 2-4 sentences explaining what problem this concept solves, its core meaning, and why it matters.
- Layer:
- Predecessors:
- Successors:
- Historical or logical position:
- Source evidence:
- Confidence:
- Key relationships:
- Common misunderstandings:
- Fable hooks:
```

## Mapping Rules

- Do not produce a simple unordered glossary.
- Prefer dependency order over alphabetical order.
- Make predecessor and successor links explicit, even when they are logical rather than historical.
- Include time order when the discipline developed through recognizable historical stages.
- Include cross-branch links when one concept from a branch changes the meaning or use of another branch.
- Give each concept a stable ID and reuse that ID in later plans.
- Add source evidence for any concept whose summary depends on a specific reference.
- Mark confidence when the source set is incomplete or the concept is still disputed.
- Use `Unknown` only when source material is insufficient; add a coverage note explaining what is missing.

## Quality Bar

A good concept map lets `fable-writing-plan` decide chapter order without rereading all source material. It should show why concept B comes after concept A, which concepts can be combined into one story, and which concepts still need coverage.

## Relationship Table

Use a table for dependency clarity when the discipline is non-trivial:

| From ID | Relation | To ID | Why it matters |
| --- | --- | --- | --- |
| C01 | enables | C02 | C02 depends on the distinction established in C01. |
| C02 | conflicts-with | C05 | The two ideas answer the same question differently. |

## ID Index

Keep a short index near the end of the file when the map is non-trivial:

| ID | Concept | Layer | Summary cue |
| --- | --- | --- | --- |
| C01 | Concept Name | Foundation | First distinction the rest depends on. |
| C02 | Concept Name | Core | Extends or refines C01. |

## Common Mistakes

- Writing one-line summaries that only rename the concept.
- Listing famous names without explaining conceptual function.
- Hiding uncertainty instead of marking source limits.
- Creating branches that never reconnect.
