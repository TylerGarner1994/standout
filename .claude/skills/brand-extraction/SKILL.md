---
name: brand-extraction
description: >
  Extract brand colors, fonts, button styles, and visual identity from a client's website URL.
  Produces a complete brand style profile saved to the client memory file.
  Uses Chrome DevTools brand-extractor.js when available, falls back to regex-based extraction.
  Trigger phrases: "extract brand", "get brand colors", "brand extraction", "pull the brand",
  "what are their brand colors", "extract styles from", "brand profile".
metadata:
  author: standout-social
  version: '1.0'
---

# Brand Extraction

Extract a complete brand style profile from any website URL. This skill powers the Discovery phase of the UCE pipeline.

## When to Use This Skill

Use this skill when:
- Starting work on a new client (first step of UCE Phase 1)
- The user provides a website URL and needs brand colors/fonts extracted
- Updating an existing client's brand profile
- The user asks "what are their brand colors?" or "pull the brand"

## Process

### Step 1: Choose Extraction Method

**Method A — Live DOM (preferred):**
If Chrome DevTools / browser control is available via MCP:
1. Navigate to the target URL using `mcp__Control_Chrome__open_url`
2. Run the script from `_tools/brand-extractor.js` via JavaScript console
3. Capture the structured JSON output

**Method B — Regex Fallback:**
If Chrome DevTools is NOT available:
1. WebFetch the target URL to get raw HTML + CSS
2. Apply the regex patterns from `_tools/brand-extractor-fallback.js`:
   - Extract CSS custom properties from `:root` → regex: `:root\s*\{([^}]+)\}`
   - Extract hex color values → regex: `#(?:[0-9A-Fa-f]{3}){1,2}\b`
   - Extract Google Fonts links → regex: `fonts\.googleapis\.com/css2?\?family=([^"'>\s]+)`
   - Extract font-family declarations → regex: `font-family\s*:\s*([^;}]+)`
   - Extract background-color values → regex: `background(?:-color)?\s*:\s*([^;}]+)`
   - Extract button/CTA styles → target `.btn`, `.button`, `.cta` CSS rules
   - Extract gradients → regex: `(linear|radial)-gradient\([^)]+\)`
   - Extract border-radius → regex: `border-radius\s*:\s*([^;}]+)`
   - Extract box-shadow → regex: `box-shadow\s*:\s*([^;}]+)`

### Step 2: Analyze & Deduplicate

From the raw extraction:
1. **Colors:** Rank by frequency, filter out generic grays/blacks/whites (#000, #fff, #333, etc.)
2. **Identify primary color** (most prominent brand color, usually in logo/CTAs)
3. **Identify accent color** (secondary brand color, used for highlights)
4. **Identify background colors** (light and dark variants)
5. **Typography:** Identify heading font vs. body font, note weights used
6. **Button styles:** CTA button appearance (bg color, text color, border-radius, padding)

### Step 3: Build Brand Profile

Use `_tools/brand-style-template.md` as the output format. Fill in:

```markdown
## Colors
| Role | Color | Hex |
|------|-------|-----|
| Primary | {name} | {hex} |
| Primary Dark | {name} | {hex} |
| Primary Light | {name} | {hex} |
| Secondary | {name} | {hex} |
| Background | {name} | {hex} |
| Text | {name} | {hex} |
| Text Light | {name} | {hex} |
| Accent | {name} | {hex} |

## Typography
| Element | Font | Weight | Size |
|---------|------|--------|------|
| Headlines | {font} | {weight} | {size} |
| Subheads | {font} | {weight} | {size} |
| Body | {font} | {weight} | {size} |
| CTA Buttons | {font} | {weight} | {size} |

## Google Fonts Import
<link href="https://fonts.googleapis.com/css2?family={font1}&family={font2}&display=swap" rel="stylesheet">

## CSS Variables
:root {
    --primary: {hex};
    --primary-dark: {hex};
    --primary-light: {hex};
    --secondary: {hex};
    --bg: {hex};
    --bg-dark: {hex};
    --text: {hex};
    --text-light: {hex};
    --accent: {hex};
}

## Button Styles
.cta-button {
    background: {hex};
    color: {hex};
    border-radius: {value};
    padding: {value};
    font-family: {font};
    font-weight: {weight};
}

## Brand Voice
{formal | casual | authoritative | friendly | playful | professional}

## Visual Style
{minimal | bold | editorial | playful | corporate | premium}
```

### Step 4: Save & Report

1. Save the completed brand profile to `memory/clients/{client}.md`
2. Report to user:
   - Primary colors with hex codes
   - Typography (heading font, body font)
   - Button styles
   - CSS variables block (ready for copy-paste)
   - Google Fonts import tag
   - Any notable patterns (gradients, shadows, animations)

## Tools Reference

- `_tools/brand-extractor.js` — Chrome DevTools script for live DOM extraction
- `_tools/brand-extractor-fallback.js` — Regex patterns for HTML-based extraction
- `_tools/brand-style-template.md` — Output template with placeholder tokens
