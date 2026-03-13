# HTML Standards for Landing Pages

## Architecture Rules (Non-Negotiable)
1. **Single HTML file** — ALL CSS in one `<style>` block in `<head>`, ALL JS in one `<script>` block before `</body>`
2. **No external frameworks** — No Bootstrap, Tailwind, React, jQuery, or any CDN dependencies
3. **No external stylesheets** — No `<link rel="stylesheet">` to external files
4. **No external scripts** — No `<script src="">` to external files (except Google Fonts)
5. **Vanilla JS only** — Use native APIs: IntersectionObserver, requestAnimationFrame, classList
6. **CSS Custom Properties** — All colors, fonts, and spacing defined as `:root` variables
7. **Mobile-first** — Write mobile styles first, use `@media (min-width:)` for larger screens

## CSS Architecture
```css
/* 1. Variables */
:root {
  --primary: #...;
  --accent: #...;
  --bg: #...;
  --text: #...;
  --text-light: #...;
  --border: #...;
  --font-heading: '...', serif;
  --font-body: '...', sans-serif;
}

/* 2. Reset */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

/* 3. Base styles */
body { font-family: var(--font-body); color: var(--text); }

/* 4. Component styles */
/* 5. Responsive overrides */
```

## JavaScript Patterns
Standard JS features to include (pick relevant ones per page):

```javascript
// 1. Scroll Progress Bar
window.addEventListener('scroll', () => {
  const progress = (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100;
  document.getElementById('scrollProgress').style.width = progress + '%';
});

// 2. Scroll Reveal (IntersectionObserver)
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// 3. Sticky CTA (appears after hero)
// 4. Counter animation for statistics
// 5. Nav scroll effect (add .scrolled class)
```

## CSS Lessons (from memory/glossary.md)
- **NEVER** use `section:nth-child(odd/even)` for backgrounds alongside class-based styling — specificity conflict causes white text on white backgrounds
- **ALWAYS** verify text contrast on dark sections with explicit color declarations
- **ALWAYS** use explicit classes (`.section-dark`, `.section-light`) on every section

## Required Meta Tags
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{Descriptive Title}</title>
<meta name="description" content="{compelling description}">
<meta property="og:title" content="{title}">
<meta property="og:description" content="{description}">
<meta property="og:image" content="{image URL}">
<meta property="og:type" content="website">
```

## Asset Organization
```
{project}/
├── index.html
└── assets/
    ├── images/
    │   ├── hero.jpg
    │   ├── logo.png
    │   └── ...
    └── ads/ (if applicable)
        ├── creative-1.png
        └── ...
```

## Image Guidelines
- Use WebP or AVIF where possible, JPEG for photos, PNG for logos/transparency
- Hero images: 1200-1600px wide max
- Compress all images before committing
- Always set `alt` attributes
- Use `loading="lazy"` on below-fold images
