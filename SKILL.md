---
name: frontend-slides
description: Create data-focused HTML presentations for Dezerv clients. Swiss Modern style optimized for portfolio reviews and financial data visualization.
---

# Frontend Slides Skill — Dezerv Edition

Create zero-dependency, animation-rich HTML presentations optimized for portfolio reviews and financial data visualization. This skill uses Swiss Modern design with data-focused components, number animations, and consistent Dezerv branding.

## Core Philosophy

1. **Zero Dependencies** — Single HTML files with inline CSS/JS. No npm, no build tools.
2. **Data-Focused Design** — Swiss Modern variant optimized for portfolio data, charts, and financial metrics.
3. **Dezerv Branding** — Every presentation features the Dezerv logo (SVG) prominently on title slide and in content slide headers.
4. **Animated Numbers** — Data values animate from 0 to target with smooth easing for visual impact.
5. **Viewport Fitting (CRITICAL)** — Every slide MUST fit exactly within the viewport. No scrolling within slides, ever.

---

## Typography

**Font:** Inter (display + body) from Google Fonts

Inter is a highly legible typeface designed for screens, perfect for data-heavy financial presentations. Use heavier weights (700-900) for headings and lighter weights (400-500) for body text.

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
```

```css
:root {
    --font-display: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    --font-body: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    
    --title-size: clamp(2.5rem, 7vw, 5rem);
    --h2-size: clamp(1.5rem, 4vw, 2.5rem);
    --h3-size: clamp(1rem, 2vw, 1.5rem);
    --body-size: clamp(0.875rem, 1.2vw, 1.125rem);
    --small-size: clamp(0.75rem, 1vw, 0.875rem);
    --micro-size: clamp(0.625rem, 0.8vw, 0.75rem);
}
```

---

## Dezerv Logo Usage (MANDATORY)

**Every presentation MUST include the Dezerv logo according to these brand guidelines:**

### Logo Colors (Non-Negotiable)

The Dezerv logo may ONLY be used in these colors:
- **Black** (`#000000`) — Use on light backgrounds (default for Swiss Modern light theme)
- **White** (`#ffffff`) — Use on dark backgrounds or colored sections

**Never use the logo in any other color.**

---

## Complete Color System

### Required CSS Variables

Include this complete color system in every presentation:

```css
:root {
    /* ===========================================
       BACKGROUNDS
       =========================================== */
    --bg-primary: #FAFAFA;        /* Content slide background */
    --bg-secondary: #f8f9fa;
    --bg-dark: #0d0d0d;           /* Title/End slides - dark */
    --bg-card: #FDFDFC;           /* Card background */
    --border-card: rgba(29, 27, 24, 0.08);  /* Card border */
    
    /* ===========================================
       TEXT COLORS
       =========================================== */
    --text-primary: #0d0d0d;
    --text-secondary: #495057;
    --text-muted: #868e96;
    --text-light: #adb5bd;
    
    /* ===========================================
       MONOCHROMATIC DATA SCALE
       For charts, bars, and data visualization
       =========================================== */
    --data-1: #0d0d0d;   /* Darkest - primary data */
    --data-2: #343a40;
    --data-3: #495057;   /* Mid-tone */
    --data-4: #868e96;
    --data-5: #adb5bd;   /* Light */
    --data-6: #dee2e6;   /* Lightest */
    
    /* ===========================================
       DEZERV SEMANTIC COLORS
       For portfolio performance indicators
       =========================================== */
    --color-positive: #23625E;  /* Green - gains, growth */
    --color-negative: #AB2626;  /* Red - losses, decline */
    --color-warning: #B1511D;   /* Orange - info, caution */
    
    /* ===========================================
       ACCENT (use sparingly)
       =========================================== */
    --accent: #e03131;          /* Swiss red - highlights only */
    --accent-light: #fff5f5;
}
```

### Semantic Color Usage

| Color | Variable | Usage |
|-------|----------|-------|
| **Dezerv Green** | `--color-positive` | Portfolio gains, growth, success (+12.5%, ₹2.4L profit) |
| **Dezerv Red** | `--color-negative` | Portfolio losses, decline, errors (-8.2%, ₹50K loss) |
| **Dezerv Orange** | `--color-warning` | Info, warnings, pending status |

### Data Scale Usage

Use the monochromatic `--data-1` through `--data-6` scale for:
- Stacked bar chart segments
- Donut/pie chart slices
- Allocation tables
- Legend items

### Utility Classes for Data Representation

Include these utility classes for easy color application:

```css
/* ===========================================
   SEMANTIC COLOR UTILITIES
   Use for portfolio data and status indicators
   =========================================== */

/* Positive (gains, success, growth) */
.positive, .gain, .up {
    color: var(--color-positive);
}

.bg-positive {
    background-color: var(--color-positive);
    color: var(--text-primary-inverse);
}

/* Negative (losses, errors, decline) */
.negative, .loss, .down {
    color: var(--color-negative);
}

.bg-negative {
    background-color: var(--color-negative);
    color: var(--text-primary-inverse);
}

/* Warning/Info (caution, pending, neutral) */
.warning, .info, .pending {
    color: var(--color-warning);
}

.bg-warning {
    background-color: var(--color-warning);
    color: var(--text-primary-inverse);
}
```

### Text Color Rules (CRITICAL for Legibility)

**Text color restrictions to ensure readability:**

