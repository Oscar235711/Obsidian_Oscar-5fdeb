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
- 目录结构：素材库/（articles, papers, transcripts, assets）、项目档案/、方法论/、竞品对比/、数据查询/

## [2026-06-28] ingest | Claude-Mem 数据库迁移
- 来源：`C:\Users\25905\.claude-mem\chroma` (ChromaDB, cm__claude-mem 集合, 项目 25905 + 场景页文案)
- 数据范围：2026-04-30 ~ 2026-06-28，36 条用户提示 + 1 条文案任务
- 创建页面：
  - `项目档案/sealight-scenario-marketing.md` — 主项目枢纽（6 阶段工作流 + Mermaid 流程图）
  - `项目档案/sealight-prototype.md` — HTML 原型开发与 QA
  - `项目档案/sealight-three-in-one-page.md` — 三合一场景页重构
  - `项目档案/sealight-copywriting.md` — 文案定稿阶段
  - `方法论/scene-marketing-logic.md` — 场景营销 10 步认知模型
- 关联：所有页面通过 `[[wikilinks]]` 双向链接，主项目页含 Mermaid flowchart 展示阶段关系

## [2026-06-28] update | 知识库重构优化
- 重写 `项目档案/sealight-scenario-marketing.md`：合并 prototype/三合一/文案 三个碎片页面内容到主项目页，去除 AI 工具内部细节（session ID、seq 号等），使用团队可读风格，添加待补充标记
- 重写 `方法论/scene-marketing-logic.md`：从项目记录升级为可复用模板，增加使用方式、实战经验、提醒事项
- 新建 `项目档案/sealight-brand.md`：品牌概览页，含产品线、SKU、竞品、视觉参考（部分信息待补充）
- 旧页面（prototype/three-in-one/copywriting）标记为 [历史记录] 保留存档
- index.md 同步更新

## [2026-06-28] update | 文件名中文化 + 团队/成果信息补充
- 全部文档文件名改为中文（保留英文专有名词前缀如 sealight）
- 旧名 → 新名见前次记录
- 所有内部 `[[wikilinks]]` 同步修正
- 补充团队信息：设计 @江江 / 前端 @鹏飞 / 运营 @Swakee
- 补充项目成果：已上线 https://sealight-led.com/collection/by-scenario，LF3 已上架（不可见状态）

## [2026-07-06] update | 转正述职 · 运营阶段笔记整理 + 目录中文化

### 目录重命名
- comparisons → 竞品对比
- concepts → 方法论
- entities → 项目档案
- queries → 数据查询
- raw → 素材库
- meta-ads、skills 保留英文（专有名词）

### 新建笔记（8 篇）
- `转正述职-运营阶段总览.md` — 述职主入口，KPI + 时间线 + 能力成长 + 导航
- `运营阶段工作完成情况表.md` — 按月/阶段记录工作内容+产出+收获
- `项目档案/培训记录.md` — 10 次培训汇总
- `项目档案/项目成果.md` — 10 份项目输出
- `项目档案/场景页搭建.md` — 场景页从调研到上线完整记录
- `项目档案/Easter-EDM策划.md` — Easter EDM 双层策略
- `项目档案/Roadtrip媒体激励活动.md` — KOL 产品激励活动
- `方法论/周报工作流.md` — 14 周周报自动化进化

### 修改
- home.md — 新增「运营阶段述职」导航区
- index目录.md — 全部索引更新
- 全局 wikilinks 路径更新（批量替换旧目录名）

## [2026-07-06] update | 内容体检 + 笔记配图

### 内容修补
- 修正一批误指向的内部双链：文案审计、素材提示词、场景营销专题页等改为明确路径链接
- 将示例型 `[[wikilinks]]` 保持为代码写法，避免被误识别为真实页面
- `sealight-Facebook拉新广告配置`、`sealight-S1Pro独立日出行周方案`、`sealight-S7S广告素材提示词` 补充 `dg-publish: true`

### 配图
- 新建 `素材库/images/`，加入首页、述职、场景营销、Meta Ads、S1 Pro、S7S 等 7 个视觉资产
- 在首页、述职总览、场景营销专题页、场景页搭建、场景营销 10 步模型、S7S 素材提示词、S1 Pro 广告方案、Meta Ads 学习笔记中嵌入图片

## [2026-07-06] fix | 网页端信息图可读性

- 将述职总览、场景营销 10 步模型两张文字型 SVG 重做为低密度、高对比版本
- 生成同名 PNG 作为网页端引用，避免 Digital Garden 发布后 SVG 样式被处理导致文字发黑或过小
- 将 Meta Ads 工作台图替换为大字版投放框架 PNG，避免假 UI 小字在网页端显脏
