# Fable Discipline Skills Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a repository-local skill suite for turning a discipline's concept system into connected fable stories.

**Architecture:** Create one orchestrator skill and four sub-skills under `skills/`. Keep each `SKILL.md` concise, trigger-focused, and action-oriented. Put the heavier fable-writing prompt into a `references/` file used by `fable-writing` and `fable-review`.

**Tech Stack:** Markdown skill files, YAML frontmatter, PowerShell file inspection, optional Codex skill validation scripts from `skill-creator`.

---

## File Structure

- Create: `skills/fable-discipline-pipeline/SKILL.md`
  - Orchestrates concept mapping, planning, writing, and review.
- Create: `skills/fable-concept-map/SKILL.md`
  - Defines the concept-map output contract, including a summary for every concept.
- Create: `skills/fable-writing-plan/SKILL.md`
  - Defines `plan.md` structure, chapter sequencing, acceptance criteria, and progress tracking.
- Create: `skills/fable-writing/SKILL.md`
  - Defines fable-writing workflow and references the reusable prompt constraints.
- Create: `skills/fable-writing/references/fable-prompt.md`
  - Stores the reusable fable prompt rules adapted from `dev_notes/refs/寓言prompt.md`.
- Create: `skills/fable-review/SKILL.md`
  - Defines objective review criteria and revision output.

## Task 1: Create Skill Directories

**Files:**
- Create directory: `skills/fable-discipline-pipeline`
- Create directory: `skills/fable-concept-map`
- Create directory: `skills/fable-writing-plan`
- Create directory: `skills/fable-writing/references`
- Create directory: `skills/fable-review`

- [ ] **Step 1: Create directories**

Run:

```powershell
New-Item -ItemType Directory -Force -Path `
  'skills\fable-discipline-pipeline', `
  'skills\fable-concept-map', `
  'skills\fable-writing-plan', `
  'skills\fable-writing\references', `
  'skills\fable-review' | Out-Null
```

Expected: command exits with code 0.

- [ ] **Step 2: Verify directories exist**

Run:

```powershell
Get-ChildItem -LiteralPath 'skills' -Directory | Select-Object -ExpandProperty Name
```

Expected names include:

```text
fable-concept-map
fable-discipline-pipeline
fable-review
fable-writing
fable-writing-plan
```

## Task 2: Add Orchestrator Skill

**Files:**
- Create: `skills/fable-discipline-pipeline/SKILL.md`

- [ ] **Step 1: Write `SKILL.md`**

Content:

```markdown
---
name: fable-discipline-pipeline
description: Use when a user wants to turn a discipline, subject system, course, theory cluster, or knowledge framework into connected寓言故事 or fable-based learning material
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

## Handoff Checklist

Before moving to the next stage, confirm:

| Stage | Required evidence |
| --- | --- |
| Concept map | Every key concept has a summary, layer, predecessors, successors, and fable hooks. |
| Writing plan | Chapters follow conceptual dependencies and include acceptance criteria. |
| Fable draft | The story avoids direct terminology in the正文 and includes explanation plus check questions. |
| Review | The draft has a pass/revise decision and actionable edits. |

## Common Mistakes

- Treating the concept map as a glossary.
- Planning chapters by topic popularity instead of conceptual dependency.
- Letting characters explain the concept directly inside the fable.
- Reviewing only the prose quality and ignoring concept coverage.
```

- [ ] **Step 2: Verify frontmatter and trigger wording**

Run:

```powershell
Get-Content -LiteralPath 'skills\fable-discipline-pipeline\SKILL.md' -First 6
```

Expected: frontmatter contains only `name` and `description`, and description starts with `Use when`.

## Task 3: Add Concept Map Skill

**Files:**
- Create: `skills/fable-concept-map/SKILL.md`

- [ ] **Step 1: Write `SKILL.md`**

Content:

```markdown
---
name: fable-concept-map
description: Use when building a Markdown concept map for a discipline, subject system, theory cluster, course, or knowledge framework before writing fables or寓言故事
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

## Concept Entry Contract

Every concept must include a summary. Use this shape unless a better local structure is clearly needed:

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

