# AGENTS.md

## 项目目标

创建一套skills，将特定领域的关键概念寓言化。

## 产物

相关 skills 已在 `skills/` 中。

## 仓库结构

- `skills/`：正式交付的技能目录。新增或修改技能时，优先维护这里。
- `.agents/skills/`：本仓库本地代理可调用的技能镜像。若修改 `skills/` 中已有技能，并且希望本仓库会话立即使用同一版本，应同步更新这里的同名 `SKILL.md`。
- `cases/`：案例项目目录，通常按 `cases/<subject>-fable/` 组织。
- `docs/`：可复用说明、规范或参考文档。
- `dev_notes/`：开发过程记录、临时设计笔记和未定稿想法。

不要只修改 `.agents/skills/` 而遗漏 `skills/` 中的正式交付件。

## 工作流程

领域寓言化任务通常按以下顺序推进：

1. 使用 `fable-concept-map` 产出或更新 `concept-map.md`。
2. 使用 `fable-writing-plan` 基于概念图谱产出或更新 `plan.md`。
3. 使用 `fable-writing` 按章节产出 `drafts/chapter-XX.md`。
4. 使用 `fable-review` 产出 `reviews/chapter-XX-review.md`，并根据审阅意见修改草稿。

案例目录建议保持以下形态：

```text
cases/<subject>-fable/
  concept-map.md
  plan.md
  drafts/
    chapter-01.md
  reviews/
    chapter-01-review.md
```

## 写作与评审原则

- 寓言正文应间接承载概念，不要在正文中过早写出概念名或学科术语。
- 概念解释应放在正文之后，并明确映射故事意象与真实概念。
- 章节顺序应遵守概念的前驱后继关系，而不是仅按资料目录或主题罗列。
- 评审时优先检查概念准确性、隐喻纪律、读者适配、章节连续性和验收标准。
- 若用户要求写作、计划、图谱或评审，先读取相关 `SKILL.md` 和当前案例中的 `concept-map.md`、`plan.md`、草稿或审阅文件。

## 禁止

禁止阅读 `archived/` 中的文档。搜索文件时显式排除 `archived/**`，例如：

```powershell
rg --files -g '!archived/**'
```

## 读取中文文件时使用 UTF-8

在 PowerShell 中读取中文、Markdown 或技能文件时，不要依赖默认编码。先设置输出编码，并在 `Get-Content` 中显式指定 UTF-8：

```powershell
[Console]::OutputEncoding = [System.Text.Encoding]::UTF8
$OutputEncoding = [System.Text.Encoding]::UTF8
Get-Content -Encoding UTF8 path\to\file.md
```

如果输出出现类似 `瀵撹█` 的乱码，应立即用 UTF-8 重新读取，不要基于乱码内容继续判断。

## 修改与验证

- 修改 Markdown 或技能文件后，用 UTF-8 重新读取关键片段，确认没有乱码、重复段落或破坏 front matter。
- 技能文件应保留 YAML front matter 中的 `name` 和 `description`，除非任务明确要求调整。
- 新增案例章节时，文件编号使用两位数：`chapter-01.md`、`chapter-02.md`。
- 不要随意重排无关章节、审阅文件或历史案例内容。
- 若 Git 因 dubious ownership 无法读取状态，不要擅自修改全局 Git 配置；继续完成文件级任务，并在最终回复中说明无法检查 Git 状态。
