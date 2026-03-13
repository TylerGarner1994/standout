# Create a New Landing Page

Create a world-class, psychology-driven landing page for a client.

## Input Required
- **Client/Offer URL:** $ARGUMENTS (or provide a detailed description)
- **Page type:** advertorial | listicle | vsl | simple-sales | quiz

## Workflow

### Phase 1: Discovery & Research
1. **WebFetch** the offer URL to understand current positioning
2. Extract key offer elements: price, deliverables, guarantees, bonuses
3. Identify the core transformation/outcome promise
4. Note any urgency elements or scarcity
5. **Run brand extraction** — use `_tools/brand-extractor.js` via Chrome DevTools or `_tools/brand-extractor-fallback.js` on the raw HTML
6. Save extracted brand to `memory/clients/{client}.md` using `_tools/brand-style-template.md`
7. **ICP Deep Dive** — Research the Ideal Customer Profile:
   - Demographics: Age, income, profession, location
   - Psychographics: Values, beliefs, aspirations, fears
   - Current state: Pain points, frustrations, failed solutions
   - Desired state: Goals, dreams, what success looks like
   - Objections: Why they might NOT buy
   - Triggers: What would make them buy TODAY

### Phase 2: Psychology-Driven Copy
Using the appropriate template from `_templates/`, create the page applying:

**System 1 Triggers (Emotional):**
- Visual hierarchy, social proof, authority, scarcity, urgency, reciprocity, liking

**System 2 Triggers (Rational):**
- ROI calculation, feature comparison, risk reversal, specificity, logic flow, objection handling

**Neuromarketing:**
- Pattern interrupts, contrast, faces pointing toward CTA, rule of 3, loss aversion, anchoring

**NLP Patterns:**
- Presuppositions, embedded commands, future pacing, sensory language, cause-effect

**Behavioral Economics:**
- Anchoring, loss aversion, endowment effect, sunk cost, social proof, commitment/consistency, peak-end rule

### Phase 3: Expert Review
Run `/review` on the completed page. Must score 90+ to proceed.

### Phase 4: Deploy
Run `/deploy` to push the page live.

## Technical Requirements
- Single self-contained HTML file with inline CSS and JS
- No external frameworks or CDN dependencies
- Mobile-first responsive design
- All assets in relative `assets/` folder
- CSS custom properties for theming
- Vanilla JS only (IntersectionObserver, scroll effects)
