# 文档说明

本项目面向个人和小团队，文档只有三类，每类只做一件事，信息只有一个权威来源。

```
docs/
├── README.md              # 本文件
├── review.md              # 各类文档的目标、范围、越界示例
├── prd.template.md        # PRD 模板
├── design.template.md     # 设计模板
├── prd.md                 # PRD
├── design.md              # 设计
└── adr/
    ├── 0000-template.md   # ADR 模板
    └── NNNN-<slug>.md     # ADR
```

## 三类文档

- **PRD**：做什么、为谁做、什么场景、不做什么。
- **设计**：当前系统的中高层设计，随项目演进更新。
- **ADR**：一个决策一份文件，只描述当前决策及备选方案。

## 引用关系

设计 → ADR → PRD。后者不依赖前者，引用时用链接，不重复描述。

## ADR 状态

- 提案中：尚在讨论
- 发布：已定稿，生效中
- 放弃：不再生效，原因写在状态括号内，如 `放弃（被 0012 取代）`

放弃的 ADR 保留文件，只修改状态。

## 如何新建

- PRD：复制 `prd.template.md` 为 `docs/prd.md`
- 设计：复制 `design.template.md` 为 `docs/design.md`
- ADR：复制 `adr/0000-template.md` 为 `docs/adr/NNNN-<english-slug>.md`，编号取现有最大值加 1

设计文档过大时，可在 `docs/` 下按模块新增 `design-<模块>.md`，`design.md` 只保留总体与模块间协作。

## Review

定稿时几个人坐下来，对照 `review.md` 中对应类型的目标和范围，检查是否有越界内容。每份文档 frontmatter 的 `review` 字段指向对应章节。
