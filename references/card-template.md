# 卡片笔记模板

遵循 Obsidian Flavored Markdown 规范。Obsidian 专属语法（wikilinks / callouts / embeds / properties）详见 `obsidian-markdown` skill。

## YAML frontmatter

```yaml
---
tags:
  - product/prd        # 支持嵌套标签
title: 原文标题
source: https://mp.weixin.qq.com/s/xxxx
source_account: 公众号名称   # 微信文章来源账号名，从 byline 第二截提取；删 byline 行前先写入，避免丢失
author: "[[作者姓名]]"   # wikilink，串联 vault 内作者笔记
published_at: 2026-07-03T12:10:00+08:00   # Obsidian 日期与时间属性
description: 一句话描述
aliases:                 # 可选：别名，提升链接/检索友好度
  - 标题别名
---
```

说明：

- `tags`：YAML 块列表（非内联数组）；支持嵌套标签 `product/prd`
- `source_account`：公众号名称（微信文章来源账号名），来自 byline 行第二截；建卡时先提取再删 byline 行
- `author`：用 `[[作者]]` wikilink 指向 vault 内作者笔记
- `published_at`：Obsidian「日期与时间」属性，ISO 8601
- `aliases`：可选，作者 / 文章别名
- 抓取不到的字段（author / location 等）可省略

## 正文结构（按顺序，锚点保持）

```markdown
# 核心观点

- 要点1：简明扼要
- 要点2：简明扼要
- 要点3：简明扼要

# 详细内容

按逻辑分段，每个段落用 1-3 句话概括。
vault 内其他卡片用 [[另一张卡片]] 互链，==关键词== 可高亮。

# 我的思考

我看完之后的感悟或吐槽，一段一义，不超过三句话。没有自己的思考，记再多也没用。
> [!tip] 关键洞察
> 可用 callout 强调最重要的那一条思考。

---

# 原文内容

原样保存文章全文，保持原文格式（小标题、分割线、图片链接、表格等）。
- 本地图片：`![[image.png]]`
- 外链图片：`![alt](https://...)`
不要给原文每行加 `>` 前缀，不要添加公众号 / 作者 / 时间摘要行，不要添加说明行，不要用 callout 包裹。
```

## 要点

- 四个一级标题锚点 `# 核心观点` / `# 详细内容` / `# 我的思考` / `# 原文内容` 必须保留，便于文章分析模式按标题解析。
- `# 我的思考` 与 `# 原文内容` 之间必须加一条 `---` 分割线，作为两个区块的视觉与解析分隔（默认加上，不要省略）。
- `# 原文内容` 原样保存全文，不改写、不加 `>` 前缀、不加摘要行、不用 callout 包裹。
- 内部引用用 `[[wikilink]]`，外部链接用标准 Markdown 链接。
- 标签反映内容实质，避免宽泛词（如「文章」「笔记」）；支持嵌套标签。
- 「我的思考」是有个人视角的独立评论，不是总结。
