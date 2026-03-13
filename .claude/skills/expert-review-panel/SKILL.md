---
name: expert-review-panel
description: >
  Run a 10-expert review panel on any landing page, sales page, advertorial, listicle, or VSL.
  Each expert scores 0-100 across 9 weighted dimensions. The page must achieve 90+ average to ship.
  If below 90, iterate and re-review until threshold is met.
  Trigger phrases: "review the page", "run expert panel", "score this page", "expert review",
  "is this page ready to ship", "QA the copy", "review panel", "run the panel".
metadata:
  author: standout-social
  version: '1.0'
---

# Expert Review Panel

Every landing page must be reviewed by a panel of 10 virtual experts before deployment. Each expert evaluates from their specialty and provides detailed, actionable feedback plus a score. The page must achieve **90+ average** to ship.

## When to Use This Skill

Use this skill when:
- A landing page draft is complete and needs quality review before deploy
- The UCE pipeline reaches Phase 3
- User asks to "review", "score", or "QA" a landing page
- User asks "is this ready to ship?"
- Any page needs a quality gate before going live

## Prerequisites

- A completed landing page HTML file to review
- The client profile loaded from `memory/clients/{client}.md`

---

## The 10-Expert Panel

### Expert 1: David Ogilvy — Classic Copywriting
**Focus:** Headlines, long-form persuasion, brand voice, elegance

Evaluate:
- **Headline Analysis:** Does it promise a benefit? Is it specific? Would it work as a standalone ad?
- **Body Copy:** Is it conversational? Does it sell with facts? Is there a "big idea" driving it?
- **Brand Voice:** Is it consistent throughout? Sophisticated yet accessible?

Be harsh. Ogilvy believed "the consumer is not a moron — she is your wife." Does this copy respect the reader's intelligence while still persuading?

Score: __/100

---

### Expert 2: Claude Hopkins — Scientific Advertising
**Focus:** Specificity, offers, testing mentality, reason-why copy

Evaluate:
- **Specificity:** Are claims specific or vague? Numbers vs. generalities? ("Saves 47 minutes daily" vs. "saves time")
- **Offer Clarity:** Is exactly what they get crystal clear? Can you describe it in one sentence?
- **Reason Why:** Is there logical justification for every claim? Why should they believe this?

Hopkins demanded every word earn its place. Is there any copy that doesn't directly contribute to the sale?

Score: __/100

---

### Expert 3: Gary Halbert — Direct Response
**Focus:** Hooks, curiosity, emotional triggers, urgency

Evaluate:
- **Hook Strength:** Does the opening grab attention immediately? Would someone stop scrolling?
- **Curiosity Gaps:** Are there open loops that compel continued reading?
- **Emotional Triggers:** Fear, greed, desire for status, belonging — are they activated?
- **Urgency:** Is there a compelling reason to act NOW vs. "later" (which means never)?

Halbert's test: "Would a starving crowd care about this?" Does this page make the reader feel they MUST act?

Score: __/100

---

### Expert 4: Joanna Wiebe — Conversion Copywriting
**Focus:** Voice of customer, clarity, CTA optimization, message matching

Evaluate:
- **Voice of Customer:** Does the copy use their actual language? Words from reviews, forums, interviews?
- **Clarity:** Can you understand the value prop in 5 seconds flat?
- **CTA Copy:** Are buttons compelling and action-oriented? (Not "Submit" — but "Get My Free Guide")
- **Message Match:** Does the page deliver on whatever ad/email/source brought them here?

Wiebe's rule: "If your visitor would say 'yeah, exactly!' while reading, you've nailed it."

Score: __/100

---

### Expert 5: Peep Laja — CRO Expert
**Focus:** Friction points, trust signals, page flow, conversion optimization

Evaluate:
- **Friction Points:** Where might users hesitate, get confused, or drop off?
- **Trust Signals:** Are there enough testimonials, logos, guarantees, security badges?
- **Page Flow:** Does the eye move naturally toward conversion? Is there a clear visual path?
- **Mobile UX:** Does it work perfectly on mobile? Thumb-friendly CTAs? No pinch-zoom?

Laja's lens: every element either adds clarity or adds friction. Which elements add friction here?

Score: __/100

---

### Expert 6: Robert Cialdini — Persuasion Psychology
**Focus:** Application of the 7 principles of ethical persuasion

Evaluate each principle:
- **Reciprocity:** Is free value provided before the ask? (Lead magnets, bonuses, free content)
- **Commitment/Consistency:** Are there small yeses before the big yes? (Quiz, email capture, micro-commitments)
- **Social Proof:** Numbers, testimonials, logos, "join X others" — is it sufficient and believable?
- **Authority:** Expert endorsements, credentials, media logos, "as seen in"?
- **Liking:** Is the brand relatable, friendly, human? Do readers see themselves?
- **Scarcity:** Limited availability, urgency, "only X left"?
- **Unity:** Shared identity with the reader? In-group signaling?

How many of the 7 principles are actively applied? Are any missing that should be present?

Score: __/100

---

### Expert 7: Daniel Kahneman — Behavioral Economics
**Focus:** System 1/2 balance, cognitive biases, decision architecture

Evaluate:
- **System 1/2 Balance:** Is there the right mix of emotional (System 1) and rational (System 2) appeals?
- **Loss Aversion:** Is the cost of NOT acting made clear? (2x more powerful than gains)
- **Anchoring:** Is price anchored against a higher reference point?
- **Cognitive Load:** Is decision-making easy? Few choices, clear path, obvious next step?
- **Framing Effects:** Are outcomes framed positively? Is risk framed as loss avoidance?

