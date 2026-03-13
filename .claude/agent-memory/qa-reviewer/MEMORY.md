# QA Reviewer Agent Memory

## Verified Data
*(This file stores verified brand data so the QA agent doesn't re-check known facts)*

## Common Patterns (Acceptable)
- CTA buttons with initial `href="#"` are OK if JavaScript overwrites them before display
- Testimonials using "Verified Buyer" attribution (no fake names/ages) is the correct pattern
- Sponsored content disclaimers in advertorial footers are required, not optional

## Common Issues to Watch For
- White text on white backgrounds (caused by CSS specificity conflicts)
- Em dashes (—) in copy — should be en dashes or rewritten
- Trailing periods on CTA button text
- External image URLs not using https
- Placeholder content left in production pages
