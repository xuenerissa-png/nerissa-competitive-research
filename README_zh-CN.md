# nerissa-competitive-research

> **不要让 AI 一边凭印象一边产出竞品报告。** 一份纪律性的 Claude Skill · 拒绝偷懒 — 每个融资数字必须有 2 个数据源 · 每个"已签 N 家"必须能查 · 每个"X 公司跟我们类似"必须 6 维度打分才能接受。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)

---

## 问题

让 AI 调研一家竞品 · 你通常会得到下列之一的烂输出:

1. **融资数字来自一篇二手博客** — 而且博客是错的
2. **"他们是 AI X 创业 · 跟我们类似"** — 但没打开过他们的官网
3. **描述"他们做什么"** — 从来不问"本质是什么 · 封装层还是真技术?"
4. **建议"向他们学习"** — 基于 $400M ARR · 完全忽略他们的客户层跟你不重叠
5. **沿用老 DD 报告** — 从来不重核 · 老错误永久传播

这些都是我在为早期创业公司做竞调时真踩过的坑。12 家公司 + 多次修正之后 · 我把纪律抽象进这份 skill。

## 这份 Skill 不一样的地方

它拒绝偷懒。具体来说:

- **每个融资数字必须 ≥ 2 个独立数据源**(Crunchbase + 官方 PR · 或 LATKA + Rewardful 案例)
- **每个"X 签 Y 客户"必须查 source-of-truth 数据库** — 不靠记忆 · 不靠上周报告
- **每家必须做本质拆解**:技术 / 封装层 / 销售模式 / 品牌 / 网络效应 — 不只是"做什么"
- **每个推荐必须 6 维度打分** — 融资数字单独永远不够
- **双轨分离**:融资参照系(轨道 A · $10M+ 同方向)vs 业务学习对象(轨道 B · 看路径相似度 · 不看融资)。混了会出错。
- **沿用历史判断必须明确打标记** — "我没重审"比"看起来对"安全

## 快速开始

### 作为 Claude Code Skill 使用

1. 把这个 repo clone 到你的 Claude skills 目录:

```bash
mkdir -p ~/.claude/skills
cd ~/.claude/skills
git clone https://github.com/xuenerissa-png/nerissa-competitive-research.git
```

2. 在任何 Claude Code 会话中触发:
   - `调研 [公司名]`
   - `按这套竞调 SOP 加 [公司名] 到竞品表`
   - `research [Company Name] using competitive research skill`

3. Claude 会按 7 步 SOP 执行 · 做 6 维度打分 · 产出 15 字段结构化数据。

### 不用 Claude · 当成手工 SOP 用

`SKILL.md` 本身是一份完整可读的 SOP 文档。打印 · 手工跑一次调研 · 填齐 15 字段 · 进自己的跟踪库(Notion / Airtable / 飞书 Base 等)。

`references/feishu-base-schema.md` 提供了飞书 Base 一键建表脚本。

## 输出格式

每家调研完 · 你拿到:

```
🏢 公司: [名字]
🔗 官网: [已 verify 打开]
💰 融资: [≥ 2 数据源标注]
🧱 本质: [技术 / 封装层 / 销售 / 品牌 / 网络]
👥 客户重叠: [已查证 · 不是推断]
📊 6 维度得分: X / 12
🎯 一句话"抄什么": ...
📖 3 个必看页面: ...
🚫 触发的偷懒红线: ...
```

外加 15 字段结构化记录 · 直接入数据库。

## 7 步 SOP(摘要)

1. **打开官网**(30 秒)— verify 存在 · 不是只在某博客提过
2. **找融资数据**(5 分钟)— Crunchbase + 官方 PR + ≥ 2 数据源
3. **本质拆解**(10 分钟)— 5 个问题问出真本质
4. **客户重叠 verify**(10 分钟)— 案例 + Twitter / G2 真实评价
5. **6 维度打分**(5 分钟)— 8+ 才进 Top
6. **产出 3 段话**(15 分钟)— 是什么 / 抄什么 / 3 个必看页
7. **入结构化数据库**(5 分钟)— 15 字段 · 标 verify 数据源

总计:每家 30-60 分钟

## 案例

5 个真实案例(脱敏)在 `examples/`:

