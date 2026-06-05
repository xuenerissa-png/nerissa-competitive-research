# Example 01 · Bootstrapped SaaS · Corrected via LATKA Cross-Check

## The Setup

Old DD report listed a company (let's call it **AcmeAttribution**) as a "$500k seed-funded B2B attribution SaaS, 8-person team." It was tagged as a peer for our own bootstrapped journey.

When a teammate asked to verify the funding before a pitch deck draft, I ran the SOP.

## What the SOP Caught

### Step 1 · Open the website
Loaded fine. They sell B2B revenue attribution. Customer logos: Stripe, HubSpot, Salesforce integrations visible. So far so good.

### Step 2 · Find funding data — and the contradiction

| Source | Funding stated |
|---|---|
| Old DD report we had | $500k seed |
| Crunchbase company page | "Bootstrapped" · no funding rounds listed |
| LATKA (CEO self-reported revenue) | $770k ARR · **0 outside funding** |
| Rewardful case study | "From $0 to $54k MRR in launch week · self-funded" |
| Official "About Us" | "We are bootstrapped from day one" |

**4 of 5 sources say $0 funding. The DD report was wrong.**

### Step 3 · Essence decomposition
- Not a packaging layer · they built proprietary multi-touch attribution
- True technical asset (CRM / ad platform / conversion API integration)
- Moat type: technical depth + customer integration switching cost

### Step 4 · Customer overlap
- Their customers: B2B SaaS founders with $5M+ ARR running paid ads
- Our customers: Chinese B2B founders going overseas, mostly no ads, mostly product-led
- **Overlap: 20%** (some shared customer types but main use case different)

### Step 5 · 6-dimension score

| Dimension | Score |
|---|---|
| Customer overlap | 1 (partial) |
| Business model borrowability | 1 (subscription, but different price point) |
| Capital/team scale proximity | 2 (7 people, $0 funding — perfectly matches our reality) |
| Recent activity | 1 (product updates but no funding news) |
| Real cash flow | 2 (profitable bootstrapped) |
| Pipeline relevance | 2 (attribution core is exactly our pipeline weakness) |
| **Total** | **9 / 12** |

### Step 6 · 3 sentences
- **What it is**: A bootstrapped B2B attribution SaaS that proves 8 people + $0 funding can reach $770k ARR
- **What to copy**: The "no free trial · $1500 onboarding fee" customer-gating that filters serious customers
- **3 must-see pages**:
  1. Pricing page (note the onboarding fee)
  2. "Why bootstrapped" founder essay
  3. Customer integrations page (which CRMs they support)

### Step 7 · Database entry — corrected version posted

## The Failure Pattern This Caught

The original "$500k seed" came from a single secondhand blog post that confused this company with a similarly-named one. Once the wrong number entered our DD report, it propagated for weeks.

**Rule extracted**: When a funding number is suspicious or important, query the CEO's own LATKA entry — they self-report and are accountable. Secondhand blogs are downstream.

## Lessons

1. Bootstrapped companies are systematically miscounted — they don't show up in funding databases, so analysts often assume "no data = small."
2. The "8 people · $770k ARR · 0 funding" pattern is your most replicable peer. Don't kill it because it doesn't match your fundraising-track filter.
3. Cross-verification across 3+ source types (database / case study / founder direct) catches what any single source misses.
