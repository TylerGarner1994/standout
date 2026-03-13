# Generate Ad Creatives

Generate a full set of Meta ad creatives for a client across multiple creative styles.

## Target
$ARGUMENTS (provide client name — must have a client profile in memory/clients/)

## Process

### Step 1: Load Context
1. Load client profile from `memory/clients/{client}.md`
2. If a landing page exists, review it for key messaging, headline, CTA
3. Identify target demographic and key selling points

### Step 2: Generate Creatives
Create ad images across 6 styles, 2-3 variants each:

| Style | Format | Description |
|-------|--------|-------------|
| `photoshoot` | 1080x1080 | Lifestyle photography with product in context |
| `minimal` | 1080x1080 | Clean, minimal text on simple background |
| `typography` | 1080x1080 | Typography-forward with bold text and brand colors |
| `story` | 1080x1920 | Instagram Stories / Reels vertical format |
| `dr` | 1080x1080 | Direct response — price, offer, urgency, strong CTA |
| `creative` | 1080x1080 | Conceptual / pattern interrupt creative |

### Step 3: Quality Control
For each generated image:
- Verify text is legible at mobile sizes
- Check CTA has no trailing period
- Verify brand colors match profile
- Regenerate any that fail QA

### Step 4: Save & Report
1. Save all images to `{client}/assets/ads/{style}-{n}.png`
2. Report summary:
   - Total ads generated
   - Styles covered
   - QA results (passed/total)
   - Any regenerations needed

### Step 5: Commit
Commit with message:
```
Add {client} ad images (automated pipeline)

{N} ads across {M} styles ({count} each): {style list}
All QA passed {passed}/{total}. {regeneration notes if any}
```
