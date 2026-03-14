# Standout Social — Landing Page Factory

## CRITICAL: Campaign State First
**Before creating ANY content for a client, a Campaign State document MUST exist at `memory/clients/{client}.md`.** This is the #1 quality driver. The campaign state contains brand injection strings, buyer personas, cognitive bias profiles, competitive intelligence, and creative strategy. Without it, output will be generic. With it, output will be targeted, specific, and high-converting.

If no campaign state exists, build one using `memory/clients/_template.md` BEFORE starting creative work.

## Skills (Core Intelligence)
The following Skills power this system. Claude Code will auto-discover them based on context, or you can reference them directly:

| Skill | What It Does | Trigger |
|-------|-------------|---------|
| `unicorn-conversion-engine` | Full 5-phase pipeline: Campaign State → Discovery → Copy → Expert Review → Deploy | "new page", "build a page", "run UCE" |
| `expert-review-panel` | 10-expert scoring panel, 90+ gate to ship | "review the page", "run the panel", "score this" |
| `brand-extraction` | Extract colors, fonts, styles from any URL | "extract brand", "pull brand colors" |
| `ad-creative-pipeline` | Generate 25-35 Meta ad creatives with persona targeting and bias stacking | "generate ads", "make ad creatives" |
| `qa-reviewer` | Technical QA: visual, content, technical, brand checks | "QA this page", "check for bugs" |

**Skills live at:** `.claude/skills/{skill-name}/SKILL.md`

## Design System
**ALWAYS read `_templates/DESIGN-SYSTEM.md` before building any page.** It defines 5 aesthetic directions (Editorial Magazine, Dark Premium, Clean Corporate, Bold DTC, Warm Wellness) with specific typography pairings, color palettes, and CSS patterns. Choose the right direction for the client — never default to a single look.

## Memory
All memory is in `memory/` at workspace root. Load relevant client profile before starting any client work.

## Session Start Protocol
1. Read `memory/glossary.md` for CSS lessons learned
2. Read `memory/context/` for reusable patterns and technical gotchas
3. Read `_templates/DESIGN-SYSTEM.md` for visual standards
4. If working on a specific client, load `memory/clients/{client}.md` (the campaign state)

## Session End Protocol
1. If you learned something reusable (CSS fix, pattern, gotcha), add it to the appropriate memory file
2. Update `memory/clients/{client}.md` — log the session, update generated content inventory
3. Update `.claude/agent-memory/qa-reviewer/MEMORY.md` if brand data was verified

## File Paths & Previewing Files
- **To preview ANY HTML file in Chrome**, use the `mcp__Control_Chrome__open_url` tool with your local file path
- **The workspace folder IS your local folder** — files written there are immediately accessible
- **DO NOT use localhost HTTP servers** — they are unreliable and unnecessary
- Pattern: `file:///Users/tylergarner_1/Desktop/standoutsocial.github.io/{project}/{file}`

## Client Work Rule
**Before starting work on ANY client folder**, load the campaign state: `memory/clients/{client}.md`. If no campaign state exists, build one using `memory/clients/_template.md` — this is NOT optional.

## Preferences
- Expert-level, production-ready outputs — never placeholder quality
- Values CRO, behavioral psychology, neuromarketing in landing pages
- Run the full workflow: campaign state → brand extraction → copy creation → expert review panel → deploy
- Expects Skills to be run (unicorn-conversion-engine, expert panels, etc.)
- Parallel execution for speed when possible
- No need to ask for approvals once plan is approved
- All pages must be self-contained single HTML files (inline CSS + JS, Google Fonts link OK)
- No external frameworks (no Bootstrap, Tailwind, React)
- No tracking pixels or analytics — client adds their own
- Vanilla JS only — IntersectionObserver, scroll effects, sticky CTAs
- **Typography matters** — always use intentional font pairings (serif + sans-serif for advertorials)
- **Every ad creative maps to a specific persona + awareness level + cognitive bias stack**

## Active Projects
| Name | What |
|------|------|
| *(add your first project here)* | Description |

## Terms
| Term | Meaning |
|------|---------|
| UCE | Unicorn Conversion Engine skill — the full landing page creation pipeline |
| Campaign State | The comprehensive strategic brief for a client (`memory/clients/{client}.md`) |
| Brand Injection String | Precise text block prepended to every image generation prompt |
| CRO | Conversion Rate Optimization |
| DTC | Direct to Consumer |
| NLP | Neuro-Linguistic Programming (in marketing context, not AI/ML) |
| DR | Direct Response |
| ICP | Ideal Customer Profile |
| VSL | Video Sales Letter |

## Page Types
| Type | Template | Aesthetic Direction | Description |
|------|----------|-------------------|-------------|
| Advertorial | `_templates/advertorial.html` | Editorial Magazine | Native ad, editorial copy, publication header, author byline |
| Listicle | `_templates/listicle.html` | Editorial Magazine | "X Reasons Why..." numbered sections |
| VSL | `_templates/vsl.html` | Dark Premium | Video sales letter with trust stats |
| Sales Page | `_templates/simple-sales.html` | Bold DTC or Clean Corporate | Direct offer, features grid, pricing |
| Quiz | *(built custom per client)* | Match client brand | Interactive quiz with personalized results |

## Patterns & Templates
| Pattern | Details |
|---------|---------|
| **Quiz Interstitials** | Always add social proof/fact stat cards between quiz questions (after Q1, Q3, Q5). Auto-dismiss after 2s. See `memory/context/quiz-interstitial-pattern.md` |
| **Sticky CTA** | Appears after hero scrolls out of viewport. Uses IntersectionObserver. |
| **Scroll Reveal** | Elements with `.reveal` class animate in on viewport entry. |
| **Counter Animation** | Stats animate counting up when they enter viewport. |
| **Progress Bar** | Thin bar at top of page showing scroll progress for long-form pages. |
| **Publication Header** | Fake pub name + nav for advertorials. Gives editorial credibility. |
| **Author Byline** | Fake author with title + date + read time. Required for advertorials. |