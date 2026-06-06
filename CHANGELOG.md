# Changelog

All notable changes to this skill.

## [1.1.0] - 2026-06-07

### Added · Evidence-Based Discipline ⭐ (Major Update)

After a real incident where Claude treated L5 founder self-reports as L1B verified data and built fragile strategic conclusions ("CompetitorX is 5x ahead of us"), the entire evidence-leveling discipline was added to the skill.

- **Principle 9** added to Core Principles: tag every claim with Evidence Level (L1A-L5); never mix L5 self-reports with L1B verified data
- **Step 4.5** added to SOP: classify every piece of collected evidence into 1 of 5 levels (L1A audited financials / L1B tier-1 financial press / L2 official first-party / L3 vertical media / L4 secondary aggregators / L5 self-report/inference)
- **Step 5** revised: 6-dimension scoring table now mandatory `evidence_level` column + both `nominal_score` and `discounted_score` (L5-backed dimensions contribute 0 in discounted)
- **Step 7** revised: Feishu Base schema adds 6 new fields (evidence_level_overall, funding_evidence_level, customer_evidence_level, arr_evidence_level, last_evidence_review, pending_verification)
- **Step 8** added: mandatory pre-publish checklist execution before sharing report
- SOP renamed from "7-Step" to "8-Step"

### Added · New Reference Documents

- `references/evidence-level-pyramid.md` — full 5-level pyramid adapted from EBM Oxford CEBM with hard rules, anti-patterns, source strength hierarchy, upgrade/downgrade triggers
- `references/evidence-level-checklist.md` — 10-section pre-publish discipline checklist; all boxes ✅ before report shares

### Added · New Example

- `examples/06-evidence-leveled-research.md` — sanitized real case showing how a "11/12" nominal score discounted to "9/12" when L5 dimensions were flagged, and how the strategic claim "5x ahead" was rewritten as a quarantined inference

### Provenance for This Update

nerissa pushed back on a Claude-generated report that combined "founder self-report 月入百万 → ARR $10M+" (L5) with "Crunchbase $40.6M cumulative" (L1B) in the same scoring table without distinguishing credibility. The propagated error meant strategy conclusions built on un-verified self-reports were treated with the same confidence as audited financial data. The 5-level pyramid was directly transplanted from evidence-based medicine where the same anti-pattern (treating expert opinion same as RCT) caused decades of clinical errors before EBM systematized it.

The behavioral rule: **never let an L5-backed scoring item win the strategy conversation alone.**

## [1.0.0] - 2026-06-05

### Added
- Initial release of `nerissa-competitive-research` skill
- Core SKILL.md with 7-step SOP, 6-dimension scoring, dual-track structure, anti-lazy rules
- English README + Chinese README
- `references/feishu-base-schema.md` — ready-to-bash Feishu Base setup script
- `references/six-dimension-scoring-worksheet.md` — print-and-fill scoring template
- `references/anti-lazy-checklist.md` — pre-publish checklist
- 5 sanitized worked examples in `examples/`:
  - 01 · Bootstrapped SaaS found via LATKA cross-check
  - 02 · Funding wave packaging layer essence decomposition
  - 03 · China direct competitor found in news
  - 04 · Incumbent (giant) warning treatment
  - 05 · Fundraising-reference vs business-learning dual-track example

### Provenance
Extracted from real competitive research practice at an early-stage growth-stage startup. Every principle traces back to a documented failure that was caught and corrected.
