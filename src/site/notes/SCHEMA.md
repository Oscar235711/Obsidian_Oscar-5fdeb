---
{"dg-publish":true,"permalink":"/SCHEMA/","dg-note-properties":{}}
---

# Wiki Schema

## Domain
项目管理与工作知识库。覆盖项目管理方法论、项目记录、会议纪要、决策记录、工作流程、工具链等。

## Conventions
- 文件名：小写、连字符、无空格（如 `project-alpha-plan.md`）
- 每个 wiki 页面以 YAML frontmatter 开头（见下方格式）
- 使用 `[[wikilinks\|wikilinks]]` 进行页面间链接（每页至少 2 个出链）
- 更新页面时，务必更新 `updated` 日期
- 每个新页面必须添加到 `index.md` 对应分类下
- 每次操作必须追加到 `log.md`
- **来源标记：** 综合 3+ 来源的页面，在对应段落末尾追加 `^[素材库/articles/源文件名.md]`

## Frontmatter
```yaml
---
title: 页面标题
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [从下方标签分类中选取]
sources: [素材库/articles/源文件名.md]
# 可选质量标记：
confidence: high | medium | low
contested: true
contradictions: [冲突页面名]
---
```

### 素材库/ Frontmatter
```yaml
---
source_url: https://example.com/article
ingested: YYYY-MM-DD
sha256: <hex digest>
---
```

## Tag Taxonomy
项目类型：
- project     — 项目主体
- task        — 具体任务
- milestone   — 里程碑
- deliverable — 交付物

方法论：
- agile       — 敏捷
- scrum       — Scrum
- kanban      — 看板
- waterfall   — 瀑布

角色：
- stakeholder — 干系人
- manager     — 管理者
- developer   — 开发者
- designer    — 设计师

状态：
- planning    — 规划中
- active      — 进行中
- blocked     — 阻塞
- completed   — 已完成
- archived    — 已归档

元数据：
- meeting     — 会议
- decision    — 决策
- reference   — 参考资料
- template    — 模板
- workflow    — 工作流

规则：页面上的每个标签必须出现在此分类中。如需新标签，先在此添加再使用。

## Page Thresholds
- **创建页面** — 当实体/概念出现在 2+ 来源中，或是一个来源的核心内容
- **追加到已有页面** — 当来源提到已在 wiki 中覆盖的内容
- **不创建页面** — 仅顺带提及、次要细节、领域外内容
- **拆分页面** — 当页面超过 ~200 行时，拆分为子主题并添加交叉链接
- **归档页面** — 内容完全被取代时，移至 `_archive/` 并从 index 中移除

## Entity Pages
每页一个实体（项目、工具、团队等）。包含：
- 概述
- 关键事实和日期
- 与其它实体的关系（[[wikilinks\|wikilinks]]）
- 来源引用

## Concept Pages
每页一个概念或方法论主题。包含：
- 定义/说明
- 当前认知状态
- 待解决问题或争议
- 相关概念（[[wikilinks\|wikilinks]]）

## Comparison Pages
并排分析。包含：
- 比较对象和目的
- 比较维度（优先使用表格）
- 结论或综合
- 来源

## Update Policy
当新信息与已有内容冲突时：
1. 检查日期 — 新来源通常取代旧来源
2. 如确实矛盾，记录双方立场（含日期和来源）
3. 在 frontmatter 中标记：`contradictions: [页面名]`
4. 在 lint 报告中标记供用户审核
