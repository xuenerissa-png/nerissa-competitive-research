---
name: nerissa-competitive-research
description: A disciplined 7-step competitive research SOP that prevents lazy AI shortcuts (sourcing from secondhand blogs, inheriting unverified judgments, confusing funding size with relevance). Forces verifiable two-source funding data, official-site visits, essence decomposition (technology vs packaging-layer vs sales), 6-dimension scoring, and dual-track separation (fundraising reference vs business learning target). Use when user says "research X company", "do competitive analysis", "调研 X 家", "竞品研究", "stress-test this competitor", or when adding any new competitor to a comparison table.
---

# nerissa-competitive-research · Disciplined Competitor Research SOP

A field-tested SOP for competitive research that refuses lazy AI shortcuts. Built from real mistakes — sourcing from secondhand blogs, inheriting unverified DD judgments, confusing funding size with relevance, treating "in negotiation" as "signed". Every rule in this skill traces back to a specific failure mode this skill prevents.

## When to Trigger

**✅ Trigger when**:
- User explicitly says: "research X company", "竞品调研", "调研 X 家", "do competitive analysis", "stress-test this competitor"
- Adding any new competitor to an existing comparison table or matrix
- Validating a competitor claim before publishing (pitch deck / report / website)
- User questions a previous competitive judgment ("are you sure about X?")

**❌ Do NOT trigger for**:
- Casual market discussion without a specific company
- User explicitly asks for a brief one-line answer
- General industry trend questions

## Core Principles (Earned from Real Failures)

| # | Principle | What It Prevents |
|---|---|---|
| 1 | **Every "signed / acquired / valuation / customer count" claim needs verifiable source** | Repeating "$500k seed" from a DD report when reality is "$0 bootstrapped" (one secondhand blog was wrong) |
| 2 | **Open the official website. Don't rely on aggregator blogs** | Treating an anti-scraping 403 as "no website exists" and skipping the company entirely |
| 3 | **Inheriting historical judgment requires explicit tagging** | Recommending a competitor on old DD without re-evaluating that it's actually a packaging layer over commodity tools |
| 4 | **Decompose the essence. Don't just describe what it does** | Saying "AI full-stack builder" without saying "essentially a packaging layer over UI-gen + BaaS + edge cloud" |
| 5 | **Funding size ≠ relevance** | Treating $400M-ARR companies as learning targets when their customer layer doesn't match yours at all |
| 6 | **Customer overlap requires verification, not intuition** | Claiming "their customers don't overlap with ours" when actual overlap is 30-50% |
| 7 | **Separate dual tracks: fundraising-reference vs business-learning** | Killing a $0-funded peer because "our fundraising goal is $10M+" — confusing two different uses |
| 8 | **Don't say "X has signed Y customers" without checking the source-of-truth database** | Reporting "we signed 3 customers" in 5 reports when source-of-truth showed 0 signed, 2 in quote, 9 in conversation |

## The 7-Step SOP (30-60 minutes per company)

### Step 1 · Open the official website (30 seconds)
- Open the main domain
- Screenshot the hero
- If site doesn't load / returns 403 → mark this fact, don't assume "no website"

### Step 2 · Find funding data (5 minutes)
**Source priority** (most to least trustworthy):
1. Crunchbase company page (primary)
2. Official funding PR / TechCrunch / Bloomberg
3. PitchBook (paid, summary visible)
4. LATKA (CEO self-reported, best for bootstrapped SaaS)
5. Secondhand aggregator blogs (use cautiously, require ≥ 2 independent sources to cross-verify)

**Required fields**: cumulative funding / current valuation / latest round (amount + date + lead) / ARR (if disclosed)

### Step 3 · Decompose the essence (10 minutes)
Ask 5 questions:
- What is it **essentially**? (technology / packaging layer / sales motion / brand / network effect)
- If it disappeared, what would happen? (many substitutes / high switching cost)
- What type of moat?
- Where does it sit on the 5-dimension category map? (service-delivery / customer-tier / pipeline-depth / vertical / business-model)
- In the current funding wave, what did it leverage? (technology / packaging / timing / capital)

### Step 4 · Verify customer overlap (10 minutes)
- Check customer logo wall on the official site
- Read 1-3 case studies to identify actual customer identity / size / pain point
- Search Twitter / Reddit / G2 / ProductHunt for real user feedback
- Cross-reference against your own current customers to assess overlap

### Step 5 · Score on 6 dimensions (5 minutes)
Score 0-2 on each, sum to 12. Only 8+ qualifies for Top.

| Dimension | 0 points | 1 point | 2 points |
|---|---|---|---|
| Customer overlap | Completely mismatched | Partial overlap | Highly overlapping |
| Business model borrowability | Path entirely different | Some shared mechanics | Directly copyable |
| Capital/team scale proximity | $100M+ / 100+ people | $10-50M / 30-80 people | <$10M / 2-20 people or bootstrapped |
| Recent activity | Dead / 18 months silent | 12 months product updates no funding | 6 months funding / ARR disclosed |
| Real cash flow | All funding-burn | ARR > $1M but funding-supported | Bootstrapped or ARR/funding > 1 |
| Pipeline relevance | Unrelated | Part of pipeline relevant | Full pipeline (Concierge) directly relevant |

