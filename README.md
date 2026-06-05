# nerissa-competitive-research

> **Stop letting AI hallucinate competitor reports.** A disciplined Claude Skill that refuses lazy shortcuts — every funding number must have 2 sources, every "they signed N customers" must be queryable, every "company X is similar to us" must be scored on 6 dimensions before being accepted.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)

---

## The Problem

When you ask AI to research a competitor, you usually get one of these bad outputs:

1. **Funding numbers pulled from one secondhand blog** — and the blog was wrong
2. **"They're an AI X startup like us"** — without ever opening their website
3. **A description of "what they do"** — never asking "what is the essence, packaging-layer or real tech?"
4. **A recommendation to "learn from them"** — based on $400M ARR, ignoring that their customer layer doesn't match yours at all
5. **Inherited from an old DD report** — never re-validated, so old errors propagate forever

Each of these is a real failure pattern I hit while doing competitive research for an early-stage startup. After 12 companies and many corrections, I extracted the discipline into this skill.

## What This Skill Does Differently

It refuses the shortcuts. Specifically:

- **Every funding claim requires ≥ 2 independent sources** (Crunchbase + official PR; or LATKA + Rewardful case study)
- **Every "X signed Y customers" requires querying your source-of-truth database** — not memory, not last week's report
- **Every company gets decomposed**: technology / packaging-layer / sales motion / brand / network effect — not just "what it does"
- **Every recommendation requires 6-dimension scoring** — funding size alone never qualifies
- **Dual-track separation**: fundraising-reference (Track A · $10M+ similar direction) vs business-learning-target (Track B · path similarity, ignore funding). Mixing them causes errors.
- **Inherited historical judgments must be explicitly tagged** — "I didn't re-validate" is safer than "looks fine"

## Quick Start

### Use as a Claude Code Skill

1. Clone this repo into your Claude skills directory:

```bash
mkdir -p ~/.claude/skills
cd ~/.claude/skills
git clone https://github.com/xuenerissa-png/nerissa-competitive-research.git
```

2. In any Claude Code session, trigger by saying:
   - `"research [Company Name] using the competitive research skill"`
   - `"调研 [公司名]"` (Chinese)
   - `"add [Company Name] to the competitor table — full SOP"`

3. Claude will execute the 7-step SOP, score on 6 dimensions, and produce the 15-field structured output.

### Use without Claude (as a manual SOP)

The `SKILL.md` is also a fully readable SOP document. Print it, run a research session manually, fill the 15 fields, and add to your own tracking database (Notion / Airtable / Feishu Base / etc).

A ready-to-use Feishu Base schema script is in `references/feishu-base-schema.md`.

## Output Format

For each company researched, you get:

```
🏢 Company: [Name]
🔗 Website: [verified open]
💰 Funding: [≥ 2 sources cited]
🧱 Essence: [technology / packaging-layer / sales / brand / network]
👥 Customer overlap with you: [verified, not inferred]
📊 6-dimension score: X / 12
🎯 One-line "what to copy": ...
📖 3 must-see pages: ...
🚫 Anti-lazy flags caught: ...
```

Plus the 15-field structured record ready to drop into a database.

## The 7 Steps (Summary)

1. **Open the official website** (30s) — verify it exists, not just an aggregator blog mention
2. **Find funding data** (5min) — Crunchbase + official PR + ≥ 2 sources
3. **Decompose essence** (10min) — 5 questions about what it really is
4. **Verify customer overlap** (10min) — case studies + Twitter / G2 reviews
5. **Score on 6 dimensions** (5min) — only 8+ qualifies for Top
6. **Produce 3 sentences** (15min) — what it is / what to copy / 3 must-see pages
7. **Enter structured database** (5min) — 15 fields, verifiable sources

Total: 30-60 minutes per company

## Examples

5 worked examples in `examples/` (sanitized from real research):

