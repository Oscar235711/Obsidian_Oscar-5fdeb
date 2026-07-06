---
{"dg-publish":true,"permalink":"/项目档案/sealight-Facebook拉新广告配置/","title":"Facebook 拉新广告配置","tags":["Meta广告","Facebook广告","拉新","广告配置","campaign类型"],"dg-note-properties":{"title":"Facebook 拉新广告配置","type":"entity","domain":"sealight","parent":[["sealight-品牌概览"]],"tags":["Meta广告","Facebook广告","拉新","广告配置","campaign类型"],"created":"2026-07-03"}}
---


# Facebook 拉新广告配置

Sealight（SuncentAuto）在 Facebook/Instagram 投放拉新广告时的系列配置规范与类型映射。

## 拉新系列基础配置

| 配置项 | 值 |
|--------|-----|
| 广告目标 | **销量（Sales）** |
| 购买方式 | 竞拍（Auction） |
| 系列结构 | **1-1-5**（1系列-1广告组-5个广告素材） |
| 素材比例 | 2图片 + 3视频 |
| 日预算 | $20/系列（学习期偏紧，建议合并用 CBO 或先集中跑购买） |
| 版位 | Advantage+ Placements |

### 为什么目标选「销量」而不是「流量」

电商拉新不需要换目标。Meta 的转化事件（购买 vs 加车）是在**广告组层级**区分的，不是在「广告目标」层级：

```
系列 1：目标 → 销量 → 广告组转化事件选「Purchase（购买）」
系列 2：目标 → 销量 → 广告组转化事件选「Add to Cart（加入购物车）」
```

排除的目标：知名度（品牌曝光）、流量（不优化转化）、互动（帖子互动）、潜在客户（线索表单）、应用推广（不适用网站）。

## Campaign 类型映射

| 类型代码 | 含义 | 适用场景 |
|----------|------|---------|
| `cpc_conv` | 转化量 | **手动素材拉新（购买/加车）** ← 首选 |
| `cpc_dpa` | 目录动态广告 | 访客召回（看过某商品的用户） |
| `cpc_daba` | 广泛受众动态广告 | 目录驱动拉新（没来过网站的新用户） |
| `cpc_cocr` | 精品栏广告（Collection Creative） | 目录Feed驱动的精品栏格式 |
| `cpc_cocr_feed` | 精品栏 + Feed分裂 | 精品栏基础上加车型Feed动态匹配 |
| `cpc_asc` / `cpc_asc_feed` | Advantage+ 购物广告 | 目录驱动，AI自动优化 |
| `cpc_traffic` | 流量目标 | 引导点击，不优化转化 |
| `cpc_engagement` | 互动目标 | 帖子互动/主页赞 |
| `cpc_pl` | 潜在客户 | 线索表单场景 |
| `cpc_aware` / `cpc_reach` / `cpc_watch` | 知名度/覆盖 | 品牌曝光 |
| `cpc_tl` | 投流（通用） | 太泛，看不出目标 |

### 两条拉新线的互补关系

| 维度 | `cpc_conv`（手动素材） | `cpc_cocr_feed`（精品栏+Feed） |
|------|------------------------|-------------------------------|
| 广告格式 | 图片 + 视频 | 精品栏（Collection） |
| 商品驱动 | 手动选择素材 | 目录 Feed 驱动 |
| 标题 | 固定标题 | Feed分裂 → 车型动态匹配 |
| 定位 | 覆盖面广，跑量 | 精准匹配有车用户，转化率高 |

命名建议：`[cpc_conv] 拉新-购买 | img+vid | 1-1-5`

## Feed 分裂（Feed Splitting）

### 原理

将车型信息（Year/Make/Model）动态插入产品标题，实现广告精准匹配用户搜索。

**例子**：
- 产品：Sealight S7S 9005 160W Headlight Bulbs 2PCS
- 适配：2015 Ford F150、2004 Honda Accord 等上千款车型
- Feed分裂后：用户搜索 "2015 Ford F150 headlight" → 广告显示 "[2015-2018 Ford F150] + 原产品标题"

### 关键字段

Year → Make → Model → Submodel → Position → Trim（与产品适配数据库对应）

### 当前不足

商品版位内容不够丰富：缺少评论、运输时效、打折信息、发货地等。

## Google Ads 自定义报告

带「品类」「补充细分」「广告类型」等业务维度字段的报告，不是 Google Ads 后台默认预置。

**查找路径**：
```
报告 → 报告 → 已保存的报告
```

业务字段来源（两种方式之一）：
- **自定义标签**：工具与设置 → 自定义标签 → 广告系列标签
- **命名规范提取**：系列名称中编码后导出用 Excel 分列/正则提取

## 相关笔记

- [[项目档案/sealight-S7S广告素材提示词\|sealight-S7S广告素材提示词]]
- [[项目档案/sealight-S1Pro独立日出行周方案\|sealight-S1Pro独立日出行周方案]]
- [[项目档案/sealight-品牌概览\|sealight-品牌概览]]
