# Evidence Level Pre-Publish Checklist

> Run through this checklist before publishing any competitive research report.
> All boxes must be ✅ or report goes back to revision.

## Section A · Tagging Discipline

- [ ] Every "X is / X did / X has" assertion has an `[L1A/L1B/L2/L3/L4/L5]` tag
- [ ] No untagged hard chronological / numeric claims
- [ ] All inference / prediction / "I guess" statements have **explicit L5 ⚠️** prefix
- [ ] All "X will happen in N months" predictions rewritten as 💭 hypothetical scenarios

## Section B · Source Discipline

- [ ] All L1B funding claims cite **≥ 3 independent sources**
- [ ] All L2 customer-overlap claims cite **≥ 2 independent sources** (official + 1 other)
- [ ] No single secondary blog used as sole evidence for any L3+ claim
- [ ] All cited URLs are loaded and verified (not pasted from memory)
- [ ] Aggregator blogs are tagged L4 / L5 explicitly, not promoted to L3

## Section C · Scoring Discipline

- [ ] The 6-dimension scoring table includes an `evidence_level` column for each dimension
- [ ] Both `nominal_score` and `discounted_score` are reported
- [ ] Discounted score formula: each L5-backed dimension contributes 0
- [ ] If discounted score < 8/12, conclusion explicitly notes "below Top threshold under conservative evidence weighting"

## Section D · Quarantine Discipline

- [ ] Section "💭 Inference / Hypothetical Scenarios" exists and is clearly separated from factual sections
- [ ] All L5 inferences live in that section, not mixed into the main report
- [ ] Inference section is labeled with ⚠️ banner: "Below content is reasoning, not evidence"

## Section E · Strategic Claim Discipline

- [ ] No strategic recommendation ("we should X / we should not X") is based solely on L4-L5 evidence
- [ ] Each strategic recommendation cites at least 1 L1B or L2 supporting evidence
- [ ] "X is our primary competitor" / "X is in Track A" decisions reference the relevant rule from `evidence-level-pyramid.md`

## Section F · Anti-Flattery Discipline

- [ ] The "Anti-Flattery Red Flags" section explicitly calls out
      which scoring dimensions are inflated by L4-L5 evidence
- [ ] The section names the verification action needed to upgrade each L5 to L2+
      (e.g. "L5 ⚠️: founder claim of monthly ¥1M revenue → upgrade by Book a Demo + estimate from pricing tier")

## Section G · Track Discipline

- [ ] Track A (fundraising reference) judgments cite L1B+ funding data
- [ ] Track B (business learning) judgments cite L2+ product / customer data
- [ ] Track A and Track B are clearly separated, not mixed

## Section H · "Pending Verification" Discipline

- [ ] Report includes a "📋 Pending Verification" section at the end
- [ ] Section lists every L5 ⚠️ claim with:
      - The claim itself
      - Why it's L5 (e.g. "founder self-report")
      - Concrete action to upgrade evidence (e.g. "申请 Demo · 录屏 · 看真实客户案例")
      - Estimated time to upgrade (e.g. "2 weeks for Demo approval")

## Section I · Self-Audit Loop

After publishing:
- [ ] Add a line to the changelog file documenting which L5 claims this report
      pushed into the report and what verification is planned next quarter
- [ ] Schedule quarterly re-audit for all L4-L5 claims
- [ ] If any cited L1B/L2 source is found to be wrong → file as a learning case

## Section J · Final Sanity Check

- [ ] If I removed all L5 ⚠️ content from this report, would the conclusion still hold?
- [ ] If yes → report is robust
- [ ] If no → mark report as **"draft pending L5 → L2+ upgrade"** and do NOT share with team / investors yet

## Quick Reference Card (print this and tape on monitor)

```
┌─────────────────────────────────────────────────────────────┐
│  Evidence Level Floor for Strategic Claims                  │
│                                                              │
│  - "Primary competitor"          ≥ L2                       │
│  - "Track A fundraising ref"     ≥ L1B (≥ 3 sources)       │
│  - "Track B business learning"   ≥ L2                       │
│  - "X will happen in N months"   FORBIDDEN → rewrite        │
│  - "We differentiate by X"       ≥ 1 L2+ supporting source  │
│                                                              │
│  All L5 ⚠️ → quarantine to 💭 Inference Section              │
└─────────────────────────────────────────────────────────────┘
```

**Adopted: 2026-06-07.**
