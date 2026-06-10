# Fabula Skill — Domain Concept Fable Toolkit

Transform key concepts from any domain into coherent allegorical stories, letting abstract knowledge flow naturally through narrative.

## Included Skills

This repository provides 5 collaborative skills covering the complete workflow from concept mapping to story review:

| Skill | Purpose |
|-------|---------|
| **fable-concept-map** | Build a Markdown concept map for a discipline, theory cluster, or knowledge system |
| **fable-writing-plan** | Create a chapter writing plan, acceptance criteria, and progress tracker based on the concept map |
| **fable-writing** | Turn abstract concepts into concrete story imagery and produce fable drafts |
| **fable-review** | Evaluate fables against the writing plan and concept map for accuracy, metaphor discipline, and readability |
| **fable-discipline-pipeline** | One-click pipeline to transform an entire discipline into a series of fable-based learning materials |

## Workflow

When using the above skills, follow this order:

```
Concept Map ──→ Writing Plan ──→ Chapter Drafts ──→ Review & Revise
(concept-map.md)  (plan.md)      (drafts/)          (reviews/)
```

1. **Concept Mapping** — Use `fable-concept-map` to produce or update `concept-map.md`
2. **Plan Creation** — Use `fable-writing-plan` to produce `plan.md` based on the concept map
3. **Story Writing** — Use `fable-writing` to produce drafts chapter by chapter in `drafts/chapter-XX.md`
4. **Review Iteration** — Use `fable-review` to produce `reviews/chapter-XX-review.md` and revise drafts based on feedback

## Repository Structure

```text
.
├── skills/                  # Official skill delivery directory
│   ├── fable-concept-map/
│   ├── fable-discipline-pipeline/
│   ├── fable-review/
│   ├── fable-writing/
│   └── fable-writing-plan/
├── .agents/skills/          # Local agent skill mirror (keep in sync with skills/)
├── cases/                   # Case project directories
│   ├── science-fable/       # What Do We Believe and Why? — Fables on Evidence, Reasoning, and Judgment (67 chapters)
│   ├── economics-fable/
│   └── quantum-fable/
├── docs/                    # Reusable instructions, specs, or reference documents
├── dev_notes/               # Development notes and draft ideas
├── test/                    # Tests and drafts
└── AGENTS.md                # Detailed working specifications for AI agents
```

### Suggested Case Directory Layout

```text
cases/<subject>-fable/
  concept-map.md
  plan.md
  drafts/
    chapter-01.md
    chapter-02.md
  reviews/
    chapter-01-review.md
    chapter-02-review.md
```

## Quick Start

1. Create your case directory under `cases/`, e.g. `cases/my-topic-fable/`
2. Invoke the `fable-concept-map` skill with your domain materials to generate `concept-map.md`
3. Invoke the `fable-writing-plan` skill to generate `plan.md` based on the concept map
4. Invoke `fable-writing` chapter by chapter following the order in `plan.md`
5. Invoke `fable-review` after each chapter and revise based on feedback

For detailed instructions, refer to the `SKILL.md` file in each skill directory.

## Case Study: What Do We Believe and Why?

`cases/science-fable/` is the most complete case in this project. It rewrites 67 core concepts from philosophy of science (Popper, Kuhn, Lakatos) and statistical inference (frequentism, Bayesianism, likelihood school) into interlinked short fables. The book is organized into five volumes; disciplinary terms do not appear in the main text, and concept mappings are placed in explanatory sections after each story.

- **Full Book Index**: [`cases/science-fable/drafts/index.md`](cases/science-fable/drafts/index.md) — includes chapter titles, reading notes, and file links
- **Writing Plan**: [`cases/science-fable/plan.md`](cases/science-fable/plan.md)
- **Chapter Drafts**: `cases/science-fable/drafts/volume-01/` ~ `volume-05/` + `supplementary/`

## Writing Principles

- **Metaphor First**: Fable text should carry concepts indirectly; avoid throwing out disciplinary terms too early
- **Postponed Explanation**: Place concept explanations after the main text, explicitly mapping story imagery to real concepts
- **Order with Reason**: Chapter order should respect prerequisite and successor relationships between concepts, not simply list topics
