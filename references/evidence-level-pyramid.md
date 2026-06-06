# Evidence Level Pyramid for Competitor Research

> Adapted from evidence-based medicine (EBM) Levels of Evidence (Oxford CEBM).
> Every claim in a competitor research report must be tagged with one of these 5 levels.

## The 5-Level Pyramid

```
Level 1A: Audited financial records           ← STRONGEST
          (Annual report / 10-K / S-1 / IPO prospectus)
          + ≥ 2 independent sources

Level 1B: Tier-1 financial press
          (Crunchbase + TechCrunch + Bloomberg)
          + ≥ 3 independent sources required for funding claims

Level 2:  Company first-party
          (Official website + company PR + LinkedIn company page)
          + ≥ 2 independent sources

Level 3:  Third-party user verification
          (G2 / Capterra / ProductHunt real reviews,
           industry verticals 36Kr / Lei.com deep coverage)
          + single trusted source acceptable but flag

Level 4:  Secondary aggregators / VC framings
          (Aggregator blogs / VC investment thesis / 
           founder interviews on biz media)
          + use carefully; cross-reference Level 2-3

Level 5:  Self-report / inference / prediction         ← WEAKEST
          (Founder self-report "$10M ARR";
           media quoting founder PR un-verified;
           Claude's own inference or prediction)
          + MUST tag ⚠️ and quarantine to "inference section"
```

## Why This Matters

| Without leveling | With leveling |
|---|---|
| "iSales monthly revenue ¥1M" treated same as Crunchbase funding | "iSales monthly revenue ¥1M [L5 founder self-report ⚠️]" — reader instantly knows credibility |
| Strategy conclusion derived from L5 → fragile | Strategy conclusion requires ≥ L2 sources → robust |
| Team can't tell which claims to push back on | Team sees ⚠️ flags → asks for verification |
| Investor reads report and trusts everything equally | Investor sees evidence hygiene → trust amplifies |

## Hard Rules

### Rule 1 · Every claim must be tagged

Format:
> "Nectar raised $40.6M cumulative **[L1B · 3 sources: TechCrunch + Menlo + Yahoo]**"
> "iSales monthly revenue ¥1M+ **[L5 · founder self-report on Tencent News ⚠️]**"

No untagged hard assertions allowed.

### Rule 2 · Strategy floor — minimum evidence levels for conclusions

| Conclusion Type | Minimum Evidence Level |
|---|---|
| Primary competitor selection | ≥ L2 |
| Track A (fundraising reference) qualification | ≥ L1B (funding ≥ 3 sources) |
| Track B (business learning) qualification | ≥ L2 |
| Prediction / warning ("X will eat 50% of market in 24 months") | **FORBIDDEN** → rewrite as "hypothetical scenario" |
| Differentiation argument | At least 1 supporting claim at L2+ |

### Rule 3 · L5 evidence is not deleted, but quarantined

- L5 evidence has information value → don't delete it
- Quarantine into a separate ⚠️ block / 💭 inference section
- Strategy conclusions citing L5 must prefix: "IF X's self-report holds, THEN ..."

### Rule 4 · Single-source = L3 or below

- 1 news article alone = L3 (could be paid placement)
- 1 VC blog post = L4
- 1 aggregator blog = L4 or L5 (depends on quality)
- **Any L1B conclusion requires ≥ 3 independent sources**

### Rule 5 · "Inference / prediction / I guess" mandatory L5

- "I estimate ARR $5-20M" = L5 inference
- "Within 24 months Accio will enter B2B" = L5 prediction
- "Team vibe is warm" = L5 subjective judgment
- All L5 inferences quarantined to **"💭 Inference section"** not mixed with facts

### Rule 6 · Phrasing matches evidence strength

| Evidence Level | Permitted phrasing |
|---|---|
| L1A | "X's real ARR is $Y" |
| L1B | "Per [TechCrunch + Bloomberg + Crunchbase], X raised $Y" |
| L2 | "Per official site + company PR, X serves Y customers" |
| L3 | "Per [media name] single-source report, X is X-certified, **pending ≥ 2 source cross-check**" |
| L4 | "Per [VC blog], X's founder believes ..." |
| L5 | "X self-reports ¥Y revenue ⚠️ **un-verified by third party**" |

## The 6-Dimension Scoring Table with Evidence Levels

Old format (broken):
```
| 维度 | 评分 |
|---|---|
| 客户重叠 | 2 |
```

