# Example 05 · Dual-Track Example · Enterprise Giant vs Bootstrapped Peer

## The Setup

Two companies on the original Top 5 competitor list:

- **An enterprise AI agent giant** — $1.475B cumulative funding, $15B valuation, 80-150 person team, Fortune 50 customers
- **A bootstrapped attribution SaaS** — $0 funding, 7-person team, $770k ARR, bootstrapped 4 years

Initial recommendation logic: "both interesting, both in our adjacency."

Then a teammate pushed back: **"our fundraising goal is $10M+. The bootstrapped one has $0 funding. Why are we even considering them?"**

This pushed the realization that two different uses of "competitor research" were being mixed.

## What the SOP Caught

### The Hidden Confusion

Both companies were being recommended as if they served the same purpose. But:

- **The enterprise giant** is useful as a **fundraising-pitch reference** ("we are a vertical version of giant X's outcome model")
  - For this use, you need: large funding, recognized name, similar direction
  - You CAN'T realistically copy their playbook (different scale, customer, capital)
- **The bootstrapped peer** is useful as a **business-learning target** ("their bootstrap path is what we can actually replicate")
  - For this use, you need: similar team size, similar funding (or none), similar customer constraints
  - You CAN copy their playbook (similar reality)

Scoring both on the same 6 dimensions gave incoherent results. The giant scored low on "capital scale proximity" (0 points · obviously) and that was killing it from recommendation — but it shouldn't have, because it was never meant to be a learning target.

### The Dual-Track Fix

Restructured the recommendation into two tracks:

#### Track A · Fundraising Reference
Selection criterion: **$10M+ funding in similar direction** (so we can credibly cite "we're like X for Y" in pitch)

| Company type | Cumulative Funding | Direction | Use in pitch |
|---|---|---|---|
| Enterprise giant | $1.475B | Enterprise AI agent, outcome model | "Our outcome model is inspired by their per-resolution pricing" |
| SMB Service-via-Software | $11.5M | "Service via Software" for SMB | "Our approach aligns with their framing" |
| B2B activation + attribution | $66.9M | Revenue-traced attribution | "We share their revenue-traced approach" |
| SDR agent for SMB | $32M | SDR agents | "Same monthly price point as their tier" |

Result: 4 companies for pitch ammunition.

#### Track B · Business Learning Target
Selection criterion: **path replicability** — similar team, capital, customer constraints

| Company type | Team | Funding | Why it's a learning target |
|---|---|---|---|
| Bootstrapped attribution | 7 | $0 | Proves bootstrap path to $770k ARR works |
| Pay-per-meeting outbound | 3 | $6M seed | Pay-per-meeting model can work small |
| YC AI agent SDR | 9 | $500k seed | YC tactics for AI agent SDR space |
| Local-market peer | 50 | Pre-A | Direct peer, similar customer base |

Result: 4 companies whose actual playbook can be replicated.

### Step 6 · Two sets of 3 sentences

**For the enterprise giant (Track A · Fundraising)**
- What it is: $15B-valued outcome-pricing benchmark in adjacency
- What to copy (in pitch): "Pay for a job well done" framing
- 3 must-see pages: Hero, Customer Stories, Pricing (Contact Sales)

**For the bootstrapped peer (Track B · Learning)**
- What it is: 7-person $0-funding $770k ARR proof point
- What to copy (in practice): No-free-trial + $1500 onboarding fee gating
- 3 must-see pages: Pricing, "Why bootstrapped" essay, Customer integrations

### Step 7 · Database entry: each company tagged with track in "Benchmark Role"

## The Failure Pattern This Caught

Mixing fundraising-reference with business-learning kills bootstrap peers (because they score low on "capital scale proximity") and over-promotes giants (because their funding is impressive but their playbook is unreachable).

**Rule extracted**: Always tag a company as either Track A or Track B before scoring. The 6-dimension scoring stays the same, but the threshold for "recommend" differs:
- Track A: capital proximity score doesn't matter (we know it's a giant, that's the point)
- Track B: capital proximity score matters a lot (we need a replicable peer)

## Lessons

1. "Competitor" is too vague a category — sub-classify into pitch-reference vs learning-target.
2. The pitch reference list should be short (4-6 companies) and impressive.
3. The learning target list should be short (3-5 companies) and replicable.
4. The same dimensions can mean different things depending on track. Don't apply one scoring threshold to both.

## How this changes the workflow

Before:
```
Research competitor → Score on 6 dimensions → Recommend if 8+ → Add to list
```

After:
```
Research competitor → Tag Track (A or B) →
  Score on 6 dimensions →
    Track A: ignore capital proximity, focus on funding scale + direction
    Track B: capital proximity is critical, plus path replicability
  Recommend if track-specific criteria met → Add to track-specific list
```

This single discipline change rescued the bootstrapped peer from the cut list and put it as Top 1 in Track B.
