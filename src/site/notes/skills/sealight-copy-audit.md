---
{"dg-publish":true,"permalink":"/skills/sealight-copy-audit/","dg-note-properties":{}}
---

# 英文文案合规审计

> Sealight 英文营销文案合规审计技能
> 来源：`C:\Users\25905\Documents\Cowork专用\sealight-skills-v1`
> Hermes 技能路径：`sealight/sealight-copy-audit`

## 功能

对面向北美 DTC 消费者的英文营销文案做四层审计，输出带决策按钮的单文件 HTML 审计报告。审计立场：**宁可多标，不可漏标**。

## 触发条件

用户提到"文案审核"、"合规检查"、"copy audit"、"检查文案"、"审一下这段英文"，或上传含英文营销文案的 xlsx / 截图 / 文本，且语境为 Sealight / SuncentAuto。

## 四层审计

| 级别 | 类型 | 处理 |
|------|------|------|
| A 级 | 合规红线 | 逐字引用 + 红线编号 + 替换建议 |
| B 级 | 官网不一致 | 产品名/参数/质保与官网不符 |
| C 级 | 拼写语法 | 直接给修正版 |
| D 级 | Chinglish / 流畅度 | 改写建议 |

## 核心红线（R 系列）

- **R1**：禁止出现 IIHS（任何形式）
- **R2**：禁止 DOT / FMVSS 108 合规声称
- **R3**：禁止 SEMA 标准声称
- **R4**：禁止虚构产品名、系列名、参数
- **R5**：禁止无据的绝对化与因果声称
- **R6**：质保承诺必须与官网一致（90-day）

## 关联

- [[entities/sealight-品牌概览\|sealight-品牌概览]]
- [[skills/sealight-image-prompts\|sealight-image-prompts]] — 提示词合规约束来源
- [[entities/sealight-场景营销专题页\|sealight-场景营销专题页]]

## 参考

- 合规红线：`references/redlines.md`
- 产品线快照：`references/products.md`
- 报告模板：`references/report-template.html`
