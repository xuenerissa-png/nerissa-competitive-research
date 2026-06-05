# Example 05 · Dual-Track Example · Sierra vs Bootstrapped Peer

## The Setup

Two companies on the original Top 5 competitor list:

- **Sierra** (US enterprise AI agent) — $1.475B cumulative funding, $15B valuation, 80-150 person team, F50 customers (Rocket Mortgage, SoFi, SiriusXM)
- **Cometly-like** (let's call it AcmeAttribution) — $0 funding, 7-person team, $770k ARR, bootstrapped 4 years

Initial recommendation logic: "both interesting, both in our adjacency."

Then user pushed back: **"our fundraising goal is $10M+. AcmeAttribution has $0 funding. Why are we even considering them?"**

This pushed me to realize I was mixing two different uses of "competitor research."

## What the SOP Caught

### The Hidden Confusion

I had been recommending both companies as if they served the same purpose. But:

- **Sierra** is useful as a **fundraising-pitch reference** ("we are a vertical version of Sierra's outcome model")
  - For this use, you need: large funding, recognized name, similar direction
  - You CAN'T realistically copy their playbook (different scale, customer, capital)
- **AcmeAttribution** is useful as a **business-learning target** ("their bootstrap path is what we can actually replicate")
  - For this use, you need: similar team size, similar funding (or none), similar customer constraints
  - You CAN copy their playbook (similar reality)

I was scoring them on the same 6 dimensions, which gave incoherent results. Sierra scored low on "capital scale proximity" (0 points · obviously) and that was killing it from recommendation — but it shouldn't have, because Sierra was never meant to be a learning target.

### The Dual-Track Fix

Restructured the recommendation into two tracks:

#### Track A · Fundraising Reference
Selection criterion: **$10M+ funding in similar direction** (so we can credibly cite "we're like X for Y" in pitch)

| Company | Cumulative Funding | Direction | Use |
|---|---|---|---|
| Sierra | $1.475B | Enterprise AI agent, outcome model | "Our outcome model is inspired by Sierra's per-resolution pricing" |
| Mega | $11.5M | "Service via Software" for SMB | "Our Service via Software approach aligns with Mega's framing" |
| Dreamdata | $66.9M | B2B attribution + activation | "We share Dreamdata's revenue-traced approach" |
| Warmly | $32M | SDR agents for SMB | "Same monthly price point ($99/seat) as Warmly" |

Result: 4 companies for pitch ammunition.

#### Track B · Business Learning Target
Selection criterion: **path replicability** — similar team, capital, customer constraints

| Company | Team | Funding | Why it's a learning target |
|---|---|---|---|
| AcmeAttribution | 7 | $0 | Proves bootstrap path to $770k ARR works |
| (Other peer 1) | 3 | $6M seed | Pay-per-meeting model can work small |
| (Other peer 2) | 9 | $500k seed | YC tactics for AI agent SDR space |
| (Other peer 3) | 50 | Pre-A in China | Direct China peer, similar customer base |

Result: 4 companies whose actual playbook we can replicate.

### Step 6 · Two sets of 3 sentences

**For Sierra (Track A · Fundraising)**
- What it is: $15B-valued outcome-pricing benchmark in adjacency
- What to copy (in pitch): "Pay for a job well done" framing
- 3 must-see pages: Hero, Customer Stories, Pricing (Contact Sales)

**For AcmeAttribution (Track B · Learning)**
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

This single discipline change rescued AcmeAttribution from the cut list and put it as Top 1 in Track B.
