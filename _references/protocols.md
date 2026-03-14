# MASTER PROTOCOLS REFERENCE

This document contains core operational protocols referenced by multiple skills.
Skills that reference this file: unicorn-conversion-engine

---

## TABLE OF CONTENTS

1. [Research Protocol](#research-protocol)
2. [Em Dash Protocol](#em-dash-protocol)
3. [Anti-Fabrication Protocol](#anti-fabrication-protocol)
4. [Quality Gates Protocol](#quality-gates-protocol)
5. [Offer Construction Protocol](#offer-construction-protocol)
6. [Conversion Audit Protocol](#conversion-audit-protocol)
7. [Competitive Intelligence Protocol](#competitive-intelligence-protocol)
8. [Landing Page Protocol](#landing-page-protocol)
9. [Ad Creative Protocol](#ad-creative-protocol)
10. [Follow-Up Sequence Protocol](#follow-up-sequence-protocol)

---

## RESEARCH PROTOCOL

### Purpose
Standardized approach for researching any business before creating marketing assets.

### Trigger
Activated whenever a URL is provided as input to any skill.

### Step 1: URL Analysis

```
Tool: web_fetch
Input: [provided URL]
Extract:
  - Business name
  - Core value proposition
  - Target audience
  - Products/services offered
  - Price points (if visible)
  - Social proof elements
  - Brand voice and tone
  - Key differentiators
  - Primary CTA
  - Contact information
```

### Step 2: Audience Research

```
Tool: web_search
Queries:
  - "[business name] reviews"
  - "[product category] customer complaints"
  - "[target audience] biggest frustrations with [category]"
  - "[business name] testimonials"

Extract:
  - Common pain points
  - Specific language customers use
  - Objections that prevent purchase
  - Desired outcomes customers seek
  - Failed alternatives they've tried
```

### Step 3: Competitive Analysis

```
Tool: web_search
Queries:
  - "[business name] alternatives"
  - "best [product category] [year]"
  - "[competitor names] vs [business name]"

Extract:
  - Top 3-5 competitors
  - Competitor positioning
  - Market gaps
  - Differentiation opportunities
```

### Step 4: Social Proof Mining

```
Tool: web_search
Queries:
  - "[business name] case studies"
  - "[business name] results"
  - "[business name] success stories"

Extract:
  - Specific metrics and numbers
  - Customer transformation stories
  - Before/after scenarios
  - Verifiable claims
```

### Output Format

```
## BUSINESS INTELLIGENCE BRIEF

**Business:** [Name]
**Industry:** [Category]
**Target Audience:** [Who they serve]
**Core Offer:** [What they sell]
**Primary Benefit:** [Biggest transformation]
**Price Point:** [If known]
**Brand Voice:** [Tone descriptors]
**Top Pain Points:**
  1. [Pain 1]
  2. [Pain 2]
  3. [Pain 3]
**Key Differentiators:**
  1. [Differentiator 1]
  2. [Differentiator 2]
**Social Proof Available:** [Yes/No + specifics]
**Competitive Landscape:** [Brief summary]
```

---

## EM DASH PROTOCOL

### The Problem
Em dashes (---) create an "AI writing" fingerprint that:
- Reduces perceived authenticity
- Signals automated content to readers
- Decreases trust in marketing copy
- Human copywriters rarely use them

### The Rule
**Em dashes are BANNED in all marketing copy, scripts, and content.**

### Verification Command
```bash
grep -c "---" [filename]
```
Required result: **0**

If count > 0: STOP. Fix ALL instances before delivery.

### Approved Replacements

| Instead of | Use |
|------------|-----|
| "solution---and it works" | "solution, and it works" |
| "results---guaranteed" | "results. Guaranteed." |
| "strategy---here's why" | "strategy. Here's why:" |
| "transform your business---starting today" | "transform your business starting today" |
| "proven system---used by" | "proven system used by" |

### Decision Tree

```
Need to connect two clauses?
  ├─ Use a COMMA if they're closely related
  ├─ Use a PERIOD if they're separate thoughts
  ├─ Use a COLON if the second explains the first
  ├─ Use a SEMICOLON if they're parallel thoughts
  └─ Use PARENTHESES if it's supplementary info
```

---

## ANTI-FABRICATION PROTOCOL

### What Is Fabrication?
Fabrication is inventing any piece of information that is presented as fact:
- Statistics and percentages
- Customer testimonials or quotes
- Research study findings
- Case study results
- Revenue or result claims
- Timeline claims ("in just 30 days")
- Comparison claims ("3x better than")
- Social proof numbers ("50,000 customers")

### The Fabrication Test
**Ask:** "Can I verify this through the client's website, their provided materials, or credible third-party sources?"

- **YES** → Include with attribution
- **NO** → Use [PLACEHOLDER] format
- **UNSURE** → Treat as NO

### PLACEHOLDER Formats

```
Statistics:
[X% of customers report improved results]
[Insert verified statistic here]

Testimonials:
[TESTIMONIAL: "[Result achieved] in [timeframe]. - Name, Title"]

Case Studies:
[CASE STUDY: Client went from [before] to [after] in [timeframe]]

Revenue Claims:
[Insert verified revenue result here]

Comparison Claims:
[Insert verified comparison data]

Social Proof:
[Insert actual customer count/rating]
```

### Why This Matters
1. **Legal risk** - False advertising claims can result in FTC action
2. **Trust destruction** - One discovered fabrication destroys all credibility
3. **Client protection** - You protect the business owner from liability
4. **Long-term performance** - Authentic copy outperforms fabricated copy over time

### Verification Sources
- Client's website and materials
- Published case studies
- Third-party review platforms
- Industry research reports (with citation)
- Client-provided data (with acknowledgment they're responsible for accuracy)

---

## QUALITY GATES PROTOCOL

### Purpose
Three mandatory checks before any deliverable is presented to the user.

### GATE 1: Em Dash Check

```
Command: grep -c "---" [filename]
Required result: 0
Action if failed: Rewrite ALL instances immediately
Time estimate: 5-10 minutes
```

### GATE 2: Fabrication Audit

```
Review checklist:
☐ All statistics → Verified or [PLACEHOLDER]
☐ All testimonials → Real or [PLACEHOLDER]
☐ All result claims → Verified or [PLACEHOLDER]
☐ All comparison data → Verified or [PLACEHOLDER]
☐ All timeline claims → Verified or [PLACEHOLDER]

Action if failed: Replace with [PLACEHOLDER] format
Time estimate: 10-15 minutes
```

### GATE 3: Output Quality Check

```
Review checklist (customize per deliverable type):

For copy/scripts:
☐ Reads naturally when spoken aloud
☐ Clear value proposition in opening
☐ Logical flow maintained throughout
☐ CTA is clear and compelling

For HTML/web assets:
☐ All interactive elements functional
☐ Mobile responsive (320px+)
☐ No JavaScript errors
☐ Load time acceptable

For email sequences:
☐ Each email has single clear purpose
☐ Subject lines non-spammy
☐ Unsubscribe link referenced
☐ No spam trigger words

Action if failed: Fix before delivery
Time estimate: 15-30 minutes
```

### Gate Failure Protocol

**If any gate fails:**
1. STOP immediately
2. Document what failed
3. Fix the specific issue
4. Re-run the gate
5. Do not proceed until gate passes
6. Note in delivery what was caught and fixed

---

## OFFER CONSTRUCTION PROTOCOL

### Purpose
Framework for building any marketing offer that maximizes perceived value and minimizes purchase resistance.

### The 5 Elements of an Irresistible Offer

**Element 1: The Core Product**
- Clear, specific description
- Primary benefit stated explicitly
- Delivery mechanism explained
- Timeline to result included

**Element 2: The Value Stack**
- List every component with individual value
- Assign credible (not inflated) dollar values
- Sum to total value amount
- Create clear gap between total value and price

```
Core Product: [Description] ...................... $[Value]
Bonus 1: [Description] .......................... $[Value]
Bonus 2: [Description] .......................... $[Value]
Bonus 3: [Description] .......................... $[Value]
                                    TOTAL VALUE: $[Sum]
                                YOUR PRICE TODAY: $[Price]
```

**Element 3: Risk Reversal**
- Guarantee type (money-back, results-based, conditional)
- Duration (30/60/90 days)
- Process (how to claim)
- Specificity (what triggers the guarantee)

```
Guarantee Template:
"Try [product] for [period]. If you don't [specific measurable result],
contact us at [contact method] within [timeframe] and we'll [specific action].
No questions asked. No hoops to jump through."
```

**Element 4: Urgency/Scarcity**

Only use REAL scarcity/urgency:
- Actual limited spots/inventory
- Real deadline (launch price, event)
- Genuine capacity constraints

NEVER use fake:
- "Only 3 left" when inventory is unlimited
- "Price goes up tomorrow" (that never happens)
- Countdown timers that reset

**Element 5: Social Proof Integration**
- Place testimonials adjacent to objections they overcome
- Use specific results, not vague praise
- Include identifying details (name, location, business type)
- Match testimonial type to buyer stage

### Price Anchoring Framework

```
Step 1: Establish high anchor
"Normally, this kind of [result] costs [high number]..."

Step 2: Justify the anchor
"...because [reason the high number makes sense]"

Step 3: Reduce to real price
"But today, your investment is just [real price]"

Step 4: Justify the real price
"Because [reason for reduced price that maintains credibility]"

Step 5: ROI calculation
"If this helps you [result] just once, that's worth [X times the price]"
```

---

## CONVERSION AUDIT PROTOCOL

### Purpose
Systematic review of any existing marketing asset to identify conversion killers and opportunities.

### 12-Point Conversion Audit Checklist

**1. Headline Clarity (0-10)**
- Does the headline state the primary benefit clearly?
- Would a stranger understand the offer in 3 seconds?
- Score: [0-10]

**2. Audience Match (0-10)**
- Does the copy speak directly to the target reader?
- Is the language at the right sophistication level?
- Score: [0-10]

**3. Problem Recognition (0-10)**
- Does the copy identify the reader's pain?
- Is the problem stated with enough specificity?
- Score: [0-10]

**4. Solution Clarity (0-10)**
- Is it clear what the product/service does?
- Is the mechanism explained?
- Score: [0-10]

**5. Proof Sufficiency (0-10)**
- Is there enough proof to believe the claims?
- Is the proof specific and verifiable?
- Score: [0-10]

**6. Offer Value (0-10)**
- Does the offer feel worth more than the price?
- Is the value stack compelling?
- Score: [0-10]

**7. Risk Reversal (0-10)**
- Is there a guarantee?
- Does it remove purchase fear effectively?
- Score: [0-10]

**8. CTA Strength (0-10)**
- Is the CTA clear and action-oriented?
- Does it appear at the right moments?
- Score: [0-10]

**9. Urgency/Motivation (0-10)**
- Is there a reason to act now?
- Is the urgency real or manufactured?
- Score: [0-10]

**10. Trust Signals (0-10)**
- Are there trust indicators (logos, certifications, guarantees)?
- Does the page feel credible?
- Score: [0-10]

**11. Mobile Experience (0-10)**
- Does it work on mobile devices?
- Are CTAs thumb-friendly?
- Score: [0-10]

**12. Load Speed (0-10)**
- Does it load within 3 seconds?
- Are there excessive scripts/images?
- Score: [0-10]

### Scoring Interpretation

```
90-120: Optimized - Focus on testing variations
70-89:  Good - Address 3-5 lowest scores
50-69:  Needs Work - Major gaps in conversion framework
 Below 50: Rebuild - Fundamental conversion elements missing
```

### Report Format

```
## CONVERSION AUDIT REPORT

**Asset:** [Name/URL]
**Date:** [Date]
**Overall Score:** [X]/120

### Critical Issues (Score < 5)
1. [Issue] - Score: [X]/10
   Current: [What exists]
   Problem: [Why it's failing]
   Fix: [Specific recommendation]

### Opportunities (Score 5-7)
1. [Opportunity] - Score: [X]/10
   Current: [What exists]
   Improvement: [Specific recommendation]

### Strengths (Score 8+)
1. [Strength] - Score: [X]/10
   What's working: [Description]

### Priority Action Plan
1. [Highest impact fix]
2. [Second priority]
3. [Third priority]
```

---

## COMPETITIVE INTELLIGENCE PROTOCOL

### Purpose
Gather actionable competitive intelligence to inform positioning and differentiation.

### Research Sequence

**Step 1: Identify Competitors**
```
Search: "[product category] best [year]"
Search: "[business name] alternatives"
Search: "[primary keyword] software/service/product"

Identify top 3-5 direct competitors
```

**Step 2: Analyze Each Competitor**

For each competitor, extract:
```
- Positioning statement (how they describe themselves)
- Primary audience
- Core offer structure
- Price point (if visible)
- Key claims and promises
- Social proof (numbers, logos, testimonials)
- Unique mechanisms (proprietary methods)
- Weaknesses (what they don't offer)
- Marketing channels visible
```

**Step 3: Gap Analysis**
```
Categories to analyze:
1. Price positioning (premium, mid, budget)
2. Audience specificity (broad vs. niche)
3. Service model (DIY, DWY, DFY)
4. Proof type (results, process, credentials)
5. Risk reversal (guarantee type and strength)
6. Speed claims (how quickly results promised)
```

**Step 4: Differentiation Opportunities**
```
For each gap identified:
- What do all competitors do?
- What does none of them do?
- What could be done better?
- What positioning is unclaimed?
```

### Output Format

```
## COMPETITIVE INTELLIGENCE BRIEF

**Market:** [Category]
**Date:** [Date]

### Competitor Profiles

**[Competitor 1]**
- Positioning: [One sentence]
- Audience: [Who they target]
- Offer: [What they sell and at what price]
- Strengths: [2-3 bullets]
- Weaknesses: [2-3 bullets]

### Market Gaps
1. [Gap 1] - [Opportunity]
2. [Gap 2] - [Opportunity]
3. [Gap 3] - [Opportunity]

### Recommended Positioning
[Statement of differentiation based on gaps]

### Messaging Angles to Avoid
[What's already saturated in the market]

### Messaging Angles to Pursue
[What's differentiated and defensible]
```

---

## LANDING PAGE PROTOCOL

### Purpose
Standardized framework for building any high-conversion landing page.

### Above-the-Fold Requirements

```
Must include ALL of these:
1. Headline (primary benefit/transformation)
2. Subheadline (clarify + amplify headline)
3. Hero image/video (show transformation or product)
4. Primary CTA button (action-oriented copy)
5. Trust signal (logo, stat, or social proof)
```

### Page Section Sequence

```
1. HERO SECTION
   - Headline
   - Subheadline
   - CTA
   - Trust element

2. PROBLEM SECTION
   - Pain identification
   - Agitation (what happens if not solved)
   - Bridge to solution

3. SOLUTION SECTION
   - Product/service introduction
   - How it works (3-step process)
   - Key features as benefits

4. PROOF SECTION
   - Testimonials (3-5 minimum)
   - Case studies (if available)
   - Social proof numbers
   - Authority logos

5. OFFER SECTION
   - Value stack
   - Price (with anchor)
   - Guarantee
   - CTA

6. FAQ SECTION
   - Top 5-7 objections as questions
   - Overcome each directly

7. FINAL CTA
   - Urgency element
   - Restate primary benefit
   - CTA button
```

### Technical Requirements

```
Code:
- Single HTML file
- Inline CSS only
- Inline JavaScript only
- No external dependencies

Performance:
- Load under 3 seconds
- Mobile responsive (320px minimum)
- Touch targets minimum 44x44px
- Font size 16px+ for body text

Functionality:
- All CTAs link to correct destination
- Forms validate before submission
- Mobile navigation functional
```

### Headline Formulas

```
Transformation: "[Verb] [Result] Without [Pain/Obstacle]"
Example: "Double Your Leads Without Doubling Your Ad Spend"

Number: "[Number] Ways to [Result] in [Timeframe]"
Example: "7 Ways to Cut Your CPA in Half This Month"

Question: "[Frustration Question]?"
Example: "Tired of Watching Your Ad Budget Disappear?"

How To: "How to [Result] Even If [Obstacle]"
Example: "How to Run Profitable Ads Even If You've Failed Before"

If-Then: "If You [Situation], Then [Product] Can [Result]"
Example: "If You're Spending $5K+/Month on Ads, Unicorn Can Double Your ROAS"
```

---

## AD CREATIVE PROTOCOL

### Purpose
Framework for creating Meta/Google ad creative that stops the scroll and drives action.

### The Scroll-Stop Framework

**First 3 Seconds (Video) or Visual (Static):**
- Pattern interrupt (unexpected visual or statement)
- Immediate identification of target audience
- Open loop that demands resolution

### Hook Categories by Awareness Level

```
UNAWARE AUDIENCE:
- Lead with entertainment/curiosity
- Avoid product mention in first 5 seconds
- Build problem awareness first

PROBLEM-AWARE:
- Open with pain identification
- "If you're struggling with [X]..."
- Agitate before presenting solution

SOLUTION-AWARE:
- Compare mechanism
- "Unlike [category], our [product] [unique mechanism]"
- Lead with differentiation

PRODUCT-AWARE:
- Overcome objections
- Reinforce with social proof
- Create urgency

MOST AWARE:
- Direct offer
- "[X% off] ends [date]"
- Remind of value already communicated
```

### Ad Copy Structure

```
Hook (first line):
[Pattern interrupt + audience identification]

Body:
[Problem agitation or benefit amplification]
[Proof element]
[Mechanism explanation]

CTA:
[Specific action + benefit]
"Click below to [specific result]"
```

### Visual Requirements

```
Static Ads:
- 1080x1080 (Feed)
- 1080x1920 (Stories/Reels)
- 1200x628 (Link Ads)

Text overlay: Maximum 20% of image
Face/person: Higher CTR than product-only
Contrast: High enough for small screens

Video Ads:
- Square (1:1) or Vertical (9:16) preferred
- Captions required (85% watch muted)
- Hook in first 3 seconds
- CTA in final 5 seconds
```

---

## FOLLOW-UP SEQUENCE PROTOCOL

### Purpose
Framework for building email/SMS follow-up sequences that nurture leads to conversion.

### Sequence Architecture

```
Email 1 (Immediate): Deliver promised value
Email 2 (Day 2): Education + soft CTA
Email 3 (Day 4): Social proof + case study
Email 4 (Day 6): Objection handling
Email 5 (Day 8): Urgency + strong CTA
Email 6 (Day 11): Last chance / reframe
Email 7 (Day 14): Re-engagement attempt
```

### Each Email Structure

```
Subject Line: [Curiosity gap or direct benefit]
Preview Text: [Amplify subject line]

Opening Hook (1-2 sentences):
- Continue story from previous email OR
- Open new curiosity loop

Body (3-5 paragraphs):
- Deliver value or advance the story
- Include one proof element per email
- Answer one objection per email

CTA:
- One clear call to action per email
- Match CTA to where they are in sequence
  (Early: soft / Middle: medium / Late: urgent)

PS Line:
- Reinforce CTA
- Add urgency element
- Personal touch
```

### Subject Line Formulas

```
Curiosity: "The [unexpected thing] that [result]"
Benefit: "How to [result] in [timeframe]"
Question: "Are you making this [mistake]?"
Number: "[X] things that [result]"
Personalization: "[Name], about your [thing]"
Direct: "[Offer] expires [when]"
```

### Deliverability Rules

```
AVOID (spam triggers):
- ALL CAPS in subject line
- Excessive exclamation points
- "Free", "Guaranteed", "No risk"
- Dollar signs in subject
- Deceptive preview text

INCLUDE (trust signals):
- Physical address in footer
- Unsubscribe link
- Company name clearly visible
- Reply-to address that works
```

### Performance Benchmarks

```
Email 1 (Welcome): Open 40-60%, Click 10-20%
Email 2-4 (Nurture): Open 25-35%, Click 5-10%
Email 5-6 (Offer): Open 20-30%, Click 8-15%
Email 7 (Re-engage): Open 15-25%, Click 3-8%

Below benchmark? Review:
- Subject lines (open rate issue)
- CTA clarity (click rate issue)
- Audience match (both issues)
```