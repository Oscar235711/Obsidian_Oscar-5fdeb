---
{"dg-publish":true,"permalink":"/skills/sealight-image-prompts/","dg-note-properties":{}}
---

# 素材需求与图片提示词

> Sealight 素材需求规格 + GPT Image 2 提示词生成技能
> 来源：`C:\Users\25905\Documents\Cowork专用\sealight-skills-v1`
> Hermes 技能路径：`sealight/sealight-image-prompts`

## 功能

把模糊的配图需求转成「结构化素材规格 + 可直接复制的英文提示词」，风格、品牌色、尺寸、合规约束一次到位。

## 触发条件

用户提到"素材需求"、"提示词"、"参考图"、"出图"、"image prompt"、"GPT Image"，或上传含空白"素材需求/素材参考图"列的表格/截图，且语境为 Sealight / SuncentAuto / 汽车LED照明。

## 工作流

1. 确认素材类型与缺口（大图+小角标都要覆盖）
2. 加载基准：品牌色板 + 提示词模板
3. 生成：每条素材 = 规格 + 提示词
4. 输出：默认钉钉 tab 表，素材>10条出 HTML 对照表

## 关联

- [[项目档案/sealight-品牌概览\|sealight-品牌概览]]
- [[skills/sealight-copy-audit\|sealight-copy-audit]] — 合规约束（IIHS/DOT/logo 红线）
- [[项目档案/sealight-场景营销专题页\|sealight-场景营销专题页]]

## 参考

- 品牌色板：`references/brand-tokens.md`
- 提示词模板与硬规则：`references/prompt-templates.md`