### Step 6 · Produce 3 sentences (15 minutes)
- **One-sentence "what it is"**
- **One-sentence "what to copy"** (the single most important thing for you)
- **3 must-see pages** (let user visit themselves, not hear secondhand)

### Step 7 · Enter into structured database (5 minutes)
Use the 24-field schema (see `references/feishu-base-schema.md` for Feishu Base template).

## Dual-Track Structure (Don't Mix)

| Track | Purpose | Selection criterion |
|---|---|---|
| **A · Fundraising reference** | For pitch decks · cite $10M+ similar-direction companies | Look at funding scale only |
| **B · Business learning target** | For product/team decisions | Ignore funding · only look at path similarity |

Mixing them causes errors (e.g. killing a $0 bootstrapped 7-person $770k ARR company because "our funding goal is $10M+" — but it's track B, not track A).

## Required Output: 15 Mandatory Fields

Every researched company must populate these in your tracking database:

| Field | Required? | Must verify? |
|---|---|---|
| Company name | ✅ | - |
| Website URL | ✅ | Must have opened |
| Founded year | ✅ | Crunchbase / official |
| Headquarters | ✅ | - |
| Founders | ✅ | LinkedIn / company About |
| Team size | ✅ | LinkedIn / Crunchbase |
| Cumulative funding | ✅ | **≥ 2 independent sources** |
| Current valuation | ⚠️ if available | Official PR only |
| Latest round | ✅ | TechCrunch / company PR |
| Lead investor | ✅ | Same |
| ARR | ⚠️ if available | LATKA / official / prospectus |
| Business model | ✅ | Must have opened pricing page |
| One-line "what it is" | ✅ | You write |
| One-line "what to copy" | ✅ | You write |
| 3 must-see pages | ✅ | You pick |
| What to learn for your context | ✅ | 3-5 bullets |
| Known customers | ✅ | Customer wall on site |
| Time to study | ✅ | For user planning |
| Overall judgment | Left for user | 1 of 4: copy directly / partial / enough / not applicable |
| Data sources | ✅ | ≥ 2 URLs |

## Anti-Lazy Rules (Reject These Behaviors)

| ❌ Don't | ✅ Do |
|---|---|
| Infer "signed / acquired" from memory | Query the source-of-truth database |
| Inherit historical DD without re-validating | Open the site again every time |
| Recommend based on funding numbers alone | Score 6 dimensions, only 8+ recommended |
| Only describe "what it does" | Always ask "what is the essence — packaging / true tech?" |
| Estimate customer overlap by gut | Check site cases + Twitter / G2 reviews |
| Mix Track A and Track B in recommendations | Separate them, label which track each is in |
| Force "vertical X" branding from one sample | Need 3+ samples before generalizing to a vertical |
| Mention "anti-competitor-X" framing | Don't free-advertise your competitors |

## Triggers for New Research

| Trigger | Should you research? |
|---|---|
| Industry report mentions new company | 🟡 Depends |
| Investor / customer / peer mentions a company | ✅ Immediately |
| TechCrunch / 36Kr reports new funding in your space | ✅ Immediately |
| Conference brings in a new potential customer | ✅ Research the customer (not as competitor) |
| A giant (major e-commerce / social / cloud platform) enters similar space | ✅ Immediately + high priority |
| Existing competitor gets new funding / launches / collapses | ✅ Upgrade the existing card |
| Team member says "I think X company is impressive" | ⚠️ First ask 6-dimension preview · only 8+ goes to formal research |

## After Research: 3 Required Sync Points

Every completed research must update:
1. **Tracking database** (one new row, all fields filled)
2. **Master report doc** (update master + detailed narrative, monthly version bump)
3. **Memory file / project notes** (update "N companies in database" counter)

## How to Use This Skill

When invoked, Claude will:
1. Confirm the company name + which use case (Track A fundraising reference or Track B business learning target)
2. Execute the 7-step SOP in order
3. Score on 6 dimensions
4. Produce the 3-sentence output
5. Format the 15 mandatory fields for database entry
6. Flag any anti-lazy rule violations encountered

## Examples Inside This Skill

See `examples/` for 5 worked examples (sanitized) from real research sessions:
- `01-bootstrapped-saas-found-via-LATKA.md` — Bootstrapped SaaS case (corrected a $500k-seed myth via LATKA cross-check)
- `02-funding-wave-packaging-layer.md` — Funding-wave AI builder case (decomposed essence to UI-gen + BaaS + edge cloud packaging)
- `03-china-direct-competitor.md` — Direct local-market competitor found via tech-media news, multi-source verified
- `04-incumbent-warning.md` — Incumbent giant entry case (treated as warning, not deep research target)
- `05-fundraising-reference-vs-learning-target.md` — Enterprise giant vs bootstrapped peer (dual-track example)

## Linked Resources

- `references/feishu-base-schema.md` — Feishu Base table-creation script (24 fields, ready to bash)
- `references/six-dimension-scoring-worksheet.md` — Print-and-fill scoring template
- `references/anti-lazy-checklist.md` — Pre-publish checklist (don't publish until all green)

## A Note on Provenance

This skill was extracted from a real growth-stage startup's competitive research practice. Every principle in the "Core Principles" table corresponds to a documented failure that was caught and corrected. The 6-dimension scoring system was empirically derived from comparing 12 sample companies and noting which dimensions actually predicted "useful to learn from" vs "irrelevant to learn from."
