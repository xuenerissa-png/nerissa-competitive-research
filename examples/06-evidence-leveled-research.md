# Example 06 · Evidence-Leveled Research with Discount Scoring

> A sanitized real case (2026-06-06) where Claude researched a China domestic competitor and the original report mixed L5 founder self-reports with L1B verified data — leading to inflated scoring and fragile strategic conclusions. This example shows the before/after when the evidence-leveling discipline is applied.

## Context

OPC (a 0-customer AI SaaS for Chinese outbound teams) asked: "我们做出来这个产品之后,国内竞品是什么?"

Claude researched 12 candidates and produced a Top-5 list. The strongest competitor — let's call it CompetitorX — scored **11/12** on the 6-dimension scoring. nerissa pushed back: "你这个评分凭什么这么高?"

## What Went Wrong (Original Report)

The original 6-dimension scoring looked clean:

| Dimension | Score |
|---|:---:|
| Customer overlap | 2 |
| Business model | 2 |
| Team scale | 1 |
| Recent activity | 2 |
| Real cash flow | 2 |
| Pipeline relevance | 2 |
| **Total** | **11/12** 🔥 |

Then "11/12" became a strategic claim: "CompetitorX is our primary direct competitor and **5x ahead of us in revenue**."

**The hidden problem**: 3 of the 6 dimensions were backed by L5 evidence.

## What Evidence-Leveling Revealed

Re-running the scoring with mandatory `evidence_level` column:

| Dimension | Score | Evidence Level | Source |
|---|:---:|:---:|---|
| Customer overlap | 2 | **L2** | Official site + case study |
| Business model | 2 | **L4** ⚠️ | Tencent News interview only |
| Team scale | 1 | **L4** ⚠️ | Founder self-report in interview |
| Recent activity | 2 | **L3** | Single news article |
| Real cash flow | 2 | **L5** ⚠️ | "月入百万" founder self-report — un-verified |
| Pipeline relevance | 2 | **L2** | Official product page |

**Reality check**:
- Of the 11 nominal points, **6 points** are backed by L3-L5 evidence
- The "5x ahead in revenue" claim is built **entirely on a single L5 founder interview** with no third-party financial verification

## Discounted Score Calculation

Rule: Each L5-backed dimension contributes 0 in the discounted score.

| Dimension | Nominal | Discounted |
|---|:---:|:---:|
| Customer overlap (L2) | 2 | 2 |
| Business model (L4 ⚠️) | 2 | 2 (L4 still counts but flagged) |
| Team scale (L4 ⚠️) | 1 | 1 |
| Recent activity (L3) | 2 | 2 |
| Real cash flow (L5 ⚠️) | 2 | **0** |
| Pipeline relevance (L2) | 2 | 2 |
| **Total** | **11/12** | **9/12** |

**9/12 still qualifies as Top**, but the dropoff from "11/12 super star" to "9/12 high but not top-1" changes the strategic framing significantly.

## What the Strategic Conclusion Becomes

### Before (fragile)

> "CompetitorX is our most dangerous direct competitor. They're already 5x ahead of us in revenue. We need to differentiate immediately on X, Y, Z."

### After (robust)

> "CompetitorX scores **9/12 discounted** (11/12 nominal · 2 points from L5 ⚠️ un-verified founder revenue claim). They are a strong Top competitor but the '5x revenue lead' is an L5 inference that we should not act on until verified.
>
> **Pending verification**:
> - Apply for CompetitorX product demo via nerissa's LinkedIn → see actual customer count + pricing tier
> - Search G2 / Capterra for real user counts → upgrade from L4 to L3
> - Subscribe to vertical newsletters that may report verified ARR → upgrade L5 → L2
>
> **Strategy**: We treat CompetitorX as a Top competitor in product positioning, but we do NOT use the '5x ahead' framing in any internal or external deck until we have ≥ L2 evidence."

## The Inference Section That Was Added

A new "💭 Inference Section ⚠️" was added to the bottom of the report:

> **💭 Inference Section · L5 ⚠️**
>
> Below content is reasoning, not evidence. Not to be cited in strategic decisions.
>
> 1. **CompetitorX ARR**: Estimated $10-15M based on "月入百万" self-report × 12 months. Real number un-verified.
> 2. **CompetitorX team size**: Estimated 50+ based on founder interview mention. LinkedIn page shows 23, suggesting "50+" may include contractors.
> 3. **CompetitorX customer count**: Not disclosed anywhere. Inferred from "rapid growth" framing in interview.

## What This Catches

| Anti-pattern caught | What it prevented |
|---|---|
| Treating L5 founder self-report as L1B verified data | Inflating "11/12" score → fragile strategy claim |
| Mixing inference with fact in main report | Reader can't tell which claims to trust |
| Using "5x ahead" framing un-flagged | Team starts strategizing against a number that might be wrong |
| Strategic conclusion built on L5 | Whole strategy collapses if founder over-reported |

## What This Costs

- **Time**: Extra 5-10 minutes per company for evidence tagging
- **Friction**: Some "exciting" findings get demoted to "💭 inference section"
- **Discipline**: Required to surface "I don't actually know this for sure" moments

## What This Gains

- **Robustness**: Strategic conclusions survive when L5 claims turn out to be wrong
- **Trust**: Team/investors see the evidence hygiene → trust amplifies
- **Self-correction**: Next research cycle has a clear list of L5 → L2+ upgrade tasks
- **Anti-flattery**: The discount column is impossible to hand-wave away — it's a number

## Provenance

This example was added 2026-06-07 after a real incident where Claude treated multiple L5 self-reports as if they were L1B verified data, leading nerissa to push back and forcing the entire evidence-leveling system into the skill.