New format (correct):
```
| 维度 | 评分 | 证据级别 | 评分依据 |
|---|:---:|:---:|---|
| 客户重叠 | 2 | L2 | 官网 logo wall + 案例研究 |
| 现金流 | 2 | L5 ⚠️ | 创始人腾讯访谈自报 · 未 verify |
```

Effect: A "11/12" total looks great until reader sees "cash flow 2/2 is L5" → instantly knows that 2 points is unreliable → discount to "real effective score = 9/12".

## The Discount Calculator

For each L5 ⚠️ scoring item, compute two scores:
- **Nominal score**: total as scored
- **Discounted score**: L5 items scored 0

Example:
```
iSales nominal:    11/12
iSales discounted: 9/12 (subtract 2 points for L5 cash flow)
→ Real comparable score 9/12 → still Top, but not "11/12 super star"
```

## Mandatory Pre-Publish Checklist

Before any report is shared:

- [ ] Every "X happened / X is true" claim has an evidence-level tag
- [ ] All L1B funding claims have ≥ 3 independent sources cited
- [ ] All L5 inferences are quarantined to 💭 inference section
- [ ] All scoring tables include an `evidence_level` column
- [ ] All "X will happen in 24 months" predictions are rewritten as "hypothetical scenario"
- [ ] All "I estimate" inferences are explicitly tagged L5 ⚠️
- [ ] Anti-flattery section calls out which scores are inflated by L5 evidence

## Source Strength Hierarchy (within levels)

Not all sources are equal even within a level:

| Source Type | Trust | Level |
|---|---|---|
| SEC EDGAR / IPO prospectus | ★★★★★ | L1A |
| Crunchbase (founder-edited) | ★★★ | L1B (need cross-check) |
| TechCrunch | ★★★★ | L1B |
| Bloomberg | ★★★★ | L1B |
| Reuters | ★★★★ | L1B |
| 36Kr | ★★★ | L3 (verticals) or L1B (funding) |
| Tencent News (founder interview) | ★★ | L4 (founder-mediated) |
| 雷锋网 | ★★ | L3 |
| Sina Tech / Sohu / 163 | ★ | L3-L4 (often syndicated) |
| Random WeChat blog | ★ | L4-L5 |
| AI tool导航 | ☆ | L5 (often paid/auto-scraped) |

## When to Up-grade Evidence Level

You can ONLY upgrade level by adding more sources:

- L5 → L4: 1 additional independent reputable source
- L4 → L3: 1 additional first-party or vertical-media source
- L3 → L2: Add official website / company PR confirmation
- L2 → L1B: For funding only, add 3rd independent tier-1 financial source
- L1B → L1A: Audited / SEC-filed document obtained

## When to DOWN-grade Evidence Level

- A source publishes a correction or retraction
- 2 sources turn out to be the same syndication chain
- Original source is identified as paid placement (软文)
- Founder later disputes the figure in a more recent interview

## Anti-Pattern Examples

❌ "iSales has 50+ team members (likely)"
✅ "iSales team size [L4 · founder mention in Tencent News interview; LinkedIn page lists 23 employees, suggesting 50+ may include contractors]"

❌ "Nectar processes 10M conversations/week, ARR $5-20M"
✅ "Nectar processes 10M conversations/week [L2 · official PR cited by TechCrunch + Menlo]. ARR is **L5 inference ⚠️** based on industry conversation pricing benchmarks of $0.5-1 per conversation × 10M × 4 weeks; actual ARR not disclosed."

❌ "Accio Work will eat 50% of OPC's market in 24 months"
✅ "💭 **Hypothetical Scenario (L5)**: IF Accio adds B2B inquiry attribution AND retains its zero-CAC bundling advantage, THEN OPC's DTC-segment win rate could compress significantly. This is a stress-test scenario, not a prediction."

## Provenance Note

This evidence-leveling system was added to the skill after Claude (the AI agent) was caught mixing L5 founder self-reports (e.g. "iSales monthly revenue ¥1M") with L1B verified funding data in strategy conclusions. nerissa flagged that all strategic decisions built on un-verified self-reports would propagate errors downstream. The 5-level pyramid was directly transplanted from evidence-based medicine (Oxford CEBM), where the same problem (treating expert opinion same as RCT) plagued clinical decision-making for decades.

**Adopted: 2026-06-07.**