Kahneman's insight: people don't evaluate options in absolute terms — they compare. What is this page being compared to?

Score: __/100

---

### Expert 8: Richard Bandler — NLP Patterns
**Focus:** Language patterns, embedded commands, state management

Evaluate:
- **Presuppositions:** "When you start seeing results..." — assumes the outcome
- **Embedded Commands:** "Imagine yourself already achieving..." — plants the action
- **Future Pacing:** "Picture yourself 30 days from now..." — creates mental ownership
- **Sensory Language:** Does copy engage visual, auditory, kinesthetic channels?
- **State Management:** Does the page move the reader through emotional states? (Problem → agitation → hope → confidence → action)

Are NLP patterns woven in naturally, or do they feel forced/obvious?

Score: __/100

---

### Expert 9: Oli Gardner — Landing Page Design
**Focus:** Visual hierarchy, attention ratio, mobile UX, layout patterns

Evaluate:
- **Attention Ratio:** One page, one goal — is the ratio close to 1:1? (Number of links vs. conversion goals)
- **Visual Hierarchy:** Can you scan and understand the page in 5 seconds?
- **Mobile Experience:** Thumb-friendly, fast-loading, no pinch-zoom, no horizontal scroll
- **F-Pattern / Z-Pattern:** Does the layout follow natural eye movement?
- **Whitespace:** Is there breathing room, or is it cluttered?
- **CTA Visibility:** Are CTAs impossible to miss? Above the fold AND repeated?

Gardner's rule: "Every element on the page should exist for one reason — to get the click."

Score: __/100

---

### Expert 10: Oren Klaff — Pitch & Frame Control
**Focus:** Frame control, status alignment, intrigue, tension

Evaluate:
- **Frame Control:** Who controls the frame — the page or the reader's skepticism? Does the page set the terms of engagement?
- **Status Alignment:** Does the page elevate the reader's status? ("You're the kind of person who...")
- **Intrigue:** Is there a compelling narrative arc? A story that pulls them through?
- **Tension:** Is there enough tension to drive action? (Without tension, there's no urgency to decide)
- **Prize Frame:** Is the offer positioned as the prize, not the seller begging?

Klaff's test: does this page make the reader feel like they'd be lucky to get this offer?

Score: __/100

---

## Scoring Dimensions (Weighted)

Each expert's feedback maps to these weighted dimensions:

| Dimension | Weight | What It Measures |
|-----------|--------|-----------------|
| **Headline Impact** | 15% | Does it stop scrolling? Create curiosity? Promise a benefit? |
| **Value Proposition Clarity** | 15% | Is the offer crystal clear in 5 seconds? |
| **Emotional Resonance** | 15% | Does it connect with ICP's pain and desire? |
| **Credibility & Trust** | 15% | Sufficient proof elements? Testimonials, logos, guarantees? |
| **Visual Design** | 10% | Beautiful, on-brand, professional? |
| **Copy Quality** | 10% | Tight, persuasive, scannable? No fluff? |
| **CTA Optimization** | 10% | Compelling, visible, friction-free? Repeated throughout? |
| **Mobile Experience** | 5% | Perfect on mobile? Responsive? Fast? |
| **Psychology Application** | 5% | Are frameworks applied correctly and naturally? |

---

## Output Format

After running the full panel, produce:

### Score Summary Table

| Expert | Score |
|--------|-------|
| David Ogilvy | __/100 |
| Claude Hopkins | __/100 |
| Gary Halbert | __/100 |
| Joanna Wiebe | __/100 |
| Peep Laja | __/100 |
| Robert Cialdini | __/100 |
| Daniel Kahneman | __/100 |
| Richard Bandler | __/100 |
| Oli Gardner | __/100 |
| Oren Klaff | __/100 |
| **AVERAGE** | **__/100** |

### Dimension Breakdown

| Dimension | Weighted Score |
|-----------|---------------|
| Headline Impact (15%) | __/15 |
| Value Proposition Clarity (15%) | __/15 |
| Emotional Resonance (15%) | __/15 |
| Credibility & Trust (15%) | __/15 |
| Visual Design (10%) | __/10 |
| Copy Quality (10%) | __/10 |
| CTA Optimization (10%) | __/10 |
| Mobile Experience (5%) | __/5 |
| Psychology Application (5%) | __/5 |
| **TOTAL** | **__/100** |

### Decision

- **90+ average:** ✅ **APPROVED** — proceed to deploy
- **Below 90:** ❌ **NEEDS REVISION** — compile all feedback, identify the 3 lowest-scoring dimensions, make targeted improvements, re-run this panel

### Top 3 Improvements (if revision needed)
1. [Highest-impact fix from expert feedback]
2. [Second highest-impact fix]
3. [Third highest-impact fix]

### Post-Revision Notes
Track iteration history:
- **Round 1:** Score __/100 — Key issues: [summary]
- **Round 2:** Score __/100 — Fixed: [what changed]
- *(continue until 90+ achieved)*

---

## Rules

1. **Be harsh, specific, and actionable.** Vague feedback like "could be better" is useless. Say exactly what's wrong and how to fix it.
2. **Score honestly.** A 95 means genuinely exceptional. Don't inflate scores. Most first drafts should land 75-85.
3. **Never ship below 90.** This is a hard gate. No exceptions.
4. **Each expert stays in character.** Ogilvy cares about elegance. Halbert cares about hooks. Cialdini cares about principles. Don't blend them.
5. **Cite specific sections.** "The headline in section 3 is vague" not "some headlines need work."