## Mapping Rules

- Do not produce a simple unordered glossary.
- Prefer dependency order over alphabetical order.
- Make predecessor and successor links explicit, even when they are logical rather than historical.
- Include time order when the discipline developed through recognizable historical stages.
- Include cross-branch links when one concept from a branch changes the meaning or use of another branch.
- Use `Unknown` only when source material is insufficient; add a coverage note explaining what is missing.

## Quality Bar

A good concept map lets `fable-writing-plan` decide chapter order without rereading all source material. It should show why concept B comes after concept A, and which concepts can be combined into one story.

## Common Mistakes

- Writing one-line summaries that only rename the concept.
- Listing famous names without explaining conceptual function.
- Hiding uncertainty instead of marking source limits.
- Creating branches that never reconnect.
```

- [ ] **Step 2: Verify per-concept summary requirement**

Run:

```powershell
Select-String -LiteralPath 'skills\fable-concept-map\SKILL.md' -Pattern 'Every concept must include a summary'
```

Expected: one match.

## Task 4: Add Writing Plan Skill

**Files:**
- Create: `skills/fable-writing-plan/SKILL.md`

- [ ] **Step 1: Write `SKILL.md`**

Content:

```markdown
---
name: fable-writing-plan
description: Use when creating a chapter plan, plan.md, acceptance criteria, or progress tracker for fables or寓言故事 based on a discipline concept map
---

# Fable Writing Plan

## Overview

Turn `concept-map.md` into a practical writing plan. Chapters must follow conceptual dependencies, not a loose list of topics.

## Inputs

- `concept-map.md` or equivalent concept map.
- Target reader level:小学, 初中, 高中, 大学, or a custom reader profile.
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

## Chapter Card Template

```markdown
### Chapter N: Working Title

- Concept cluster:
- Depends on:
- Enables:
- Target reader:
- Story premise:
- Short draft:
- Concepts that must stay implicit in正文:
- Explanation points after正文:
- Acceptance criteria:
- Status: planned
```

## Planning Rules

- Start with concepts that unlock later concepts.
- Combine concepts only when their relationship can be dramatized in one scene.
- Split concepts when combining them would force explanation inside the story.
- Write acceptance criteria that `fable-review` can judge directly.
- Add continuity notes whenever multiple chapters share characters, setting, or cause-effect history.

## Common Mistakes

- Treating chapter order as a table of contents copied from the source.
- Omitting acceptance criteria.
- Planning stories around terminology instead of conflicts, choices, and consequences.
- Forgetting to track review status.
```

- [ ] **Step 2: Verify `plan.md` contract**

Run:

```powershell
Select-String -LiteralPath 'skills\fable-writing-plan\SKILL.md' -Pattern 'Required `plan.md` Sections'
```

Expected: one match.

## Task 5: Add Fable Writing Skill and Reference

**Files:**
- Create: `skills/fable-writing/SKILL.md`
- Create: `skills/fable-writing/references/fable-prompt.md`

- [ ] **Step 1: Write reference file**

Content for `skills/fable-writing/references/fable-prompt.md`:

```markdown
# Fable Prompt Constraints

Write a fable around a target concept, but do not directly name the concept in the fable正文. Let the story carry the meaning indirectly.

## Fable Feel

- Length: within 1000 Chinese characters unless the plan says otherwise.
- World: fictional, concrete, and small enough to hold in one scene or a few turns.
- Characters: no more than three major characters, preferably two.
- Reveal rhythm: avoid concept names and field terminology in the正文; let the reader infer the idea near the end.
- Narrative discipline: details and consequences carry meaning; characters should not become lecturers.

## Avoid These Tropes

Images: 钟, 河流, 镜子, 迷宫, 织布机, 地图, 灯塔, 棋盘, 回声, 影子, 沙漏, 风, 蜡烛, 种子, 桥, 星辰, 蝴蝶, 蛛网.

Places: avoid names like 回声城, 记忆之村, 遗忘之海, 寂静谷. Use ordinary geography or no named place.

Structures:

- 旅行者求教智者
- 村庄异象 -> 众人顿悟
- 孩童一句话点醒大人
- 师徒辩难
- 临终遗言

