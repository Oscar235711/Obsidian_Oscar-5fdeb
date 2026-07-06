---
{"dg-publish":true,"permalink":"/skills/HTML代码审查可视化/","dg-note-properties":{}}
---

# HTML 代码审查可视化

> 基于 [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/) 的三种模式
> Hermes 技能路径：`software-development/html-code-review`

## 三种模式

| 模式 | 适用场景 | 关键元素 |
|------|---------|----------|
| **Annotated PR** | 审查已有 PR，逐文件标注问题 | 风险地图、diff 渲染、气泡评论、严重度标签 |
| **PR Writeup** | 提交者视角，向 reviewer 说明改动 | 动机→Before/After→逐文件 tour→Test→Rollout |
| **Module Map** | 理解陌生代码库/包的结构 | SVG 方框箭头图、入口点列表、数据模型 |

## 共享设计系统

所有模式共用一套配色和排版变量：

```css
:root {
  --ivory:    #FAF9F5;   /* 页面背景 */
  --slate:    #141413;   /* 标题色 */
  --clay:     #D97757;   /* 强调/警告 */
  --oat:      #E3DACC;   /* 次要底色 */
  --olive:    #788C5D;   /* 安全/新增 */
  --rust:     #B04A3F;   /* 删除 */
  --gray-150: #F0EEE6;   /* 浅灰底 */
  --gray-300: #D1CFC5;   /* 边框 */
  --gray-500: #87867F;   /* 次级文字 */
  --gray-700: #3D3D3A;   /* 正文 */
  --serif: ui-serif, Georgia, serif;
  --sans:  system-ui, sans-serif;
  --mono:  ui-monospace, SF Mono, monospace;
}
```

## 模式一：Annotated PR Review

审查已有 PR，逐文件标注发现的问题。

- **PR Header**：仓库、编号、标题、作者、分支、stat（+N/-N, N files）
- **What this PR does**：要点列表
- **Risk Map**：彩色芯片（attention / medium / safe），点击跳转到文件区块
- **Files**：每个文件一张卡片（路径 + 风险标签 + diff 统计）
  - 深色背景 rendered diff（行号 | +/- | 代码）
  - 评论气泡（blocking 橙色 / nit 灰色）带行号锚点
- **Collapsed files**：低风险文件折叠
- **Footer**：checklist 待办

## 模式二：PR Writeup

提交者视角，向 reviewer 系统说明改动。

- **Header**：PR #、标题、分支、stat、原始 prompt
- **Motivation & Context**：为什么改、背景
- **Before → After**：双栏对比
- **File-by-file tour**：逐文件走查（路径 + delta + why）
- **Testing**：测试说明
- **Rollout plan**：上线步骤
- **Known limitations**：已知局限
- **Sidebar TOC**：粘性导航

## 模式三：Module Map

理解陌生代码包的结构和调用关系。

- **Architecture**：SVG 方框箭头图（自上而下或左到右）
- **Entry points**：入口函数/文件
- **Key types / Data model**：核心类型/数据结构
- **Sidebar**：快速索引

## 触发条件

- 用户说「review 这个 PR」「帮我 code review」
- 用户说「写个 PR writeup」「给 reviewer 说明一下改了什么」
- 用户说「这个模块是什么结构」「画个调用图」「分析代码结构」

## 操作流程

1. 获取代码上下文（git diff / 文件读取 / 目录结构）
2. 判断意图 → 选模式
3. 基于实际代码填充模板
4. 输出自包含 HTML → 告知路径

## 输出规范

- 单文件自包含，CSS/JS 全部内嵌
- 文件名：`PR-{num}-review.html` / `PR-{num}-writeup.html` / `module-map-{name}.html`
- 深色 diff 背景用 `#141413`
- 不引入外部依赖

## 关联

- [[skills/照明周报全品类分析\|照明周报全品类分析]]
- [[skills/sealight-copy-audit\|英文文案合规审计]]
- [[skills/sealight-image-prompts\|素材需求与图片提示词]]
