# Deployment Rules

## Branch Strategy
- Always work on a `claude/{project-name}` branch
- Never commit directly to `main`
- The auto-merge workflow handles deployment — pushing to `claude/**` auto-merges to `main`

## Commit Messages
Follow this format:
```
{Action} {client} {page-type} ({context})

- Brief description of what was built/changed
- Expert panel score: XX/100 (for new pages)
- QA status: All checks passed

Co-Authored-By: Claude <noreply@anthropic.com>
```

Examples:
```
Add yousmle advertorial landing page

- Publication-style advertorial for USMLE exam prep
- Expert panel score: 94/100
- All QA checks passed
```

```
Add yousmle ad images (automated pipeline)

12 ads across 6 styles (2 each): photoshoot, minimal, typography, story, dr, creative
All QA passed 12/12.
```

## File Structure Per Project
```
{client-name}/
├── advertorial/
│   ├── index.html
│   └── assets/
│       └── images/
├── listicle/
│   ├── index.html
│   └── assets/
├── quiz/
│   ├── index.html
│   ├── quiz.html
│   ├── results.html
│   └── assets/
└── assets/
    ├── ads/
    ├── images/
    └── refs/
```

## Quality Gates
1. **Expert Review:** Must score 90+ average before deploy
2. **QA Review:** Must pass all checklist items before deploy  
3. **No deploy without both gates passing**

## Post-Deploy Verification
After push:
1. Wait 30-60 seconds for GitHub Pages to build
2. Verify the live URL loads correctly
3. Check mobile rendering
4. Report the live URL to the user
