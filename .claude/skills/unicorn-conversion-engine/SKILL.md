---
name: unicorn-conversion-engine
description: >
  The core landing page creation engine. Use when asked to create, build, or generate a landing page,
  sales page, advertorial, listicle, VSL page, or quiz funnel. Orchestrates the full 4-phase pipeline:
  Discovery & Research → Psychology-Driven Copy → Expert Review Panel → Production Deployment.
  Ensures every page scores 90+ from the 10-expert review panel before shipping.
  Trigger phrases: "new landing page", "build a page", "create a page", "new advertorial",
  "new listicle", "new VSL", "new sales page", "new quiz", "UCE", "run the engine".
metadata:
  author: standout-social
  version: '1.0'
---

# Unicorn Conversion Engine (UCE)

The UCE is the complete system for creating world-class, psychology-driven landing pages. Every page goes through four phases and must score 90+ from a 10-expert review panel before deployment.

## When to Use This Skill

Use this skill when:
- Creating a new landing page for any client
- Building an advertorial, listicle, VSL, sales page, or quiz funnel
- The user says "run UCE", "new page", "build a landing page", or similar
- Any request that involves creating conversion-focused web content from scratch

## Prerequisites

Before starting:
1. Load the client profile from `memory/clients/{client}.md` (create one if it doesn't exist using `memory/clients/_template.md`)
2. Have at minimum: an offer URL or description, and brand materials (logo/website/screenshots)
3. Know the CTA destination (where buttons should link)

## Available Templates

| Template | File | Best For |
|----------|------|----------|
| Advertorial | `_templates/advertorial.html` | Native ads, editorial sales copy, article format |
| Listicle | `_templates/listicle.html` | "X Reasons Why..." numbered sections, stats, quotes |
| VSL | `_templates/vsl.html` | Video sales letters with trust stats |
| Sales Page | `_templates/simple-sales.html` | Direct offers, features grid, pricing card |
| Quiz | *(built custom per client)* | Interactive quiz with personalized results |

---

## Phase 1: Discovery & Research

### 1.1 Analyze the Offer
- **WebFetch** the offer URL to understand current positioning
- Extract key offer elements: price, deliverables, guarantees, bonuses
- Identify the core transformation/outcome promise
- Note any urgency elements or scarcity

### 1.2 Brand Extraction
Run the `brand-extraction` skill OR manually extract:
- **Primary colors** (hex codes)
- **Secondary/accent colors**
- **Typography** (heading font, body font, weights)
- **Logo** (download to assets folder)
- **Brand voice** (formal, casual, authoritative, friendly)
- **Visual style** (minimal, bold, editorial, playful)
- Save results to `memory/clients/{client}.md`

### 1.3 ICP Deep Dive
Research the Ideal Customer Profile thoroughly:

| Dimension | What to Find |
|-----------|-------------|
| **Demographics** | Age, income, profession, location |
| **Psychographics** | Values, beliefs, aspirations, fears |
| **Current State** | Pain points, frustrations, failed solutions |
| **Desired State** | Goals, dreams, what success looks like |
| **Objections** | Why they might NOT buy (top 5-7 objections) |
| **Triggers** | What would make them buy TODAY |
| **Language** | Exact phrases they use to describe their problem |

### 1.4 Trend Research
WebSearch for current best practices:
- "landing page design trends {current_year}"
- "highest converting sales page examples {current_year}"
- "CRO best practices {current_year}"
- "above the fold optimization {current_year}"

Incorporate: mobile-first responsive, micro-interactions, social proof placement, friction-reducing forms, trust signal positioning, scroll-triggered CTAs.

---

## Phase 2: Psychology-Driven Copy Creation

Select the appropriate template from `_templates/` and build the page applying ALL of the following frameworks:

### 2.1 System 1 Triggers (Emotional / Intuitive / Fast)

These trigger automatic, emotional responses:

| Trigger | How to Implement |
|---------|-----------------|
| **Visual hierarchy** | Hero image, color contrast, strategic whitespace |
| **Social proof** | Testimonials, logos, numbers ("10,000+ customers") |
| **Authority** | Expert endorsements, credentials, media logos, "as seen in" |
| **Scarcity** | Limited spots, countdown timers, "only X left" |
| **Urgency** | Deadlines, expiring bonuses, price increase warnings |
| **Reciprocity** | Free value upfront (guides, tools, bonuses before the ask) |
| **Liking** | Relatable founder stories, behind-the-scenes, brand personality |

### 2.2 System 2 Triggers (Rational / Analytical / Slow)

These engage deliberate, logical processing:

| Trigger | How to Implement |
|---------|-----------------|
| **ROI calculation** | "Pays for itself in X days", cost-per-day breakdown |
| **Feature comparison** | vs. alternatives, vs. doing nothing, vs. status quo |
| **Risk reversal** | Money-back guarantees, free trials, "nothing to lose" |
| **Specificity** | Exact numbers, timeframes, deliverables — never vague |
| **Logic flow** | Problem → Agitate → Solution → Proof → CTA |
| **Objection handling** | FAQ section, preemptive rebuttals woven into copy |
| **Social validation** | Case studies with specifics, before/after data, named testimonials |

### 2.3 Neuromarketing Principles

**Attention Capture:**
- Pattern interrupts in first 3 seconds (unexpected stat, bold claim, provocative question)
- Color contrast and psychology (red for urgency, green for growth, blue for trust)
- Faces with eye direction pointing toward CTA
- Subtle, purposeful movement and animation

**Memory Anchoring:**
- Rule of 3 (three key benefits, three testimonials, three steps)
- Concrete language over abstract ("$47/month" not "affordable")
- Emotional anchoring to key messages
- Repetition of core promise at least 3x on page

**Decision Architecture:**
- Reduce cognitive load (fewer choices = more conversions)
- Default options and clear recommendations
- Loss aversion framing ("Don't miss out", "You're leaving money on the table")
- Price anchoring (show higher reference point before real price)

### 2.4 NLP Language Patterns

Weave these throughout the copy naturally:

| Pattern | Example | Purpose |
|---------|---------|---------|
| **Presuppositions** | "When you start seeing results..." | Assumes the outcome is inevitable |
| **Embedded commands** | "Imagine yourself already achieving..." | Plants action in subconscious |
| **Future pacing** | "Picture yourself 30 days from now..." | Creates mental ownership |
| **Sensory language** | "Feel the confidence... see the results..." | Engages multiple processing modes |
| **Cause-effect** | "Because you're reading this, you already know..." | Creates logical inevitability |
| **Mind reading** | "You're probably wondering if this will work for you..." | Builds rapport through empathy |
| **Modal operators** | "You can... You will... You deserve..." | Opens possibility and permission |

### 2.5 Behavioral Economics

| Principle | Implementation |
|-----------|---------------|
| **Anchoring** | Show original price / competitor price before the actual price |
| **Loss aversion** | Frame what they LOSE by not acting (2x more powerful than gains) |
| **Endowment effect** | "Your transformation is waiting" — make it feel already theirs |
| **Sunk cost** | Reference time/money already spent on the problem |
| **Social proof** | "Join 10,000+ others who..." — tribal belonging |
| **Commitment/consistency** | Small yes before big yes (quiz, email capture, micro-commitment) |
| **Peak-end rule** | Strong opening hook + powerful closing CTA (what they remember) |

---

## Phase 3: Expert Review Panel

**CRITICAL: Every page must pass through the expert-review-panel skill before deployment.**

Run the `expert-review-panel` skill on the completed page:
- All 10 experts evaluate and score
- Must achieve 90+ average across all experts
- If below 90: compile feedback, fix lowest-scoring dimensions, re-run review
- Iterate until 90+ is achieved — never ship below threshold

See the `expert-review-panel` skill for full scoring criteria and expert profiles.

---

## Phase 4: Production & Deployment

### 4.1 Asset Organization

```
/{client-name}/
├── index.html          # Main landing page (self-contained)
└── assets/
    ├── logo.png        # Client logo
    ├── hero.jpg        # Hero section image
    ├── testimonial-1.jpg
    ├── testimonial-2.jpg
    ├── product-shot.png
    ├── favicon.ico
    └── og-image.jpg    # Social sharing image (1200x630)
```

### 4.2 Technical QA Checklist

Run through EVERY item before deploy:

**Content:**
- [ ] No placeholder content (search for "Lorem", "TODO", "{{", "placeholder", "example.com")
- [ ] All headlines are final copy
- [ ] All testimonials properly attributed ("Verified Buyer" pattern — no fake names/ages)
- [ ] Disclaimer footer present for advertorials
- [ ] CTA links point to correct destination (not "#")
- [ ] No em dashes (—) in copy

**Technical:**
- [ ] Mobile viewport meta tag present
- [ ] Descriptive `<title>` tag
- [ ] `<meta name="description">` set
- [ ] OG meta tags set (og:title, og:description, og:image)
- [ ] Favicon linked
- [ ] ALL CSS inline (no external stylesheet links)
- [ ] ALL JS inline (no external script links)
- [ ] No console errors
- [ ] All external URLs use https
- [ ] All images have alt attributes

**Performance:**
- [ ] Images optimized (WebP where possible)
- [ ] Page weight under 500KB (excluding large hero images)
- [ ] No debug code or unnecessary comments

**Responsive:**
- [ ] Tested at 375px (mobile)
- [ ] Tested at 768px (tablet)
- [ ] Tested at 1024px (small desktop)
- [ ] Tested at 1440px (desktop)
- [ ] No horizontal scrollbar at any breakpoint

### 4.3 Deploy

1. Create directory at repo root: `{client-name}/` or `{client-name}/{page-type}/`
2. Place `index.html` and `assets/` folder
3. Create branch: `claude/{client-name}-{page-type}`
4. Commit with message:
   ```
   Add {client} {page-type} landing page

   - {brief description}
   - Expert panel score: {score}/100
   - All QA checks passed
   ```
5. Push to remote — auto-merge workflow handles deployment
6. Verify live URL works
7. Report live URL + local preview path to user

### 4.4 Deliverables

Provide to client:
1. **Live URL** — the GitHub Pages URL
2. **Local preview** — file:/// path for Chrome
3. **Asset folder** — location for future edits
4. **Expert scores** — summary table of panel feedback

---

## Technical Standards

All pages must follow these rules:
- **Self-contained single HTML file** — inline CSS + inline JS
- **No external frameworks** — no Bootstrap, Tailwind, React, jQuery
- **No tracking pixels** — client adds their own analytics
- **Vanilla JS only** — IntersectionObserver for scroll effects, sticky CTAs, counter animations
- **CSS custom properties** for theming (easy brand color swaps)
- **Mobile-first responsive** — design for 375px first, scale up

## Color Scheme Defaults

Use these when no client brand colors exist:

| Scheme | CSS Variables | Best For |
|--------|--------------|----------|
| Premium | `--bg-dark: #0a0e1a; --accent: #EAA34F` | High-end, luxury |
| Modern | `--bg-dark: #0a0a0a; --accent: #ff5722` | Bold, energetic |
| Corporate | `--bg-dark: #0f172a; --accent: #3b82f6` | B2B, professional |
| Growth | `--bg-dark: #0a0a0a; --accent: #22c55e` | Health, wellness |
| Clean | `--bg: #fafafa; --accent: #0d9488` | Minimal, modern |

---

## Quick Start Prompt

To trigger the full UCE pipeline, provide:
1. Offer URL (or detailed description)
2. Brand materials (logo, website URL, or screenshots)
3. CTA destination (where buttons should link)
4. Any existing assets (images, testimonials in a folder)

Example:
```
Create a landing page for https://example.com/offer
Brand assets are in the /client-name/ folder.
CTA should go to https://example.com/checkout.
Page type: advertorial.
```

The engine will execute all 4 phases autonomously, iterate until 90+ expert score, and deploy to production.