| Text Color | Allowed Backgrounds |
|------------|---------------------|
| Black (`--text-primary`) | Light backgrounds only |
| White (`#ffffff`) | Dark or colored backgrounds only |
| Light gray (`--text-muted`, `--text-light`) | **Pure white (#FFFFFF) background ONLY** |
| Semantic colors (green, red, orange) | Light backgrounds only (`--bg-card`, `--bg-primary`) |

| Background Type | Allowed Text Colors |
|-----------------|---------------------|
| Pure white (`#FFFFFF`) | Any: black, gray, green, red, orange |
| Light (`--bg-primary`, `--bg-card`) | Black, dark gray, green, red, orange — **NO light gray** |
| Dark (`--bg-dark`, black) | **White ONLY** |
| Accent (`--accent`, green) | **White ONLY** |
| Colored backgrounds (`--color-positive`, etc.) | **White ONLY** |

**Never use:**
- `.positive`, `.negative`, `.warning` text on `.data-card.dark` or `.data-card.accent`
- Light gray text (`--text-muted`, `--text-light`) on any background except pure white
- Green/red/orange text on any dark or colored background

```css
/* Data value styling */
.data-value {
    font-family: var(--font-display);
    font-weight: 700;
}

.data-value.positive::before {
    content: '+';
}

.data-value.negative::before {
    content: '';  /* Negative sign included in value */
}
```

### Example Usage in HTML

```html
<!-- Portfolio performance -->
<div class="metric">
    <span class="label">Total Returns</span>
    <span class="data-value positive">+24.5%</span>
</div>

<div class="metric">
    <span class="label">This Month</span>
    <span class="data-value negative">-2.1%</span>
</div>

<!-- Status indicators -->
<span class="positive">● Invested</span>
<span class="warning">● Pending</span>
<span class="negative">● Withdrawn</span>

<!-- Comparison table -->
<table>
    <tr>
        <td>Equity</td>
        <td class="positive">+18.2%</td>
    </tr>
    <tr>
        <td>Debt</td>
        <td class="negative">-1.5%</td>
    </tr>
</table>
```

### Logo Placement

**Title Slide (First Slide):**
- Display the Dezerv logo prominently
- Position: Top-left corner OR centered above the main heading
- Size: `width: clamp(100px, 15vw, 180px)` — visible but not overwhelming

**All Other Slides:**
- Display the Dezerv logo subtly as a watermark
- Position: Bottom-right corner (fixed position)
- Size: `width: clamp(60px, 8vw, 100px)` — subtle but visible
- Opacity: 0.6–0.8 for subtle presence

### Dezerv Logo SVG (Inline)

Include this SVG inline in every presentation. Use CSS `fill` to control color.

**Black version (for light backgrounds):**
```html
<!-- Dezerv Logo - Black (use on light backgrounds) -->
<svg class="dezerv-logo" viewBox="0 0 128 32" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path fill-rule="evenodd" clip-rule="evenodd" d="M13.5913 6.3999C19.5734 6.40001 23.1999 10.1524 23.1999 15.9999C23.1999 21.8474 19.5734 25.5998 13.5913 25.5999H6.3999V6.3999H13.5913ZM11.2976 10.7155V21.253H13.3429C16.5045 21.253 18.2718 19.2207 18.2718 15.9999C18.2718 12.7478 16.5045 10.7155 13.3429 10.7155H11.2976Z" fill="#000000"/>
    <path d="M41.1999 10.7155H32.7507V13.7171H40.478V17.939H32.7507V21.253H41.1999V25.5999H27.9999V6.3999H41.1999V10.7155Z" fill="#000000"/>
    <path d="M61.5046 10.0897L52.5819 21.253H61.5999V25.5999H45.9999V21.8788L55.0179 10.7155H46.0952V6.3999H61.5046V10.0897Z" fill="#000000"/>
    <path d="M79.5999 10.7155H71.1507V13.7171H78.878V17.939H71.1507V21.253H79.5999V25.5999H66.3999V6.3999H79.5999V10.7155Z" fill="#000000"/>
    <path fill-rule="evenodd" clip-rule="evenodd" d="M92.664 6.3999C96.6163 6.3999 99.3412 8.74505 99.3413 12.9351C99.3413 15.8432 97.9338 17.8446 95.6882 18.7202L99.9999 25.5999H94.6702L90.8374 19.2522H89.1608V25.5999H84.3999V6.3999H92.664ZM89.1608 15.2491H92.1554C93.8618 15.249 94.6405 14.3421 94.6405 12.9351C94.6404 11.5282 93.8617 10.6219 92.1554 10.6218H89.1608V15.2491Z" fill="#000000"/>
    <path d="M112.109 18.814L116.448 6.3999H121.6L114.451 25.5999H109.549L102.4 6.3999H107.769L112.109 18.814Z" fill="#000000"/>
</svg>
```

**White version (for dark backgrounds):**
```html
<!-- Dezerv Logo - White (use on dark backgrounds) -->
<svg class="dezerv-logo" viewBox="0 0 128 32" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path fill-rule="evenodd" clip-rule="evenodd" d="M13.5913 6.3999C19.5734 6.40001 23.1999 10.1524 23.1999 15.9999C23.1999 21.8474 19.5734 25.5998 13.5913 25.5999H6.3999V6.3999H13.5913ZM11.2976 10.7155V21.253H13.3429C16.5045 21.253 18.2718 19.2207 18.2718 15.9999C18.2718 12.7478 16.5045 10.7155 13.3429 10.7155H11.2976Z" fill="#ffffff"/>
    <path d="M41.1999 10.7155H32.7507V13.7171H40.478V17.939H32.7507V21.253H41.1999V25.5999H27.9999V6.3999H41.1999V10.7155Z" fill="#ffffff"/>
    <path d="M61.5046 10.0897L52.5819 21.253H61.5999V25.5999H45.9999V21.8788L55.0179 10.7155H46.0952V6.3999H61.5046V10.0897Z" fill="#ffffff"/>
    <path d="M79.5999 10.7155H71.1507V13.7171H78.878V17.939H71.1507V21.253H79.5999V25.5999H66.3999V6.3999H79.5999V10.7155Z" fill="#ffffff"/>
    <path fill-rule="evenodd" clip-rule="evenodd" d="M92.664 6.3999C96.6163 6.3999 99.3412 8.74505 99.3413 12.9351C99.3413 15.8432 97.9338 17.8446 95.6882 18.7202L99.9999 25.5999H94.6702L90.8374 19.2522H89.1608V25.5999H84.3999V6.3999H92.664ZM89.1608 15.2491H92.1554C93.8618 15.249 94.6405 14.3421 94.6405 12.9351C94.6404 11.5282 93.8617 10.6219 92.1554 10.6218H89.1608V15.2491Z" fill="#ffffff"/>
    <path d="M112.109 18.814L116.448 6.3999H121.6L114.451 25.5999H109.549L102.4 6.3999H107.769L112.109 18.814Z" fill="#ffffff"/>
</svg>
```

### Required Logo CSS

Include this CSS in every presentation:

```css
/* ===========================================
   DEZERV LOGO STYLES
   Consistent branding across all slides
   =========================================== */

/* Base logo styling */
.dezerv-logo {
    display: block;
    height: auto;
}

/* Title slide: Prominent logo */
.title-slide .dezerv-logo {
    width: clamp(100px, 15vw, 180px);
    margin-bottom: var(--content-gap);
}

/* All other slides: Subtle watermark in corner */
.dezerv-logo-watermark {
    position: fixed;
    bottom: clamp(1rem, 3vw, 2rem);
    right: clamp(1rem, 3vw, 2rem);
    width: clamp(60px, 8vw, 100px);
    opacity: 0.7;
    z-index: 50;
    pointer-events: none;
}

/* Hide watermark on very short screens */
@media (max-height: 500px) {
    .dezerv-logo-watermark {
        display: none;
    }
}
```

### HTML Structure with Logo

**Title Slide:**
```html
<section class="slide title-slide">
    <div class="slide-content">
        <!-- Prominent Dezerv logo -->
        <svg class="dezerv-logo reveal" viewBox="0 0 128 32" ...>
            <!-- Black logo paths -->
        </svg>
        
        <h1 class="reveal">Presentation Title</h1>
        <p class="subtitle reveal">Subtitle or tagline</p>
    </div>
</section>
```

**Global Watermark (outside slides, fixed position):**
```html
<body>
    <!-- Dezerv watermark - appears on all slides -->
    <svg class="dezerv-logo-watermark" viewBox="0 0 128 32" ...>
        <!-- Black logo paths -->
    </svg>
    
    <!-- Slides -->
    <section class="slide title-slide">...</section>
    <section class="slide">...</section>
</body>
```

---

## Icon Usage (Heroicons)

Use Heroicons (heroicons.com) to add visual context where it genuinely aids comprehension. Icons should clarify, not decorate.

### Philosophy: Less is More

Icons are powerful when used sparingly. A slide with zero icons is perfectly fine. A slide with 10 icons is visual noise.

### When to Use Icons

| Context | Example | Icon Suggestion |
|---------|---------|-----------------|
| Data card labels | "Total Portfolio" | `banknotes` or `wallet` |
| Positive indicators | Gains, growth | `arrow-trending-up` |
| Negative indicators | Losses, decline | `arrow-trending-down` |
| Key highlights | Important callout | `check-circle` |
| Warnings/cautions | Risk note | `exclamation-triangle` |
| Section headers | Strategy section | `chart-pie` |
| Contact/CTA | "Get in touch" | `phone` or `envelope` |

### When NOT to Use Icons

- Every data card (pick 1-2 key metrics only)
- Every bullet point (use for emphasis only)
- Purely decorative purposes
- When the label is already clear
- In data values or percentages

### Limits per Slide

| Slide Type | Maximum Icons |
|------------|---------------|
| Title slide | 0-1 (optional decorative) |
| Data overview | 2-4 icons |
| Content slide | 2-3 icons |
| Summary slide | 3-5 icons |
| End slide | 0-1 icons |

### Icon Styling

Icons should be subtle, not attention-grabbing. Include this CSS in every presentation:

```css
/* ===========================================
   ICON STYLES (Heroicons)
   =========================================== */
.icon {
    width: 1.25em;
    height: 1.25em;
    vertical-align: -0.2em;
    flex-shrink: 0;
    display: inline-block;
}

/* Size variants */
.icon-sm { width: 1em; height: 1em; }
.icon-lg { width: 1.5em; height: 1.5em; }
.icon-xl { width: 2em; height: 2em; }

/* Color: inherit from parent or use semantic colors */
.icon { color: currentColor; }
.icon-muted { color: var(--text-muted); }
.icon-positive { color: var(--color-positive); }
.icon-negative { color: var(--color-negative); }
.icon-warning { color: var(--color-warning); }

/* ===========================================
   DATA LABEL ROW (Icon + Label Container)
   IMPORTANT: Always use this wrapper for icons in data cards
   =========================================== */
.data-label-row {
    display: flex;
    align-items: center;
    gap: 0.35rem;
}

.data-label-row .icon {
    width: 0.875rem;
    height: 0.875rem;
    flex-shrink: 0;
    opacity: 0.85;
}

.data-label-row .data-label {
    margin: 0;
}
```

> **Warning**: Never embed icons directly inside `.data-label` spans. The `text-transform: uppercase` property causes icon sizing issues and can break layouts. Always use `.data-label-row` as a wrapper container.

### Common Heroicons for Financial Presentations

**Portfolio & Finance:**
- `banknotes` - Total value, AUM
- `wallet` - Holdings, accounts
- `currency-rupee` - Currency amounts
- `credit-card` - Payments
- `calculator` - Projections
- `scale` - Balance, comparison

**Performance & Charts:**
- `arrow-trending-up` - Growth, gains
- `arrow-trending-down` - Decline, losses
- `chart-bar` - Performance charts
- `chart-pie` - Allocation
- `presentation-chart-line` - Projections

**Status & Indicators:**
- `check-circle` - Success, complete
- `x-circle` - Failed, negative
- `exclamation-triangle` - Warning, caution
- `information-circle` - Info, note
- `shield-check` - Secure, protected

**Time & People:**
- `clock` - Time, duration
- `calendar` - Dates, schedule
- `users` - Family, clients
- `building-office` - Institutions

**Actions & Navigation:**
- `arrow-right` - Next, proceed
- `phone` - Contact
- `envelope` - Email

> **Need a different icon?** Visit heroicons.com, search for any icon, copy the outline SVG (24x24), add `class="icon"`, and embed inline.

### HTML Usage Examples

```html
<!-- Data card with icon using .data-label-row wrapper (RECOMMENDED) -->
<div class="data-card">
    <div class="data-label-row">
        <svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 18.75a60.07 60.07 0 0 1 15.797 2.101c.727.198 1.453-.342 1.453-1.096V18.75M3.75 4.5v.75A.75.75 0 0 1 3 6h-.75m0 0v-.375c0-.621.504-1.125 1.125-1.125H20.25M2.25 6v9m18-10.5v.75c0 .414.336.75.75.75h.75m-1.5-1.5h.375c.621 0 1.125.504 1.125 1.125v9.75c0 .621-.504 1.125-1.125 1.125h-.375m1.5-1.5H21a.75.75 0 0 0-.75.75v.75m0 0H3.75m0 0h-.375a1.125 1.125 0 0 1-1.125-1.125V15m1.5 1.5v-.75A.75.75 0 0 0 3 15h-.75M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Zm3 0h.008v.008H18V10.5Zm-12 0h.008v.008H6V10.5Z" />
        </svg>
        <span class="data-label">Total Portfolio</span>
    </div>
    <span class="data-value">₹7.93Cr</span>
</div>

<!-- Highlight list item with icon -->
<li style="display: flex; align-items: flex-start; gap: 0.5rem;">
    <svg class="icon icon-positive" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
    </svg>
    <span>91.5% equity allocation for growth</span>
</li>

<!-- Section header with icon -->
<h3 style="display: flex; align-items: center; gap: 0.5rem;">
    <svg class="icon icon-positive icon-lg" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
    </svg>
    Key Highlights
</h3>

<!-- Performance indicator with trending icon -->
<span class="positive" style="display: inline-flex; align-items: center; gap: 0.25rem;">
    <svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 18 9 11.25l4.306 4.306a11.95 11.95 0 0 1 5.814-5.518l2.74-1.22m0 0-5.94-2.281m5.94 2.28-2.28 5.941" />
    </svg>
    +24.5%
</span>
```

### Curated Heroicons SVG Reference

Copy these inline SVGs directly. Add `class="icon"` (already included) for proper styling.

**Portfolio & Finance:**

```html
<!-- banknotes - AUM, portfolio value -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 18.75a60.07 60.07 0 0 1 15.797 2.101c.727.198 1.453-.342 1.453-1.096V18.75M3.75 4.5v.75A.75.75 0 0 1 3 6h-.75m0 0v-.375c0-.621.504-1.125 1.125-1.125H20.25M2.25 6v9m18-10.5v.75c0 .414.336.75.75.75h.75m-1.5-1.5h.375c.621 0 1.125.504 1.125 1.125v9.75c0 .621-.504 1.125-1.125 1.125h-.375m1.5-1.5H21a.75.75 0 0 0-.75.75v.75m0 0H3.75m0 0h-.375a1.125 1.125 0 0 1-1.125-1.125V15m1.5 1.5v-.75A.75.75 0 0 0 3 15h-.75M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Zm3 0h.008v.008H18V10.5Zm-12 0h.008v.008H6V10.5Z" />
</svg>

<!-- wallet - Holdings, accounts -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M21 12a2.25 2.25 0 0 0-2.25-2.25H15a3 3 0 1 1-6 0H5.25A2.25 2.25 0 0 0 3 12m18 0v6a2.25 2.25 0 0 1-2.25 2.25H5.25A2.25 2.25 0 0 1 3 18v-6m18 0V9M3 12V9m18 0a2.25 2.25 0 0 0-2.25-2.25H5.25A2.25 2.25 0 0 0 3 9m18 0V6a2.25 2.25 0 0 0-2.25-2.25H5.25A2.25 2.25 0 0 0 3 6v3" />
</svg>

<!-- currency-rupee - Currency amounts -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 8.25H9m6 3H9m3 6-3-3h1.5a3 3 0 1 0 0-6M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
</svg>

<!-- credit-card - Payments -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 8.25h19.5M2.25 9h19.5m-16.5 5.25h6m-6 2.25h3m-3.75 3h15a2.25 2.25 0 0 0 2.25-2.25V6.75A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25v10.5A2.25 2.25 0 0 0 4.5 19.5Z" />
</svg>

<!-- calculator - Projections -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 15.75V18m-7.5-6.75h.008v.008H8.25v-.008Zm0 2.25h.008v.008H8.25V13.5Zm0 2.25h.008v.008H8.25v-.008Zm0 2.25h.008v.008H8.25V18Zm2.498-6.75h.007v.008h-.007v-.008Zm0 2.25h.007v.008h-.007V13.5Zm0 2.25h.007v.008h-.007v-.008Zm0 2.25h.007v.008h-.007V18Zm2.504-6.75h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V13.5Zm0 2.25h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V18Zm2.498-6.75h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V13.5ZM8.25 6h7.5v2.25h-7.5V6ZM12 2.25c-1.892 0-3.758.11-5.593.322C5.307 2.7 4.5 3.65 4.5 4.757V19.5a2.25 2.25 0 0 0 2.25 2.25h10.5a2.25 2.25 0 0 0 2.25-2.25V4.757c0-1.108-.806-2.057-1.907-2.185A48.507 48.507 0 0 0 12 2.25Z" />
</svg>

<!-- scale - Balance, comparison -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v17.25m0 0c-1.472 0-2.882.265-4.185.75M12 20.25c1.472 0 2.882.265 4.185.75M18.75 4.97A48.416 48.416 0 0 0 12 4.5c-2.291 0-4.545.16-6.75.47m13.5 0c1.01.143 2.01.317 3 .52m-3-.52 2.62 10.726c.122.499-.106 1.028-.589 1.202a5.988 5.988 0 0 1-2.031.352 5.988 5.988 0 0 1-2.031-.352c-.483-.174-.711-.703-.59-1.202L18.75 4.971Zm-16.5.52c.99-.203 1.99-.377 3-.52m0 0 2.62 10.726c.122.499-.106 1.028-.589 1.202a5.989 5.989 0 0 1-2.031.352 5.989 5.989 0 0 1-2.031-.352c-.483-.174-.711-.703-.59-1.202L5.25 4.971Z" />
</svg>
```

**Performance & Charts:**

```html
<!-- arrow-trending-up - Growth, gains -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 18 9 11.25l4.306 4.306a11.95 11.95 0 0 1 5.814-5.518l2.74-1.22m0 0-5.94-2.281m5.94 2.28-2.28 5.941" />
</svg>

<!-- arrow-trending-down - Decline, losses -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6 9 12.75l4.286-4.286a11.948 11.948 0 0 1 4.306 6.43l.776 2.898m0 0 3.182-5.511m-3.182 5.51-5.511-3.181" />
</svg>

<!-- chart-pie - Allocation -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M10.5 6a7.5 7.5 0 1 0 7.5 7.5h-7.5V6Z" />
  <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 10.5H21A7.5 7.5 0 0 0 13.5 3v7.5Z" />
</svg>

<!-- chart-bar - Performance charts -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M3 13.125C3 12.504 3.504 12 4.125 12h2.25c.621 0 1.125.504 1.125 1.125v6.75C7.5 20.496 6.996 21 6.375 21h-2.25A1.125 1.125 0 0 1 3 19.875v-6.75ZM9.75 8.625c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125v11.25c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 0 1-1.125-1.125V8.625ZM16.5 4.125c0-.621.504-1.125 1.125-1.125h2.25C20.496 3 21 3.504 21 4.125v15.75c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 0 1-1.125-1.125V4.125Z" />
</svg>

<!-- presentation-chart-line - Projections, trends -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 3v11.25A2.25 2.25 0 0 0 6 16.5h2.25M3.75 3h-1.5m1.5 0h16.5m0 0h1.5m-1.5 0v11.25A2.25 2.25 0 0 1 18 16.5h-2.25m-7.5 0h7.5m-7.5 0-1 3m8.5-3 1 3m0 0 .5 1.5m-.5-1.5h-9.5m0 0-.5 1.5m.75-9 3-3 2.148 2.148A12.061 12.061 0 0 1 16.5 7.605" />
</svg>

<!-- arrow-up - Increase -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 10.5 12 3m0 0 7.5 7.5M12 3v18" />
</svg>

<!-- arrow-down - Decrease -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 13.5 12 21m0 0-7.5-7.5M12 21V3" />
</svg>
```

**Status & Indicators:**

```html
<!-- check-circle - Success, complete -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
</svg>

<!-- x-circle - Failed, negative -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="m9.75 9.75 4.5 4.5m0-4.5-4.5 4.5M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
</svg>

<!-- exclamation-triangle - Warning, caution -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 9v3.75m-9.303 3.376c-.866 1.5.217 3.374 1.948 3.374h14.71c1.73 0 2.813-1.874 1.948-3.374L13.949 3.378c-.866-1.5-3.032-1.5-3.898 0L2.697 16.126ZM12 15.75h.007v.008H12v-.008Z" />
</svg>

<!-- exclamation-circle - Alert, attention -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 9v3.75m9-.75a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9 3.75h.008v.008H12v-.008Z" />
</svg>

<!-- information-circle - Info, note -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="m11.25 11.25.041-.02a.75.75 0 0 1 1.063.852l-.708 2.836a.75.75 0 0 0 1.063.853l.041-.021M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9-3.75h.008v.008H12V8.25Z" />
</svg>

<!-- shield-check - Secure, protected -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75m-3-7.036A11.959 11.959 0 0 1 3.598 6 11.99 11.99 0 0 0 3 9.749c0 5.592 3.824 10.29 9 11.623 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751h-.152c-3.196 0-6.1-1.248-8.25-3.285Z" />
</svg>
```

**Time & People:**

```html
<!-- clock - Time, duration -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
</svg>

<!-- calendar - Dates, schedule -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5" />
</svg>

<!-- calendar-days - Timeline -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5m-9-6h.008v.008H12v-.008ZM12 15h.008v.008H12V15Zm0 2.25h.008v.008H12v-.008ZM9.75 15h.008v.008H9.75V15Zm0 2.25h.008v.008H9.75v-.008ZM7.5 15h.008v.008H7.5V15Zm0 2.25h.008v.008H7.5v-.008Zm6.75-4.5h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V15Zm0 2.25h.008v.008h-.008v-.008Zm2.25-4.5h.008v.008H16.5v-.008Zm0 2.25h.008v.008H16.5V15Z" />
</svg>

<!-- users - Family, clients -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 19.128a9.38 9.38 0 0 0 2.625.372 9.337 9.337 0 0 0 4.121-.952 4.125 4.125 0 0 0-7.533-2.493M15 19.128v-.003c0-1.113-.285-2.16-.786-3.07M15 19.128v.106A12.318 12.318 0 0 1 8.624 21c-2.331 0-4.512-.645-6.374-1.766l-.001-.109a6.375 6.375 0 0 1 11.964-3.07M12 6.375a3.375 3.375 0 1 1-6.75 0 3.375 3.375 0 0 1 6.75 0Zm8.25 2.25a2.625 2.625 0 1 1-5.25 0 2.625 2.625 0 0 1 5.25 0Z" />
</svg>

<!-- user - Individual -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 6a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0ZM4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.933 17.933 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632Z" />
</svg>

<!-- building-office - Institutions -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 21h16.5M4.5 3h15M5.25 3v18m13.5-18v18M9 6.75h1.5m-1.5 3h1.5m-1.5 3h1.5m3-6H15m-1.5 3H15m-1.5 3H15M9 21v-3.375c0-.621.504-1.125 1.125-1.125h3.75c.621 0 1.125.504 1.125 1.125V21" />
</svg>

<!-- home - Home, residence -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
</svg>
```

**Actions & Navigation:**

```html
<!-- arrow-right - Next, proceed -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
</svg>

<!-- arrow-long-right - Flow, direction -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M17.25 8.25 21 12m0 0-3.75 3.75M21 12H3" />
</svg>

<!-- phone - Contact, call -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z" />
</svg>

<!-- envelope - Email, message -->
<svg class="icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75" />
</svg>
```

### Fetching Additional Icons

For any icon not in this curated set:

1. Visit **https://heroicons.com**
2. Search for the desired icon
3. Select **Outline** style (24x24) for consistency
4. Click to copy the SVG code
5. Add `class="icon"` to the `<svg>` element
6. Optionally add color class: `icon-muted`, `icon-positive`, `icon-negative`, `icon-warning`

---

## CRITICAL: Viewport Fitting Requirements

**This section is mandatory for ALL presentations. Every slide must be fully visible without scrolling on any screen size.**

### The Golden Rule

```
Each slide = exactly one viewport height (100vh/100dvh)
Content overflows? → Split into multiple slides or reduce content
Never scroll within a slide.
```

### Content Density Limits

To guarantee viewport fitting, enforce these limits per slide:

| Slide Type | Maximum Content |
|------------|-----------------|
| Title slide | 1 heading + 1 subtitle + optional tagline |
| Content slide | 1 heading + 4-6 bullet points OR 1 heading + 2 paragraphs |
| Feature grid | 1 heading + 6 cards maximum (2x3 or 3x2 grid) |
| Code slide | 1 heading + 8-10 lines of code maximum |
| Quote slide | 1 quote (max 3 lines) + attribution |
| Image slide | 1 heading + 1 image (max 60vh height) |

**If content exceeds these limits → Split into multiple slides**

### Required CSS Architecture

Every presentation MUST include this base CSS for viewport fitting:

```css
/* ===========================================
   VIEWPORT FITTING: MANDATORY BASE STYLES
   These styles MUST be included in every presentation.
   They ensure slides fit exactly in the viewport.
   =========================================== */

/* 1. Lock html/body to viewport */
html, body {
    height: 100%;
    overflow-x: hidden;
}

html {
    scroll-snap-type: y mandatory;
    scroll-behavior: smooth;
}

/* 2. Each slide = exact viewport height */
.slide {
    width: 100vw;
    height: 100vh;
    height: 100dvh; /* Dynamic viewport height for mobile browsers */
    overflow: hidden; /* CRITICAL: Prevent ANY overflow */
    scroll-snap-align: start;
    display: flex;
    flex-direction: column;
    position: relative;
}

/* 3. Content container with flex for centering */
.slide-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    max-height: 100%;
    overflow: hidden; /* Double-protection against overflow */
    padding: var(--slide-padding);
}

/* 4. ALL typography uses clamp() for responsive scaling */
:root {
    /* Titles scale from mobile to desktop */
    --title-size: clamp(1.5rem, 5vw, 4rem);
    --h2-size: clamp(1.25rem, 3.5vw, 2.5rem);
    --h3-size: clamp(1rem, 2.5vw, 1.75rem);

    /* Body text */
    --body-size: clamp(0.75rem, 1.5vw, 1.125rem);
    --small-size: clamp(0.65rem, 1vw, 0.875rem);

    /* Spacing scales with viewport */
    --slide-padding: clamp(1rem, 4vw, 4rem);
    --content-gap: clamp(0.5rem, 2vw, 2rem);
    --element-gap: clamp(0.25rem, 1vw, 1rem);
}

/* 5. Cards/containers use viewport-relative max sizes */
.card, .container, .content-box {
    max-width: min(90vw, 1000px);
    max-height: min(80vh, 700px);
}

/* 6. Lists auto-scale with viewport */
.feature-list, .bullet-list {
    gap: clamp(0.4rem, 1vh, 1rem);
}

.feature-list li, .bullet-list li {
    font-size: var(--body-size);
    line-height: 1.4;
}

/* 7. Grids adapt to available space */
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 250px), 1fr));
    gap: clamp(0.5rem, 1.5vw, 1rem);
}

/* 8. Images constrained to viewport */
img, .image-container {
    max-width: 100%;
    max-height: min(50vh, 400px);
    object-fit: contain;
}

/* ===========================================
   RESPONSIVE BREAKPOINTS
   Aggressive scaling for smaller viewports
   =========================================== */

/* Short viewports (< 700px height) */
@media (max-height: 700px) {
    :root {
        --slide-padding: clamp(0.75rem, 3vw, 2rem);
        --content-gap: clamp(0.4rem, 1.5vw, 1rem);
        --title-size: clamp(1.25rem, 4.5vw, 2.5rem);
        --h2-size: clamp(1rem, 3vw, 1.75rem);
    }
}

/* Very short viewports (< 600px height) */
@media (max-height: 600px) {
    :root {
        --slide-padding: clamp(0.5rem, 2.5vw, 1.5rem);
        --content-gap: clamp(0.3rem, 1vw, 0.75rem);
        --title-size: clamp(1.1rem, 4vw, 2rem);
        --body-size: clamp(0.7rem, 1.2vw, 0.95rem);
    }

    /* Hide non-essential elements */
    .nav-dots, .keyboard-hint, .decorative {
        display: none;
    }
}

/* Extremely short (landscape phones, < 500px height) */
@media (max-height: 500px) {
    :root {
        --slide-padding: clamp(0.4rem, 2vw, 1rem);
        --title-size: clamp(1rem, 3.5vw, 1.5rem);
        --h2-size: clamp(0.9rem, 2.5vw, 1.25rem);
        --body-size: clamp(0.65rem, 1vw, 0.85rem);
    }
}

/* Narrow viewports (< 600px width) */
@media (max-width: 600px) {
    :root {
        --title-size: clamp(1.25rem, 7vw, 2.5rem);
    }

    /* Stack grids vertically */
    .grid {
        grid-template-columns: 1fr;
    }
}

/* ===========================================
   REDUCED MOTION
   Respect user preferences
   =========================================== */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.2s !important;
    }

    html {
        scroll-behavior: auto;
    }
}
```

### Overflow Prevention Checklist

Before generating any presentation, mentally verify:

1. ✅ Every `.slide` has `height: 100vh; height: 100dvh; overflow: hidden;`
2. ✅ All font sizes use `clamp(min, preferred, max)`
3. ✅ All spacing uses `clamp()` or viewport units
4. ✅ Content containers have `max-height` constraints
5. ✅ Images have `max-height: min(50vh, 400px)` or similar
6. ✅ Grids use `auto-fit` with `minmax()` for responsive columns
7. ✅ Breakpoints exist for heights: 700px, 600px, 500px
8. ✅ No fixed pixel heights on content elements
9. ✅ Content per slide respects density limits

### When Content Doesn't Fit

If you find yourself with too much content:

**DO:**
- Split into multiple slides
- Reduce bullet points (max 5-6 per slide)
- Shorten text (aim for 1-2 lines per bullet)
- Use smaller code snippets
- Create a "continued" slide

**DON'T:**
- Reduce font size below readable limits
- Remove padding/spacing entirely
- Allow any scrolling
- Cram content to fit

### Testing Viewport Fit

After generating, recommend the user test at these sizes:
- Desktop: 1920×1080, 1440×900, 1280×720
- Tablet: 1024×768, 768×1024 (portrait)
- Mobile: 375×667, 414×896
- Landscape phone: 667×375, 896×414

---

## Phase 0: Detect Mode

First, determine what the user wants:

**Mode A: New Presentation**
- User wants to create slides from scratch
- Proceed to Phase 1 (Content Discovery)

**Mode B: PPT Conversion**
- User has a PowerPoint file (.ppt, .pptx) to convert
- Proceed to Phase 4 (PPT Extraction)

**Mode C: Existing Presentation Enhancement**
- User has an HTML presentation and wants to improve it
- Read the existing file, understand the structure, then enhance

---

## Phase 1: Content Discovery (New Presentations)

Use the content the user provides. If content is incomplete or only a topic is provided, create a concise outline and proceed without asking follow-up questions.

---

## Phase 2: Style Application

Apply the single available style: **Swiss Modern — Clean, Bauhaus-inspired, geometric (Light Theme)**. Do not ask style selection questions or generate preview files.

---

## Phase 3: Generate Presentation

Now generate the full presentation based on:
- Content from Phase 1
- Style from Phase 2

### File Structure

For single presentations:
```
presentation.html    # Self-contained presentation
assets/              # Images, if any
```

For projects with multiple presentations:
```
[presentation-name].html
[presentation-name]-assets/
```

### HTML Architecture

Follow this structure for all Dezerv presentations:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Review | Client Name</title>
    
    <!-- Fonts: Cabinet Grotesk + Satoshi from Fontshare -->
    <link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=satoshi@400,500,700,900&f[]=cabinet-grotesk@500,700,800&display=swap">
    
    <style>
        /* ===========================================
           SWISS MODERN THEME — DEZERV EDITION
           Minimal, precise, data-focused design
           =========================================== */
        :root {
            /* Backgrounds */
            --bg-primary: #FAFAFA;        /* Content slide background */
            --bg-secondary: #f8f9fa;
            --bg-dark: #0d0d0d;           /* Title/End slides */
            --bg-card: #FDFDFC;           /* Card background */
            --border-card: rgba(29, 27, 24, 0.08);  /* Card border */
            
            /* Text */
            --text-primary: #0d0d0d;
            --text-secondary: #495057;
            --text-muted: #868e96;
            --text-light: #adb5bd;
            
            /* Data visualization scale */
            --data-1: #0d0d0d;
            --data-2: #343a40;
            --data-3: #495057;
            --data-4: #868e96;
            --data-5: #adb5bd;
            --data-6: #dee2e6;
            
            /* Dezerv semantic colors */
            --color-positive: #23625E;
            --color-negative: #AB2626;
            --color-warning: #B1511D;
            
            /* Accent */
            --accent: #e03131;
            
            /* Typography */
            --font-display: 'Cabinet Grotesk', sans-serif;
            --font-body: 'Satoshi', -apple-system, sans-serif;
            --title-size: clamp(2.5rem, 7vw, 6rem);
            --h2-size: clamp(1.5rem, 4vw, 3rem);
            --h3-size: clamp(1rem, 2vw, 1.5rem);
            --body-size: clamp(0.875rem, 1.2vw, 1.125rem);
            --small-size: clamp(0.75rem, 1vw, 0.875rem);
            --micro-size: clamp(0.625rem, 0.8vw, 0.75rem);
            
            /* Spacing */
            --slide-padding: clamp(2rem, 5vw, 6rem);
            --content-gap: clamp(1.5rem, 3vw, 3rem);
            --grid-gap: clamp(1rem, 2vw, 2rem);
            
            /* Animation */
            --ease-out: cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --duration-fast: 0.25s;
            --duration-normal: 0.4s;
        }

        /* Base styles, slide container, grids, data cards... */
        /* See STYLE_PRESETS.md for complete CSS */
    </style>
</head>
<body>
    <!-- Progress Bar -->
    <div class="progress-bar"></div>
    
    <!-- Navigation Dots -->
    <nav class="nav-dots"></nav>
    
    <!-- Keyboard Hint -->
    <div class="keyboard-hint">
        <kbd>↑</kbd> <kbd>↓</kbd> Navigate
    </div>

    <!-- SLIDE 1: Title (Dark) -->
    <section class="slide title-slide">
        <div class="slide-content">
            <!-- Dezerv Logo (White for dark bg) -->
            <svg class="dezerv-logo reveal" viewBox="0 0 128 32" ...>
                <!-- White logo paths -->
            </svg>
            
            <h1 class="reveal">Portfolio<br>Review</h1>
            <div class="title-meta reveal">
                <div class="title-meta-item">
                    <span class="title-meta-label">Client</span>
                    <span class="title-meta-value">Client Name</span>
                </div>
                <div class="title-meta-item">
                    <span class="title-meta-label">Date</span>
                    <span class="title-meta-value">February 2026</span>
                </div>
            </div>
        </div>
    </section>

    <!-- SLIDE 2: Data Overview -->
    <section class="slide">
        <header class="slide-header reveal">
            <!-- Dezerv Logo (Black for light bg) -->
            <svg class="dezerv-logo" viewBox="0 0 128 32" ...>
                <!-- Black logo paths -->
            </svg>
            <span class="slide-number">01 / 09</span>
        </header>
        <div class="slide-content">
            <h2 class="reveal">Portfolio Overview</h2>
            <div class="grid-4 reveal">
                <div class="data-card accent">
                    <span class="data-label">Total AUM</span>
                    <span class="data-value">₹7.93Cr</span>
                </div>
                <!-- More data cards... -->
            </div>
        </div>
    </section>

    <!-- More slides... -->

    <script>
        /* NumberAnimator + SlidePresentation classes */
        /* See "Number Ticker Animation" section below */
    </script>
</body>
</html>
```

### Required JavaScript Features

Every presentation MUST include:

1. **NumberAnimator Class** — Animates data values from 0 to target
   - Parses currency (₹), percentages (%), and units (Cr, L)
   - Easing function for smooth deceleration
   - Triggers when slide becomes visible

2. **SlidePresentation Class** — Main controller
   - Keyboard navigation (arrows, space)
   - Touch/swipe support
   - Intersection Observer for visibility
   - Progress bar updates
   - Navigation dots

2. **Intersection Observer** — For scroll-triggered animations
   - Add `.visible` class when slides enter viewport
   - Trigger CSS animations efficiently

3. **Optional Enhancements** (based on style):
   - Custom cursor with trail
   - Particle system background (canvas)
   - Parallax effects
   - 3D tilt on hover
   - Magnetic buttons
   - Counter animations

### Code Quality Requirements

**Comments:**
Every section should have clear comments explaining:
- What it does
- Why it exists
- How to modify it

```javascript
/* ===========================================
   CUSTOM CURSOR
   Creates a stylized cursor that follows mouse with a trail effect.
   - Uses lerp (linear interpolation) for smooth movement
   - Grows larger when hovering over interactive elements
   =========================================== */
class CustomCursor {
    constructor() {
        // ...
    }
}
```

**Accessibility:**
- Semantic HTML (`<section>`, `<nav>`, `<main>`)
- Keyboard navigation works
- ARIA labels where needed
- Reduced motion support

```css
@media (prefers-reduced-motion: reduce) {
    .reveal {
        transition: opacity 0.3s ease;
        transform: none;
    }
}
```

**Responsive & Viewport Fitting (CRITICAL):**

**See the "CRITICAL: Viewport Fitting Requirements" section above for complete CSS and guidelines.**

Quick reference:
- Every `.slide` must have `height: 100vh; height: 100dvh; overflow: hidden;`
- All typography and spacing must use `clamp()`
- Respect content density limits (max 4-6 bullets, max 6 cards, etc.)
- Include breakpoints for heights: 700px, 600px, 500px
- When content doesn't fit → split into multiple slides, never scroll

---

## Phase 4: PPT Conversion

When converting PowerPoint files:

### Step 4.1: Extract Content

Use Python with `python-pptx` to extract:

```python
from pptx import Presentation
from pptx.util import Inches, Pt
import json
import os
import base64

def extract_pptx(file_path, output_dir):
    """
    Extract all content from a PowerPoint file.
    Returns a JSON structure with slides, text, and images.
    """
    prs = Presentation(file_path)
    slides_data = []

    # Create assets directory
    assets_dir = os.path.join(output_dir, 'assets')
    os.makedirs(assets_dir, exist_ok=True)

    for slide_num, slide in enumerate(prs.slides):
        slide_data = {
            'number': slide_num + 1,
            'title': '',
            'content': [],
            'images': [],
            'notes': ''
        }

        for shape in slide.shapes:
            # Extract title
            if shape.has_text_frame:
                if shape == slide.shapes.title:
                    slide_data['title'] = shape.text
                else:
                    slide_data['content'].append({
                        'type': 'text',
                        'content': shape.text
                    })

            # Extract images
            if shape.shape_type == 13:  # Picture
                image = shape.image
                image_bytes = image.blob
                image_ext = image.ext
                image_name = f"slide{slide_num + 1}_img{len(slide_data['images']) + 1}.{image_ext}"
                image_path = os.path.join(assets_dir, image_name)

                with open(image_path, 'wb') as f:
                    f.write(image_bytes)

                slide_data['images'].append({
                    'path': f"assets/{image_name}",
                    'width': shape.width,
                    'height': shape.height
                })

        # Extract notes
        if slide.has_notes_slide:
            notes_frame = slide.notes_slide.notes_text_frame
            slide_data['notes'] = notes_frame.text

        slides_data.append(slide_data)

    return slides_data
```

### Step 4.2: Confirm Content Structure

Present the extracted content to the user:

```
I've extracted the following from your PowerPoint:

**Slide 1: [Title]**
- [Content summary]
- Images: [count]

**Slide 2: [Title]**
- [Content summary]
- Images: [count]

...

All images have been saved to the assets folder.

Does this look correct? Should I proceed with style selection?
```

### Step 4.3: Style Application

Proceed to Phase 2 (Style Application) with the extracted content in mind.

### Step 4.4: Generate HTML

Convert the extracted content into the chosen style, preserving:
- All text content
- All images (referenced from assets folder)
- Slide order
- Any speaker notes (as HTML comments or separate file)

---

## Phase 5: Delivery

### Final Output

When the presentation is complete:

1. **Clean up temporary files**
   - Delete `.claude-design/slide-previews/` if it exists

2. **Open the presentation**
   - Use `open [filename].html` to launch in browser

3. **Provide summary**
```
Your presentation is ready!

📁 File: [filename].html
🎨 Style: Swiss Modern (Light)
📊 Slides: [count]

**Navigation:**
- Arrow keys (← →) or Space to navigate
- Scroll/swipe also works
- Click the dots on the right to jump to a slide

**To customize:**
- Colors: Look for `:root` CSS variables at the top
- Fonts: Change the Fontshare/Google Fonts link
- Animations: Modify `.reveal` class timings

Would you like me to make any adjustments?
```

---

## Style Reference: Effect → Feeling Mapping

Use this guide to match animations to intended feelings:

### Dramatic / Cinematic
- Slow fade-ins (1-1.5s)
- Large scale transitions (0.9 → 1)
- Dark backgrounds with spotlight effects
- Parallax scrolling
- Full-bleed images

### Techy / Futuristic
- Neon glow effects (box-shadow with accent color)
- Particle systems (canvas background)
- Grid patterns
- Monospace fonts for accents
- Glitch or scramble text effects
- Cyan, magenta, electric blue palette

### Playful / Friendly
- Bouncy easing (spring physics)
- Rounded corners (large radius)
- Pastel or bright colors
- Floating/bobbing animations
- Hand-drawn or illustrated elements

### Professional / Corporate
- Subtle, fast animations (200-300ms)
- Clean sans-serif fonts
- Navy, slate, or charcoal backgrounds
- Precise spacing and alignment
- Minimal decorative elements
- Data visualization focus

### Calm / Minimal
- Very slow, subtle motion
- High whitespace
- Muted color palette
- Serif typography
- Generous padding
- Content-focused, no distractions

### Editorial / Magazine
- Strong typography hierarchy
- Pull quotes and callouts
- Image-text interplay
- Grid-breaking layouts
- Serif headlines, sans-serif body
- Black and white with one accent

---

## Number Ticker Animation (REQUIRED)

Every presentation with data values MUST include the NumberAnimator class. This creates the signature animated number effect where values count up from 0.

### NumberAnimator Class

```javascript
/* ===========================================
   NUMBER TICKER ANIMATION
   Animates numbers from 0 to target value
   with easing, completes in under 2 seconds
   =========================================== */
class NumberAnimator {
    constructor() {
        this.animatedSlides = new Set();
        this.duration = 1000; // 1 second
    }

    // Easing function for smooth deceleration
    easeOutExpo(t) {
        return t === 1 ? 1 : 1 - Math.pow(2, -10 * t);
    }

    // Parse number from text, handling currency, percentages, etc.
    parseNumber(text) {
        const match = text.match(/([₹+\-]?\s*)(\d+(?:[.,]\d+)?)\s*(%|Cr|L|Lakhs)?/);
        if (!match) return null;

        const prefix = match[1] || '';
        const numStr = match[2].replace(',', '.');
        const suffix = match[3] || '';
        const value = parseFloat(numStr);

        if (isNaN(value)) return null;

        const decimalMatch = numStr.match(/\.(\d+)/);
        const decimals = decimalMatch ? decimalMatch[1].length : 0;

        return { prefix, value, suffix, decimals, original: text };
    }

    // Format number back to string
    formatNumber(value, decimals, prefix, suffix) {
        let formatted = value.toFixed(decimals);
        if (value >= 1000) {
            formatted = value.toLocaleString('en-IN', { 
                minimumFractionDigits: decimals,
                maximumFractionDigits: decimals 
            });
        }
        return `${prefix}${formatted}${suffix}`;
    }

    // Animate a single element
    animateElement(element, parsed) {
        const startTime = performance.now();
        const startValue = 0;
        const endValue = parsed.value;

        const animate = (currentTime) => {
            const elapsed = currentTime - startTime;
            const progress = Math.min(elapsed / this.duration, 1);
            const easedProgress = this.easeOutExpo(progress);
            const currentValue = startValue + (endValue - startValue) * easedProgress;

            element.textContent = this.formatNumber(
                currentValue, 
                parsed.decimals, 
                parsed.prefix, 
                parsed.suffix
            );

            if (progress < 1) {
                requestAnimationFrame(animate);
            } else {
                element.textContent = parsed.original;
            }
        };

        requestAnimationFrame(animate);
    }

    // Find and animate all numbers in a slide
    animateSlide(slide) {
        const slideIndex = Array.from(document.querySelectorAll('.slide')).indexOf(slide);
        
        if (this.animatedSlides.has(slideIndex)) return;
        this.animatedSlides.add(slideIndex);

        const selectors = [
            '.data-value',
            '.account-value', 
            '.chart-stat-value',
            '.donut-value',
            '.strategy-pct',
            '.stacked-segment'
        ];

        const elements = slide.querySelectorAll(selectors.join(', '));

        elements.forEach((element, index) => {
            const text = element.textContent.trim();
            const parsed = this.parseNumber(text);
            
            if (parsed && parsed.value > 0) {
                setTimeout(() => {
                    this.animateElement(element, parsed);
                }, index * 50); // 50ms stagger
            }
        });
    }
}
```

### Integration with SlidePresentation

```javascript
class SlidePresentation {
    constructor() {
        this.slides = document.querySelectorAll('.slide');
        this.numberAnimator = new NumberAnimator();
        // ... other initialization
    }

    setupIntersectionObserver() {
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    
                    // Trigger number animations after reveal animation starts
                    setTimeout(() => {
                        this.numberAnimator.animateSlide(entry.target);
                    }, 200);
                }
            });
        }, { threshold: 0.5 });

        this.slides.forEach(slide => observer.observe(slide));
    }
}
```

---

## Animation Patterns Reference

### Entrance Animations

```css
/* Fade + Slide Up (most common) */
.reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.6s var(--ease-out-expo),
                transform 0.6s var(--ease-out-expo);
}

