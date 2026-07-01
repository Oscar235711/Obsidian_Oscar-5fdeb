---
{"dg-publish":true,"permalink":"/log/","dg-note-properties":{}}
---

# Wiki Log

> 所有 wiki 操作的按时间顺序记录。只追加不修改。
> 格式：`## [YYYY-MM-DD] 操作 | 主题`
> 操作类型：ingest, update, query, lint, create, archive, delete
> 当本文件超过 500 条记录时，重命名为 log-YYYY.md，重新开始。

## [2026-06-28] create | Wiki 初始化
- 领域：项目管理/工作
- 创建了 SCHEMA.md、index.md、log.md
- 目录结构：raw/（articles, papers, transcripts, assets）、entities/、concepts/、comparisons/、queries/

## [2026-06-28] ingest | Claude-Mem 数据库迁移
- 来源：`C:\Users\25905\.claude-mem\chroma` (ChromaDB, cm__claude-mem 集合, 项目 25905 + 场景页文案)
- 数据范围：2026-04-30 ~ 2026-06-28，36 条用户提示 + 1 条文案任务
- 创建页面：
  - `entities/sealight-scenario-marketing.md` — 主项目枢纽（6 阶段工作流 + Mermaid 流程图）
  - `entities/sealight-prototype.md` — HTML 原型开发与 QA
  - `entities/sealight-three-in-one-page.md` — 三合一场景页重构
  - `entities/sealight-copywriting.md` — 文案定稿阶段
  - `concepts/scene-marketing-logic.md` — 场景营销 10 步认知模型
- 关联：所有页面通过 `[[wikilinks]]` 双向链接，主项目页含 Mermaid flowchart 展示阶段关系

## [2026-06-28] update | 知识库重构优化
- 重写 `entities/sealight-scenario-marketing.md`：合并 prototype/三合一/文案 三个碎片页面内容到主项目页，去除 AI 工具内部细节（session ID、seq 号等），使用团队可读风格，添加待补充标记
- 重写 `concepts/scene-marketing-logic.md`：从项目记录升级为可复用模板，增加使用方式、实战经验、提醒事项
- 新建 `entities/sealight-brand.md`：品牌概览页，含产品线、SKU、竞品、视觉参考（部分信息待补充）
- 旧页面（prototype/three-in-one/copywriting）标记为 [历史记录] 保留存档
- index.md 同步更新

## [2026-06-28] update | 文件名中文化 + 团队/成果信息补充
- 全部文档文件名改为中文（保留英文专有名词前缀如 sealight）
- 旧名 → 新名：
  - `sealight-scenario-marketing` → `sealight-场景营销专题页`
  - `sealight-brand` → `sealight-品牌概览`
  - `sealight-prototype` → `sealight-html原型`
  - `sealight-three-in-one-page` → `sealight-三合一场景页`
  - `sealight-copywriting` → `sealight-场景页文案`
  - `scene-marketing-logic` → `场景营销10步模型`
- 所有内部 `[[wikilinks]]` 同步修正
- 补充团队信息：设计 @江江 / 前端 @鹏飞 / 运营 @Swakee
- 补充项目成果：已上线 https://sealight-led.com/collection/by-scenario，LF3 已上架（不可见状态）
- 品牌概览页待截图解析后补全产品线信息