- **01 · LATKA 找到的 bootstrapped SaaS** — Cometly 案例。原 DD 写 "$500k 种子"。LATKA + Rewardful + 官方 About 三方交叉验证:**$0 融资 · 7 人 · 4 年 $770k ARR**。错的数字在内部传播了几周才被纠正。

- **02 · 融资浪潮里的封装层** — Lovable 案例。$400M ARR · $6.6B 估值。原判断:"AI 全栈生成器 · 必须学"。本质拆解后发现:**它本质 = v0(UI 生成)+ Supabase(后端)+ Cloudflare(部署)封装** · 没造任何新技术。这把结论从"必须学"改成了"它的护城河是规模/资本/品牌 · 我们学不来"。

- **03 · 中国直接对标** — 百型智能案例。36 氪报道 "哈啰前 COO 创业外贸 AI agent · 拿金沙江 Pre-A 数千万" — 立刻调研。多源 verify:创始人韩美的阿里 + 哈啰背景 / 拟人化 AI 员工 Zoe/David/Lisa / 真实客户案例数字。**比之前对标的 Sierra(F50 客户)更贴近我们的实际客户画像**。

- **04 · 巨头入局警示** — 阿里 Accio Work 案例。**不是直接竞品** · 但巨头免费 + 生态变现的入局 = 对付费 Concierge 模型是结构性威胁。标记为月度监控 · 不做深度调研。

- **05 · 双轨示例** — Sierra($1.5B 融资 · $15B 估值 · F50 客户)vs Cometly($0 融资 · 7 人 · $770k ARR)。两家都相关 · 但用途不同。Sierra 是轨道 A(融资参照系 · "我们是 Sierra outcome 模型的 vertical 版本")· Cometly 是轨道 B(业务学习 · "他们的 bootstrap 路径才是我们真能复制的")。**最初混了两者 · 误把 Cometly 从推荐清单里删了 — 直到双轨澄清才救回来**。

## 为什么会有这份 Skill

我是为一家早期成长阶段的创业公司做竞调时建的它。一周内反复抓到自己(和 Claude)犯同一类偷懒错:

- 沿用老 DD 的融资数字 · 不重核
- 把公司称为"竞品" · 但没打开过它的官网
- 推荐 Lovable 当学习目标 · 没意识到它本质是个封装层 · 我们学不来
- 在 5 份报告里说"我们签了 3 家 design partner" · 而 source-of-truth 数据库显示 0 已签
- 凭 1 个样本就锁定"制造业出海"作为 vertical · 实际上整个 pipeline 只有 40% 是制造业

每一次纠正都指向一条规则。这份 skill 把它们全部捕获。

## 跟其他做法比

| 做法 | 你得到 | 你失去 |
|---|---|---|
| **一次性 AI 查询**("调研 X 公司") | 快速叙事 | 经常继承单源错数据 · 没 verify |
| **通用竞品模板**(Notion / Airtable) | 结构 | 没纪律防偷懒填 · 没本质拆解 |
| **VC pitch deck 竞品 slide** | 一眼可视 | 倾向比有利于你的维度 · 不诚实 |
| **nerissa-competitive-research** | 上述全部 + 强制 verify + 双轨 + 本质拆解 + 反偷懒清单 | 单家时间多 30-60 分钟 |

如果你一年调研 < 3 家 · 可能不需要这个。如果 10+ · 纪律的回报很快。

## 路线图

- [x] v1.0 · 核心 SOP + 6 维度打分 + 15 字段 schema + 5 个案例
- [ ] v1.1 · 加 Notion / Airtable schema 模板(目前只有飞书 Base)
- [ ] v1.2 · 加自动化 Crunchbase + LATKA + G2 多源抓取(等可靠 scraper 出现时)
- [ ] v1.3 · 加竞品监控 agent(每日 diff 监测融资 / 价格 / 客户墙变化)

## 相关 Skills

- [decision-lens](https://github.com/xuenerissa-png/decision-lens) — 多角色决策评审(当"X 公司算不算我们竞品"本身是个复杂决策时用)

## License

MIT · 自由使用 / fork / 改编

## 作者

由 [@xuenerissa-png](https://github.com/xuenerissa-png) 打造。如果你觉得有用 · 或想贡献一条新的"失败模式 → 规则" · 欢迎提 issue。

---

English README: [README.md](README.md)
