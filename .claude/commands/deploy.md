# Deploy to Production

Deploy a landing page to GitHub Pages after running the technical QA checklist.

## Target
Deploy: $ARGUMENTS (provide client/project name)

## Pre-Deploy Checklist

Run through every item. Do NOT skip any.

### Content Checks
- [ ] No placeholder content remaining (search for "Lorem", "TODO", "{{", "placeholder", "example.com")
- [ ] All headlines are final copy (not draft)
- [ ] All testimonials have proper attribution
- [ ] Disclaimer/sponsored content footer is present (for advertorials)
- [ ] CTA links point to correct destination (not "#")
- [ ] No em dashes (—) in copy — use en dashes (–) or rewrite

### Technical Checks
- [ ] `<meta name="viewport" content="width=device-width, initial-scale=1.0">` present
- [ ] `<title>` tag is descriptive (not "Untitled" or template default)
- [ ] `<meta name="description">` is set
- [ ] OG meta tags set (og:title, og:description, og:image)
- [ ] Favicon linked
- [ ] All CSS is inline (no external stylesheet links)
- [ ] All JS is inline (no external script links)
- [ ] No console errors when page loads
- [ ] All external URLs use https
- [ ] All images have alt attributes

### Performance Checks
- [ ] Images optimized (WebP where possible, compressed)
- [ ] Total page weight under 500KB (excluding large images/video)
- [ ] No unnecessary comments or debug code in production HTML

### Responsive Checks
- [ ] Tested at 375px (mobile)
- [ ] Tested at 768px (tablet)
- [ ] Tested at 1024px (small desktop)
- [ ] Tested at 1440px (desktop)
- [ ] No horizontal scrollbar at any breakpoint

## Deploy Steps

1. Verify all checks pass above
2. Create the project directory at repo root: `{client-name}/` or `{client-name}/{page-type}/`
3. Ensure `index.html` and `assets/` folder are in place
4. Create a new branch: `claude/{client-name}-{page-type}`
5. Commit with descriptive message:
   ```
   Add {client} {page-type} landing page
   
   - {brief description of the page}
   - Expert panel score: {score}/100
   - All QA checks passed
   ```
6. Push to remote — the auto-merge workflow will deploy to main automatically
7. Verify live URL: `https://{username}.github.io/{client-name}/{page-type}/`
8. Report the live URL to the user

## Deliverables
Provide to the user:
1. **Live URL** — the GitHub Pages URL
2. **Local preview path** — file:/// path for Chrome
3. **Expert panel score** — summary of the review
4. **Asset folder** — location of all assets for future edits
