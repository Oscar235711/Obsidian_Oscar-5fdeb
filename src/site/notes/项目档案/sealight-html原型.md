---
{"dg-publish":true,"permalink":"/项目档案/sealight-html原型/","title":"Sealight 场景页 HTML 原型","tags":["deliverable","active","workflow"],"dg-note-properties":{"title":"Sealight 场景页 HTML 原型","created":"2026-06-28","updated":"2026-06-28","type":"entity","tags":["deliverable","active","workflow"],"sources":["claude-mem/observer-sessions"],"confidence":"high","parent":[["sealight-场景营销专题页"]]}}
---


# Sealight 场景页 HTML 原型

> 从策略文档到可视化 HTML prototype 的开发与部署全记录。主项目见 [[项目档案/sealight-场景营销专题页\|sealight-场景营销专题页]]。

## 开发周期
- **启动**：2026-05-06
- **部署**：2026-05-09
- **会话**：`4ca15f71-feea-4f86-9704-d56540157495`
- **工作目录**：`C:\Users\25905\research-inputs\sealight-v04\`

## 需求来源

### 触发原因
策略文档（Step 1-5 产物）对运营来说太抽象，需要可视化交付物用于团队讨论。

### 核心需求
1. **HTML 首页 + 专题页**（可部署到 Vercel 和腾讯云）
2. **首页 → 专题页 → 产品跳转架构**（程序框图）
3. **Figma 设计文件**
4. **专题页 SKU**：双色雾灯（已定）+ 推荐产品（待调）

### 品牌约束
- 色调参考：`SEALIGHT v04 Reader.html`
- 官网参考：sealight-led.com
- 新增参考：`0507新增参考文件/`

## 网站结构

```
首页 (index.html)
├── Night 驾驶场景页
├── Weather 天气场景页
├── Refresh 升级焕新页
└── Architecture 程序框图
```

### 交付物
- **XLSX 网站结构表**：子表 = 首页 + 4 个场景页名称
- **格式参照**：`SEALIGHT网站-2026表格.csv`
- **用途**：与运营对接时表格形式一目了然

## 部署

| 项目 | 详情 |
|------|------|
| URL | `https://sealight-scenario-page.vercel.app/` |
| 部署平台 | Vercel |
| 部署日期 | 2026-05-09 |
| 目标服务器 | Vercel + 腾讯云个人服务器 |

## QA 验收 (2026-05-09)

> 用户浏览器复验，6/6 全部通过。

| # | 检查项 | 状态 |
|---|--------|------|
| 1 | utm_term 路由正确（mountain→night, rain→weather, refresh→refresh） | ✅ |
| 2 | 375/390/430px 移动端无溢出（5 页均为 0px） | ✅ |
| 3 | 移动抽屉 ≡→× 切换，含 Home/Night/Weather/Refresh/Architecture + 3 折叠组 | ✅ |
| 4 | FAQ 单开逻辑正确 | ✅ |
| 5 | Weather/Refresh CTA 指向 sealight-led.com（target="_blank"） | ✅ |
| 6 | Favicon 5 页均加载（200） | ✅ |

### 已知问题
- `index.html` line 183：Trail 卡片 `<a>` 无 href → 建议改为 `<div>` 或 `<span>`（语义坏锚点）
- Tailwind CDN 生产环境 warning（不阻塞验收）

### 可分享性
- 压缩后解压可直接浏览 ✅
- Windows + Mac 兼容 ✅

## 相关实体
- [[项目档案/sealight-场景营销专题页\|sealight-场景营销专题页]] — 主项目总览
- [[项目档案/sealight-三合一场景页\|sealight-三合一场景页]] — 三合一页面重构
- [[方法论/场景营销10步模型\|场景营销10步模型]] — 场景营销 10 步方法论
