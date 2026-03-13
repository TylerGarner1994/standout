---
name: ad-creative-pipeline
description: >
  Generate a full set of Meta (Facebook/Instagram) ad creatives for a client across multiple
  creative styles. Produces 12-18 ad images across 6 styles with built-in QA.
  Trigger phrases: "generate ads", "create ad creatives", "make ads", "ad images",
  "Meta ads", "Facebook ads", "Instagram ads", "ad pipeline", "creative batch".
metadata:
  author: standout-social
  version: '1.0'
---

# Ad Creative Pipeline

Generate high-performing Meta ad creatives across multiple styles with automated quality control.

## When to Use This Skill

Use this skill when:
- A client needs ad creatives for Facebook/Instagram campaigns
- The user asks to "generate ads", "make ad images", or "run the ad pipeline"
- A landing page is deployed and needs accompanying ad creatives
- The user wants to batch-generate multiple ad variants

## Prerequisites

1. A client profile must exist at `memory/clients/{client}.md` (with brand colors, fonts, voice)
2. Ideally a completed landing page exists (for messaging alignment)

## Process

### Step 1: Creative Brief

1. Load client profile from `memory/clients/{client}.md`
2. If a landing page exists, review it to extract: key headline, value prop, CTA, social proof points
3. Identify:
   - Target demographic and psychographics
   - Top 3 selling points / pain points
   - Key transformation promise
   - Any specific offers (discounts, bonuses, free trials)

### Step 2: Generate Across 6 Styles

Create 2-3 variants of each style:

| Style | Format | Description | Best For |
|-------|--------|-------------|----------|
| `photoshoot` | 1080x1080 | Lifestyle photography with product in context | Aspirational brands, lifestyle products |
| `minimal` | 1080x1080 | Clean, minimal text on simple background | Brand awareness, premium positioning |
| `typography` | 1080x1080 | Typography-forward with bold text and brand colors | Direct response, offer-focused |
| `story` | 1080x1920 | Instagram Stories / Reels vertical format | Stories/Reels placements |
| `dr` | 1080x1080 | Direct response — price, offer, urgency, strong CTA | Conversion campaigns, retargeting |
| `creative` | 1080x1080 | Conceptual / pattern interrupt creative | Cold audiences, awareness |

### Step 3: Ad Copy Elements

For each creative, include:
- **Headline** (40 chars max) — the hook that stops the scroll
- **Primary text** (125 chars for feed) — the value prop in one line
- **CTA** — action-oriented, NO trailing period
- **Visual hierarchy** — headline → supporting text → CTA (clear reading order)

### Step 4: Quality Control

For EVERY generated image, verify:
- [ ] Text is legible at mobile sizes (would you be able to read it on a phone?)
- [ ] CTA has NO trailing period
- [ ] Brand colors match client profile
- [ ] No spelling/grammar errors in overlay text
- [ ] Visual hierarchy is clear (headline → body → CTA)
- [ ] Image resolution is correct (1080x1080 or 1080x1920)

Regenerate any that fail QA. Report: "All QA passed X/Y" or "Regenerated {file} — {reason}"

### Step 5: File Organization

Save all creatives to:
```
{client}/assets/ads/
├── creative-1.png
├── creative-2.png
├── dr-1.png
├── dr-2.png
├── minimal-1.png
├── minimal-2.png
├── photoshoot-1.png
├── photoshoot-2.png
├── story-1.png
├── story-2.png
├── typography-1.png
└── typography-2.png
```

### Step 6: Commit & Report

Commit with message:
```
Add {client} ad images (automated pipeline)

{N} ads across {M} styles ({count} each): {style list}
All QA passed {passed}/{total}. {any regeneration notes}
```

Report to user:
- Total ads generated
- Breakdown by style
- QA results (passed/failed/regenerated)
- File locations
