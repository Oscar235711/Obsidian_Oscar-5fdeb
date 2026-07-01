---
{"dg-publish":true,"permalink":"/skills/claude-ads-付费广告审计技能/","tags":["claude-code","广告审计","PPC","付费广告","AI工具","开源"],"dg-note-properties":{"type":"tool","domain":"ai-marketing","tags":["claude-code","广告审计","PPC","付费广告","AI工具","开源"],"source":"https://github.com/AgriciDaniel/claude-ads","author":"Agrici Daniel","license":"MIT","stars":"6500+","created":"2026-06-29"}}
---


# Claude Ads：付费广告审计技能

Claude Ads 是专为 Claude Code 设计的综合付费广告审计与优化 Skill，由 [[AgriciDaniel\|AgriciDaniel]] 开发。一次完整的多平台广告审计从人工 4-6 小时缩短到 **10-15 分钟**，输出 0-100 加权评分和优先级行动方案。

## 核心能力

- **250+ 审计检查项**，覆盖 8 大广告平台
- **并行子代理**：`/ads audit` 同时派发 6 个子代理独立审计不同平台
- **Ads Health Score（0-100）**：加权评分算法，按严重程度分级（A/B/C/D/F）
- **行业模板**：11 种业务类型（SaaS、电商、本地服务、B2B 等）
- **创意管线**：品牌 DNA 提取 → 广告概念生成 → AI 图像生成 → 产品摄影
- **10 原则思考框架**：所有审计、计划、创意输出基于统一认知纪律
- **本地运行**：数据不离开本机，无需上传到第三方服务器

## 支持平台

| 平台 | 检查项 | 关键覆盖 |
|------|--------|----------|
| Google Ads | 80 | Search, PMax, AI Max, Display, YouTube, Demand Gen |
| Meta Ads | 50 | FB/IG/Threads, Advantage+, Andromeda + GEM + Lattice |
| LinkedIn Ads | 27 | B2B, Lead Gen, TLA, ABM |
| TikTok Ads | 28 | Creative-first, Smart+, GMV Max |
| Microsoft Ads | 24 | Google Import, Copilot, CTV |
| Apple Ads | 35+ | CPPs, Maximize Conversions, AdAttributionKit |
| Amazon Ads | 30+ | Sponsored Products/Brands/Display, ACOS/TACOS |
| 跨平台 | 3+ | 隐私基础设施, 创意多样性, 广告疲劳检测 |
| 归因+追踪 | 25+ | AdAttributionKit, GA4, Consent Mode V2, sGTM |

## 主要命令

| 命令 | 功能 |
|------|------|
| `/ads audit` | 全平台并行审计 |
| `/ads google` / `meta` / `linkedin` / `tiktok` / `microsoft` / `apple` / `amazon` / `youtube` | 单平台深度分析 |
| `/ads plan <type>` | 按行业类型制定广告策略（saas, ecommerce, local-service 等 11 种） |
| `/ads creative` | 跨平台创意质量审计 |
| `/ads budget` | 预算分配与出价策略审查 |
| `/ads math` | PPC 财务计算器（CPA, ROAS, 盈亏平衡, LTV:CAC） |
| `/ads test` | A/B 测试设计（假设框架、显著性、样本量） |
| `/ads report` | 生成 PDF 审计报告 |
| `/ads dna <url>` | 从网站提取品牌 DNA |
| `/ads create` / `generate` / `photoshoot` | 创意生成管线 |
| `/ads attribution` | 跨平台归因审计 |
| `/ads tracking` | 服务端追踪管道审计 |

## 质量门禁

硬性规则在每次审计中强制执行：
- 禁止在没有智能出价的情况下推荐广泛匹配（Google）
- **3x Kill Rule**：CPA > 目标 3 倍的广告组立即标记暂停
- 预算充足性：Meta ≥ 5x CPA/广告组，TikTok ≥ 50x CPA/广告组
- 学习期保护：活跃学习期内禁止编辑
- 合规自动检查：特殊广告类别（住房/信贷/金融）
- **隐私基础设施门禁**：推荐优化前验证追踪堆栈
- **Andromeda 创意多样性**：标记 Meta 账户中独特创意 < 10 个的情况

## 评估体系（Eval Harness）

v1.7.0 版本新增 **41 个 pytest 测试**，CI 在每次提交时运行：
- 路由快照：每个文档化的触发短语路由到预期子技能
- 检查目录覆盖：`check-catalog.yaml`（209 个 ID）双向校验
- 评分数学：加权评分算法的确定性验证
- SSRF 回归套件：27 个 IPv4/IPv6 阻止列表案例

## 与 Hermes 的关联

> 当前版本专为 **Claude Code** 设计，但也标注了 Codex CLI、Cursor、Windsurf、Gemini CLI、Goose 等实验性支持。其在 Hermes 上的可行性待验证。

核心架构模式与 Hermes 有共通之处：
- **子代理并行派发**：`/ads audit` 同时启动 6 个子代理，类似 Hermes 的 [[delegate_task\|delegate_task]] 并行任务
- **Skill 路由**：Orchestrator → Sub-skills 的分发模式，与 Hermes 的 Skill 体系类似
- **RAG 参考数据**：26 个内置参考文件按需加载
- **本地运行**：所有分析在本地完成，数据不离开本机

> **试验想法**：可尝试将 Claude Ads 的核心审计逻辑转为 Hermes Skill，保持相同的检查目录和评分体系，利用 Hermes 的多代理能力实现类似功能。

## 安装方式

### Claude Code（推荐）
```shell
/plugin marketplace add AI-Marketing-Hub/claude-ads
/plugin install claude-ads@ai-marketing-hub-claude-ads
```

### 一键安装（Unix/macOS/Linux）
```bash
curl -fsSL https://raw.githubusercontent.com/AI-Marketing-Hub/claude-ads/main/install.sh | bash
```

### 一键安装（Windows PowerShell）
```powershell
irm https://raw.githubusercontent.com/AI-Marketing-Hub/claude-ads/main/install.ps1 | iex
```

## 版本

- 当前版本：v1.7.1（Wave 2）
- 公开仓库：MIT 开源，无需会员
- 社区私有镜像：早期访问新功能，需 Pro 会员

## 相关资源

- 公开仓库：https://github.com/AgriciDaniel/claude-ads
- 主页：https://claude-ads.md
- 作者博客：https://agricidaniel.com/blog
- 相关项目：[[Claude SEO\|Claude SEO]]（同作者）

## 评分体系

| 等级 | 分数 | 含义 |
|------|------|------|
| A | 90-100 | 仅需微调优化 |
| B | 75-89 | 有改进机会 |
| C | 60-74 | 存在值得关注的问题 |
| D | 40-59 | 存在显著问题 |
| F | <40 | 需紧急干预 |