Roles: 钟表匠, 图书管理员, 隐士, 说书人, 老船夫, 酿酒师, 铁匠, 抄经人.

Openings: avoid 从前有个地方, 某天某人遇见某事, 在很远的山里. Start inside the scene.

## Preferred Angles

- Non-human viewpoint: tool, animal, plant, household object, machine, or institution.
- Concrete modern scenes: insurance claim, elevator maintenance, market stall, night nurse station, delivery station, housing agency, sorting line.
- Micro-scale events: one transaction, appointment, call, repair, inspection, or handoff.

## Output Format

1. Fable正文: story only, no title or preface.
2. Concept explanation: name the concept, identify discipline or school, define it, and map story elements to concept parts.
3. Check questions:
   - Understanding question: specific and answerable.
   - Transfer question: asks the reader to apply the concept to a related case.
```

- [ ] **Step 2: Write `SKILL.md`**

Content:

```markdown
---
name: fable-writing
description: Use when drafting, revising, or continuing fables or寓言故事 from a concept map or writing plan for teaching discipline concepts
---

# Fable Writing

## Overview

Write fables that teach concepts indirectly through concrete scenes. Use short plain description, clear explanation, and gentle imagery: 汪曾祺的白描 + 叶圣陶的明白 + 丰子恺的温柔寓言感.

## Required Context

Before writing, inspect the relevant part of `plan.md`. If available, also inspect `concept-map.md` for concept summaries and predecessor-successor links.

For detailed constraints, read `references/fable-prompt.md` when drafting or reviewing a fable's shape.

## Drafting Workflow

1. Identify the chapter card, concept cluster, target reader, and acceptance criteria.
2. Decide which concept names and domain terms must stay out of the fable正文.
3. Choose one concrete scene and no more than three major characters.
4. Draft the fable正文 with short sentences, visible objects, and minimal explanation.
5. Add a clear concept explanation after the正文.
6. Add one understanding question and one transfer question.
7. Check continuity against earlier chapters if this belongs to a larger work.

## Style Rules

- Use concrete nouns and actions before abstractions.
- Keep the正文 indirect; put explicit teaching in the explanation section.
- Make causality visible through what characters try, notice, lose, or gain.
- Prefer one strong scene over a tour of examples.
- Keep language smooth enough for the target reader level.

## Output Format

```markdown
[Fable正文 only]

## 概念解析

- 概念名称：
- 所属学科或流派：
- 核心定义：
- 故事映射：

## 检验问题

1. 理解检验：
2. 迁移检验：
```

## Common Mistakes

- Naming the concept inside the fable正文.
- Turning a character into a teacher who explains the concept.
- Using banned stock images from the reference prompt.
- Breaking continuity with earlier chapters.
- Writing beautiful prose that no longer maps to the planned concept.
```

- [ ] **Step 3: Verify reference link**

Run:

```powershell
Select-String -LiteralPath 'skills\fable-writing\SKILL.md' -Pattern 'references/fable-prompt.md'
```

Expected: one match.

## Task 6: Add Fable Review Skill

**Files:**
- Create: `skills/fable-review/SKILL.md`

- [ ] **Step 1: Write `SKILL.md`**

Content:

```markdown
---
name: fable-review
description: Use when evaluating, scoring, accepting, or giving revision advice for fables or寓言故事 against a writing plan, concept map, reader level, or acceptance criteria
---

# Fable Review

## Overview

Judge whether a fable teaches the intended concepts accurately while remaining a real fable. Review concept coverage, story discipline, reader fit, continuity, and plan acceptance criteria.

## Required Inputs

- Fable draft.
- Relevant chapter card or acceptance criteria from `plan.md`.
- Relevant concept entries from `concept-map.md`.
- Target reader level and style, if not already in the plan.
- `fable-writing/references/fable-prompt.md` when checking trope bans and output shape.

## Review Procedure