.visible .reveal {
    opacity: 1;
    transform: translateY(0);
}

/* Scale In */
.reveal-scale {
    opacity: 0;
    transform: scale(0.9);
    transition: opacity 0.6s, transform 0.6s var(--ease-out-expo);
}

/* Slide from Left */
.reveal-left {
    opacity: 0;
    transform: translateX(-50px);
    transition: opacity 0.6s, transform 0.6s var(--ease-out-expo);
}

/* Blur In */
.reveal-blur {
    opacity: 0;
    filter: blur(10px);
    transition: opacity 0.8s, filter 0.8s var(--ease-out-expo);
}
```

### Background Effects

```css
/* Gradient Mesh */
.gradient-bg {
    background:
        radial-gradient(ellipse at 20% 80%, rgba(120, 0, 255, 0.3) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 20%, rgba(0, 255, 200, 0.2) 0%, transparent 50%),
        var(--bg-primary);
}

/* Noise Texture */
.noise-bg {
    background-image: url("data:image/svg+xml,..."); /* Inline SVG noise */
}

/* Grid Pattern */
.grid-bg {
    background-image:
        linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
}
```

### Interactive Effects

```javascript
/* 3D Tilt on Hover */
class TiltEffect {
    constructor(element) {
        this.element = element;
        this.element.style.transformStyle = 'preserve-3d';
        this.element.style.perspective = '1000px';
        this.bindEvents();
    }