- **01 · Bootstrapped SaaS via LATKA** — Cometly case. Original DD said "$500k seed." LATKA + Rewardful + official About cross-verified: $0 funding, fully bootstrapped, $770k ARR with 7 people. The wrong number propagated for weeks before correction.

- **02 · Funding wave packaging layer** — Lovable case. $400M ARR, $6.6B valuation. Original take: "AI full-stack builder." Essence decomposition revealed: it's v0 (UI gen) + Supabase (backend) + Cloudflare (deploy) packaged with a conversational interface. No new technology. This changed the conclusion from "must learn from" to "they have wide moat (scale/capital/brand) but technically anyone can copy."

- **03 · China direct competitor** — Baixing Intelligence case. Found via 36Kr report mentioning ex-Hello COO founding an overseas trade AI agent startup. Multi-source verified: founder background, Jinsha Jiang Pre-A funding, named AI employees (Zoe / David / Lisa). Closer mirror to our customer profile than the Sierra-class US giants we had been benchmarking against.

- **04 · Incumbent warning** — Alibaba Accio Work case. Not a direct competitor. But entry of a giant with free + ecosystem monetization is a structural threat to a paid Concierge model. Flagged for monthly monitoring, not deep research.

- **05 · Dual-track example** — Sierra ($1.5B funding, $15B valuation, F50 customers) vs Cometly ($0 funding, 7 people, $770k ARR). Both relevant — but for different uses. Sierra is Track A (fundraising-reference, "we're a vertical version of Sierra's outcome model"). Cometly is Track B (business-learning, "their bootstrap path is what we can actually replicate"). Confusing the two killed Cometly from the recommendation list initially.

## Why This Exists

I built this skill while doing real competitive research for an early-stage growth startup. Over a week of research, I caught myself (and Claude) making the same lazy mistakes repeatedly:

- Re-quoting funding numbers from old DD reports without re-checking
- Calling companies "competitors" without opening their website
- Recommending Lovable as a learning target without realizing it's a packaging-layer with a moat we can't access
- Saying "we signed 3 design partners" in 5 reports when the source-of-truth database showed 0 signed
- Defaulting to "manufacturing exports" as our vertical based on 1 sample company, when actually only 40% of our pipeline was manufacturing

Each correction pointed to a rule. This skill captures all of them.

## Comparison to Other Approaches

| Approach | What it gives you | What it misses |
|---|---|---|
| **One-shot AI query** ("research X company") | Quick narrative | Often inherits wrong data from one source; no verification |
| **Generic competitor template** (Notion / Airtable) | Structure | No discipline against lazy filling; no essence decomposition |
| **VC pitch deck competitor slide** | Visual at-a-glance | Tends to compare on dimensions that flatter you; not honest |
| **nerissa-competitive-research** | All of the above + forced verification + dual-track + essence decomposition + anti-lazy checklist | More work upfront (30-60 min per company) |

If you do < 3 competitor researches a year, you probably don't need this. If you do 10+, the discipline pays back fast.

## Roadmap

- [x] v1.0 · Core SOP + 6-dimension scoring + 15-field schema + 5 examples
- [ ] v1.1 · Add Notion / Airtable schema templates (currently only Feishu Base)
- [ ] v1.2 · Add automated Crunchbase + LATKA + G2 multi-source fetcher (when reliable scrapers available)
- [ ] v1.3 · Add competitor monitoring agent (daily diff watcher for funding / pricing / customer wall changes)

## Related Skills

- [decision-lens](https://github.com/xuenerissa-png/decision-lens) — Multi-role decision review (when "should we treat X as competitor?" itself is a complex decision)

## License

MIT · Free to use, fork, adapt.

## Author

Built by [@xuenerissa-png](https://github.com/xuenerissa-png). If you find this useful or want to contribute a new failure pattern → rule, file an issue.

---

中文版 README: [README_zh-CN.md](README_zh-CN.md)
