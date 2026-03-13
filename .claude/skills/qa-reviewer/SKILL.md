---
name: qa-reviewer
description: >
  Meticulous Quality Assurance review for landing pages before deployment. Performs visual QA
  (desktop + mobile screenshots), content QA, technical QA, and brand consistency checks.
  Stores verified data in persistent agent memory to avoid re-checking known facts.
  Trigger phrases: "QA this page", "check the page", "review for bugs", "technical review",
  "is there anything broken", "check for issues", "run QA", "quality check".
metadata:
  author: standout-social
  version: '1.0'
---

# QA Reviewer

Meticulous quality assurance for landing pages. Catches every error, inconsistency, and quality issue before a page goes live.

## When to Use This Skill

Use this skill when:
- A page needs technical QA before deployment (Phase 4 of UCE)
- The user asks to "QA", "check", or "review for bugs"
- After making edits to an existing live page
- Any time code changes are made to HTML/CSS/JS

This is DIFFERENT from the expert-review-panel (which reviews copy/conversion quality). This skill reviews technical quality and correctness.

## Checks to Perform

### 1. Visual QA

Screenshot the page at multiple breakpoints:
- **Desktop:** 1440px width
- **Tablet:** 768px width
- **Mobile:** 375px width

Check for:
- [ ] Text overflow, truncation, or overlap at every breakpoint
- [ ] All images load correctly (no broken image icons)
- [ ] Dark section text contrast (white/light text on dark backgrounds must be readable)
- [ ] No placeholder content ("Lorem ipsum", "TODO", "{{placeholder}}", "example.com")
- [ ] CTA buttons are properly styled, visible, and clickable
- [ ] No horizontal scrollbar on mobile
- [ ] Sticky CTA appears correctly after hero scrolls out
- [ ] Animations/transitions work smoothly
- [ ] No visual gaps or misaligned sections

### 2. Content QA

- [ ] Headings are hierarchical (H1 → H2 → H3, no skipped levels)
- [ ] Testimonials use "Verified Buyer" or real attribution — NO fake names with ages
- [ ] Statistics and claims have proper context (not misleading)
- [ ] Disclaimers present where required (sponsored content, results not typical, etc.)
- [ ] No em dashes (—) — convert to en dashes (–) or rewrite the sentence
- [ ] No orphaned words in headlines (single word on last line)
- [ ] CTA copy is action-oriented and consistent across all buttons
- [ ] No spelling or grammar errors
- [ ] Phone numbers, emails, addresses are correct (if present)

### 3. Technical QA

- [ ] All links/hrefs point to correct URLs (not "#" placeholders, unless JS overwrites before display)
- [ ] All external URLs use `https://`
- [ ] Meta tags complete: `<title>`, `<meta name="description">`, OG tags (og:title, og:description, og:image)
- [ ] Favicon is set and loads
- [ ] No JavaScript console errors on page load
- [ ] Page weight under 500KB (excluding large hero images)
- [ ] ALL CSS is inline (no `<link rel="stylesheet">` to external files)
- [ ] ALL JS is inline (no `<script src="...">` to external files)
- [ ] Mobile viewport meta tag: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- [ ] All `<img>` tags have `alt` attributes
- [ ] No `console.log()` or debug statements in production JS

### 4. Brand Consistency

Load the client profile from `memory/clients/{client}.md` and verify:
- [ ] Brand colors match the profile (check CSS variables, backgrounds, buttons, text)
- [ ] Fonts match the profile (heading font, body font)
- [ ] Logo is the correct version
- [ ] Brand voice matches (formal/casual/authoritative — consistent throughout)
- [ ] Visual style matches (minimal/bold/editorial — consistent with brand)

## Persistent Memory

Store verified facts in `.claude/agent-memory/qa-reviewer/MEMORY.md`:
- Confirmed brand colors (hex codes) for each client
- Confirmed product prices
- Confirmed review counts and ratings
- Common acceptable patterns (so you don't re-flag known non-issues)
- Screenshots saved to `.claude/agent-memory/qa-reviewer/screenshots/`

This prevents re-verifying known data across sessions.

## Output Format

```markdown
## QA Report: {page-name}
**Date:** {date}
**Status:** PASS / FAIL / PASS WITH NOTES

### Issues Found
| # | Severity | Category | Description | Recommended Fix |
|---|----------|----------|-------------|----------------|
| 1 | Critical | ... | ... | ... |
| 2 | Major | ... | ... | ... |

### Checks Passed
- [x] Visual QA (desktop 1440px)
- [x] Visual QA (mobile 375px)
- [x] Content QA
- [x] Technical QA
- [x] Brand Consistency

### Screenshots
- Desktop: {path}
- Mobile: {path}

### Summary
{1-2 sentence summary of overall quality}
```

## Severity Levels

| Severity | Meaning | Action |
|----------|---------|--------|
| **Critical** | Must fix before deploy | Broken functionality, wrong client info, missing content, broken links |
| **Major** | Should fix before deploy | Design issues, contrast problems, unclear copy, mobile issues |
| **Minor** | Nice to fix | Small spacing issues, minor copy tweaks, optimization opportunities |
| **Note** | Not a defect | Suggestions for improvement, observations for future iterations |

## Rules

1. **Check EVERYTHING.** Don't skip items because the page "looks fine."
2. **Be specific.** "Section 4 heading overflows on mobile 375px" not "some text issues."
3. **Critical issues block deploy.** If any Critical issue exists, the page cannot ship.
4. **Take actual screenshots.** Don't guess about visual issues — verify them.
5. **Cross-reference the client profile.** Every color, font, and price should match.