1. Restate the target concept cluster and acceptance criteria.
2. Check whether every required concept is represented accurately.
3. Check whether the正文 avoids concept names and field terminology until the explanation section.
4. Check narrative continuity with earlier chapters when applicable.
5. Check target reader fit: vocabulary, sentence complexity, image clarity, and explanation level.
6. Check the two questions: one must test understanding, one must test transfer.
7. Return pass/revise decision with specific edits.

## Score Table

Use a 1-5 score for each dimension:

| Dimension | What to inspect |
| --- | --- |
| Concept accuracy | Does the mapping match the concept-map summary and relationships? |
| Concept completeness | Are required concepts and dependencies covered? |
| Fable indirectness | Does the正文 teach through scene and consequence instead of explanation? |
| Style fit | Does it match the requested plain, clear, gentle style? |
| Reader fit | Can the target reader understand the story and explanation? |
| Continuity | Does it preserve shared setting, character memory, and cause-effect links? |
| Prompt discipline | Does it avoid banned images, roles, structures, places, and openings? |
| Question quality | Are understanding and transfer questions specific and answerable? |

## Output Format

```markdown
## 评判结论

- Decision: Pass / Revise
- Main reason:

## Score Table

| Dimension | Score | Evidence | Required edit |
| --- | ---: | --- | --- |

## Concept Mapping Check

## Acceptance Criteria Check

## Revision Advice
```

## Common Mistakes

- Giving only literary feedback.
- Accepting a pleasant story with weak concept mapping.
- Missing terminology leaked inside the正文.
- Giving vague advice such as "make it clearer" without naming exact edits.
```

- [ ] **Step 2: Verify pass/revise decision requirement**

Run:

```powershell
Select-String -LiteralPath 'skills\fable-review\SKILL.md' -Pattern 'Pass / Revise'
```

Expected: one match.

## Task 7: Validate All Skills

**Files:**
- Inspect: `skills/*/SKILL.md`

- [ ] **Step 1: Check files exist**

Run:

```powershell
Get-ChildItem -LiteralPath 'skills' -Directory | ForEach-Object {
  Join-Path $_.FullName 'SKILL.md'
} | ForEach-Object {
  if (-not (Test-Path -LiteralPath $_)) { throw "Missing $_" }
}
```

Expected: command exits with code 0.

- [ ] **Step 2: Scan for placeholders**

Run:

```powershell
Select-String -Path 'skills\*\SKILL.md','skills\*\references\*.md' -Pattern 'TODO|TBD|placeholder|待定'
```

Expected: no matches.

- [ ] **Step 3: Check frontmatter fields**

Run:

```powershell
Get-ChildItem -LiteralPath 'skills' -Directory | ForEach-Object {
  $file = Join-Path $_.FullName 'SKILL.md'
  $first = Get-Content -LiteralPath $file -First 4
  if ($first[0] -ne '---') { throw "Missing opening frontmatter in $file" }
  if ($first[1] -notmatch '^name: [a-z0-9-]+$') { throw "Bad name in $file" }
  if ($first[2] -notmatch '^description: Use when ') { throw "Bad description in $file" }
  if ($first[3] -ne '---') { throw "Unexpected frontmatter shape in $file" }
}
```

Expected: command exits with code 0.

- [ ] **Step 4: Run official quick validator if available**

Run:

```powershell
$validator = 'C:\Users\gcszc\.codex\skills\.system\skill-creator\scripts\quick_validate.py'
if (Test-Path -LiteralPath $validator) {
  Get-ChildItem -LiteralPath 'skills' -Directory | ForEach-Object {
    python $validator $_.FullName
    if ($LASTEXITCODE -ne 0) { throw "Validation failed: $($_.FullName)" }
  }
} else {
  Write-Output "quick_validate.py not found; manual validation already completed."
}
```

Expected: either all validations pass, or the script is not found and the manual checks have passed.

- [ ] **Step 5: Note git status**

Run:

```powershell
git status --short
```

Expected in this repository today: fails with `fatal: not a git repository`. Do not initialize git unless the user asks.

## Self-Review

- Spec coverage: Tasks create all five requested skills, include the per-concept summary contract, include the fable prompt reference, and include validation.
- Placeholder scan: Plan intentionally uses no TODO/TBD placeholders.
- Type consistency: Skill names and paths match the design spec.
