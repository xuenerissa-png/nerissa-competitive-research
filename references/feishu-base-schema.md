# Feishu Base Schema · Ready-to-Bash Setup

Creates a 24-field competitor research table in Feishu Base via `lark-cli`. Requires `lark-cli` installed and authenticated (`lark-cli auth login --domain base`).

## Quick Setup (3 commands)

### 1. Create the table

```bash
BASE_TOKEN="YOUR_BASE_TOKEN_HERE"

lark-cli base +table-create \
  --base-token "$BASE_TOKEN" \
  --name "Competitor Research v1.0" \
  --as user
```

Note the returned `table-id` (e.g. `tblXXXXXXXX`) — use it as `$TBL` below.

### 2. Rename the default primary field

```bash
TBL="tblXXXXXXXX"

# First get the default primary field-id
lark-cli base +field-list --base-token "$BASE_TOKEN" --table-id "$TBL" --as user \
  | grep -oE '"id":\s*"fld[^"]+"' | head -1

# Then rename it to "Company"
lark-cli base +field-update \
  --base-token "$BASE_TOKEN" --table-id "$TBL" --field-id "fldYYY" \
  --json '{"type":"text","name":"Company"}' --as user
```

### 3. Add the 23 additional fields (bash loop)

```bash
for spec in \
  '{"type":"select","name":"Priority","multiple":false,"options":[{"name":"⭐⭐⭐⭐⭐ Must See","hue":"Red"},{"name":"⭐⭐⭐⭐ Recommended","hue":"Orange"},{"name":"⭐⭐⭐ Bonus","hue":"Yellow"},{"name":"⭐⭐ Pitch Reference","hue":"Purple"},{"name":"✗ Removed","hue":"Gray"}]}' \
  '{"type":"select","name":"Benchmark Role","multiple":false,"options":[{"name":"Primary Benchmark","hue":"Red"},{"name":"Business Model Template","hue":"Orange"},{"name":"Dual Engine Reference","hue":"Yellow"},{"name":"Per-Outcome Pricing","hue":"Green"},{"name":"Bootstrapped Sample","hue":"Blue"},{"name":"Reverse Reference","hue":"Purple"},{"name":"Pipeline Cohort","hue":"Carmine"},{"name":"China-to-Global Story","hue":"Wathet"}]}' \
  '{"type":"text","name":"Website","style":{"type":"url"}}' \
  '{"type":"text","name":"Founded Year"}' \
  '{"type":"text","name":"Headquarters"}' \
  '{"type":"text","name":"Founders"}' \
  '{"type":"text","name":"Team Size"}' \
  '{"type":"text","name":"Cumulative Funding"}' \
  '{"type":"text","name":"Current Valuation"}' \
  '{"type":"text","name":"Latest Round"}' \
  '{"type":"text","name":"Lead Investor"}' \
  '{"type":"text","name":"ARR"}' \
  '{"type":"text","name":"Business Model"}' \
  '{"type":"text","name":"One-Liner: What It Is"}' \
  '{"type":"text","name":"One-Liner: What To Copy"}' \
  '{"type":"text","name":"3 Must-See Pages"}' \
  '{"type":"text","name":"What We Should Learn"}' \
  '{"type":"text","name":"Known Customers"}' \
  '{"type":"text","name":"Study Duration"}' \
  '{"type":"select","name":"Overall Judgment","multiple":false,"options":[{"name":"🔥 Copy Directly","hue":"Red"},{"name":"⭐ Partial","hue":"Orange"},{"name":"👀 Enough","hue":"Yellow"},{"name":"✗ Not Applicable","hue":"Gray"},{"name":"⏳ Pending My Review","hue":"Blue"}]}' \
  '{"type":"datetime","name":"Site Visit Date","style":{"format":"yyyy-MM-dd"}}' \
  '{"type":"text","name":"Data Sources"}' \
  '{"type":"text","name":"📄 Linked Report","style":{"type":"url"}}' \
  '{"type":"text","name":"💬 My Notes / Corrections"}' \
  '{"type":"text","name":"💰 Pricing Detail (Verified)"}'; do
  sleep 1
  lark-cli base +field-create --base-token "$BASE_TOKEN" --table-id "$TBL" --json "$spec" --as user
done
```

Total: 24 fields (Company + 23 added). All set.

## Why these 24 fields?

| Group | Fields | Why mandatory |
|---|---|---|
| **Identity** (5) | Company / Website / Founded / HQ / Founders | Verifiable basics |
| **Scale** (3) | Team / Cumulative Funding / Current Valuation | Multi-source verify required |
| **Recent activity** (3) | Latest Round / Lead Investor / ARR | Tells you if they're alive and active |
| **Mechanism** (1) | Business Model | Must open pricing page to fill |
| **Synthesis** (4) | One-line What It Is / What To Copy / 3 Must-See / What To Learn | Forces you to think, not just collect |
| **Validation** (2) | Known Customers / Data Sources | Anti-lazy proof |
| **Workflow** (3) | Priority / Benchmark Role / Study Duration | For your own filtering |
| **Feedback loop** (3) | Overall Judgment / Site Visit Date / Linked Report | Track that you (or user) actually visited |

## Adapting to Other Databases

For Notion / Airtable / your own tool: the 24 fields above port directly. Just create them as the equivalent property types (text / select / date / URL). Use the same names so the SKILL.md output drops in cleanly.

## Common Issues

| Issue | Fix |
|---|---|
| `Field option not found` when batch-inserting records | The select field options auto-add when first record uses them — or pre-create option list in field schema |
| 中文 sed 替换里出错 | Use a `--json` file (`@records.json`) instead of inline JSON with Chinese brackets |
| `"ok":false "not_found" "Priority"` | The Priority select option you wrote doesn't exist yet — add it to field schema first via `+field-update` |
