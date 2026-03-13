# Extract Brand Styles

Extract brand colors, fonts, and visual identity from a client's website.

## Target URL
$ARGUMENTS (provide the URL to extract from)

## Process

### Step 1: Try Live DOM Extraction
If Chrome DevTools / browser control is available:
1. Navigate to the target URL
2. Run the script from `_tools/brand-extractor.js` via the JavaScript console
3. Capture the JSON output

### Step 2: Fallback to Regex Extraction
If Chrome DevTools is not available:
1. WebFetch the target URL to get raw HTML
2. Apply the regex patterns from `_tools/brand-extractor-fallback.js`:
   - Extract CSS custom properties from `:root`
   - Extract all hex color values (deduplicate, rank by frequency)
   - Extract Google Fonts links
   - Extract font-family declarations
   - Extract background-color values
   - Extract button/CTA styles
   - Extract gradient values
   - Extract border-radius values
   - Extract box-shadow values

### Step 3: Save Brand Profile
1. Use `_tools/brand-style-template.md` as the output format
2. Fill in all extracted values
3. Save to `memory/clients/{client}.md`

### Step 4: Report
Show the user:
- Primary colors (with hex swatches description)
- Typography (heading font, body font, weights)
- Button styles
- CSS variables ready for copy-paste
- Any Google Fonts import tags needed
