# Fabula Skill — 领域概念寓言化技能集

将特定领域的关键概念转化为连贯的寓言故事，让抽象知识通过叙事自然流淌。

## 包含技能

本仓库提供 5 个协作式技能，覆盖从概念梳理到故事评审的完整工作流：

| 技能 | 用途 |
|------|------|
| **fable-concept-map** | 为某个学科、理论簇或知识体系构建 Markdown 概念图谱 |
| **fable-writing-plan** | 基于概念图谱制定章节写作计划、验收标准与进度追踪 |
| **fable-writing** | 将抽象概念转化为具象故事意象，产出寓言正文 |
| **fable-review** | 对照写作计划与概念图谱，评审寓言的准确性、隐喻纪律与可读性 |
| **fable-discipline-pipeline** | 一键式流水线，将完整学科直接转化为系列寓言学习材料 |

## 工作流程

使用以上技能时，建议按以下顺序推进：

```
概念图谱 ──→ 写作计划 ──→ 章节草稿 ──→ 评审修改
(concept-map.md)  (plan.md)    (drafts/)    (reviews/)
```

1. **概念梳理** — 使用 `fable-concept-map` 产出或更新 `concept-map.md`
2. **计划制定** — 使用 `fable-writing-plan` 基于图谱产出 `plan.md`
3. **故事写作** — 使用 `fable-writing` 按章节产出 `drafts/chapter-XX.md`
4. **评审迭代** — 使用 `fable-review` 产出 `reviews/chapter-XX-review.md`，并根据意见修改草稿

## 仓库结构

```text
.
├── skills/                  # 正式交付的技能目录
│   ├── fable-concept-map/
│   ├── fable-discipline-pipeline/
│   ├── fable-review/
│   ├── fable-writing/
│   └── fable-writing-plan/
├── .agents/skills/          # 本地代理可调用的技能镜像（应与 skills/ 保持同步）
├── cases/                   # 案例项目目录
│   ├── science-fable/       # 《我们凭什么相信》（67章全书）
│   ├── economics-fable/
│   └── quantum-fable/
├── docs/                    # 可复用说明、规范或参考文档
├── dev_notes/               # 开发过程记录与未定稿想法
├── test/                    # 测试与草稿
└── AGENTS.md                # 面向 AI 代理的详细工作规范
```

### 案例目录建议形态

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

## 快速开始

1. 在 `cases/` 下新建你的案例目录，如 `cases/my-topic-fable/`
2. 调用 `fable-concept-map` 技能，输入你的领域资料，生成 `concept-map.md`
3. 调用 `fable-writing-plan` 技能，基于图谱生成 `plan.md`
4. 按 `plan.md` 的章节顺序，逐章调用 `fable-writing` 产出草稿
5. 每章完成后调用 `fable-review` 进行评审，根据反馈修改

详细指令请参考各技能目录下的 `SKILL.md` 文件。

## 案例：《我们凭什么相信》

`cases/science-fable/` 是本项目最完整的案例，将科学哲学（波普尔、库恩、拉卡托斯）与统计推断（频率主义、贝叶斯、似然学派）的 67 个核心概念，改写为可独立阅读又彼此呼应的短篇寓言。全书按五个分册组织，正文不出现学科术语，概念映射放在正文后的讲解段。

- **全书索引**：[`cases/science-fable/drafts/index.md`](cases/science-fable/drafts/index.md) — 含每章故事题目、阅读提示与文件链接
- **写作计划**：[`cases/science-fable/plan.md`](cases/science-fable/plan.md)
- **章节草稿**：`cases/science-fable/drafts/volume-01/` ~ `volume-05/` + `supplementary/`

## 写作原则

- **隐喻优先**：寓言正文应间接承载概念，避免过早抛出学科术语
- **后置解释**：概念解释放在正文之后，明确映射故事意象与真实概念
- **顺序有据**：章节顺序遵守概念的前驱后继关系，而非简单罗列主题