    bindEvents() {
        this.element.addEventListener('mousemove', (e) => {
            const rect = this.element.getBoundingClientRect();
            const x = (e.clientX - rect.left) / rect.width - 0.5;
            const y = (e.clientY - rect.top) / rect.height - 0.5;

            this.element.style.transform = `
                rotateY(${x * 10}deg)
                rotateX(${-y * 10}deg)
            `;
        });

        this.element.addEventListener('mouseleave', () => {
            this.element.style.transform = 'rotateY(0) rotateX(0)';
        });
    }
}
```

---

## Troubleshooting

### Common Issues

**Fonts not loading:**
- Check Fontshare/Google Fonts URL
- Ensure font names match in CSS

**Animations not triggering:**
- Verify Intersection Observer is running
- Check that `.visible` class is being added

**Scroll snap not working:**
- Ensure `scroll-snap-type` on html/body
- Each slide needs `scroll-snap-align: start`

**Mobile issues:**
- Disable heavy effects at 768px breakpoint
- Test touch events
- Reduce particle count or disable canvas

**Performance issues:**
- Use `will-change` sparingly
- Prefer `transform` and `opacity` animations
- Throttle scroll/mousemove handlers

---

## Related Skills

- **learn** — Generate FORZARA.md documentation for the presentation
- **frontend-design** — For more complex interactive pages beyond slides
- **design-and-refine:design-lab** — For iterating on component designs

---

## Example Session Flow

1. User: "I want to create a pitch deck for my AI startup"
2. User shares their bullet points and key messages
3. Skill generates full presentation with all slides in Swiss Modern (Light)
4. Skill opens the presentation in browser
5. User requests tweaks to specific slides
6. Final presentation delivered

---

## Conversion Session Flow

1. User: "Convert my slides.pptx to a web presentation"
2. Skill extracts content and images from PPT
3. Skill confirms extracted content with user
4. Skill applies Swiss Modern (Light)
5. Skill generates HTML presentation with preserved assets
6. Final presentation delivered
