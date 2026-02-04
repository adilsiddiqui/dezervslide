# Style Presets Reference — Dezerv Edition

Curated visual styles for Dezerv client presentations. Minimal, precise, data-focused design optimized for portfolio reviews and financial data visualization.

---

## Dezerv Branding (MANDATORY)

**Every presentation MUST feature the Dezerv logo.**

### Logo Color Guidelines

| Background | Logo Color | Hex Code |
|------------|------------|----------|
| Light (white, cream, pastels) | **Black** | `#000000` |
| Dark (black, navy, charcoal) | **White** | `#ffffff` |

**Never use the logo in any other color. This is non-negotiable.**

### Logo Placement Summary

| Slide Type | Position | Size | Opacity |
|------------|----------|------|---------|
| Title slide | Top-left or centered | `clamp(100px, 15vw, 180px)` | 1.0 |
| Content slides | Header bar (top-left) | `clamp(60px, 8vw, 100px)` | 1.0 |
| Watermark (optional) | Bottom-right (fixed) | `clamp(60px, 8vw, 100px)` | 0.5 |

### Dezerv Logo SVG (Black — for light backgrounds)

```html
<svg class="dezerv-logo" viewBox="0 0 128 32" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path fill-rule="evenodd" clip-rule="evenodd" d="M13.5913 6.3999C19.5734 6.40001 23.1999 10.1524 23.1999 15.9999C23.1999 21.8474 19.5734 25.5998 13.5913 25.5999H6.3999V6.3999H13.5913ZM11.2976 10.7155V21.253H13.3429C16.5045 21.253 18.2718 19.2207 18.2718 15.9999C18.2718 12.7478 16.5045 10.7155 13.3429 10.7155H11.2976Z" fill="#000000"/>
    <path d="M41.1999 10.7155H32.7507V13.7171H40.478V17.939H32.7507V21.253H41.1999V25.5999H27.9999V6.3999H41.1999V10.7155Z" fill="#000000"/>
    <path d="M61.5046 10.0897L52.5819 21.253H61.5999V25.5999H45.9999V21.8788L55.0179 10.7155H46.0952V6.3999H61.5046V10.0897Z" fill="#000000"/>
    <path d="M79.5999 10.7155H71.1507V13.7171H78.878V17.939H71.1507V21.253H79.5999V25.5999H66.3999V6.3999H79.5999V10.7155Z" fill="#000000"/>
    <path fill-rule="evenodd" clip-rule="evenodd" d="M92.664 6.3999C96.6163 6.3999 99.3412 8.74505 99.3413 12.9351C99.3413 15.8432 97.9338 17.8446 95.6882 18.7202L99.9999 25.5999H94.6702L90.8374 19.2522H89.1608V25.5999H84.3999V6.3999H92.664ZM89.1608 15.2491H92.1554C93.8618 15.249 94.6405 14.3421 94.6405 12.9351C94.6404 11.5282 93.8617 10.6219 92.1554 10.6218H89.1608V15.2491Z" fill="#000000"/>
    <path d="M112.109 18.814L116.448 6.3999H121.6L114.451 25.5999H109.549L102.4 6.3999H107.769L112.109 18.814Z" fill="#000000"/>
</svg>
```

### Dezerv Logo SVG (White — for dark backgrounds)

```html
<svg class="dezerv-logo" viewBox="0 0 128 32" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path fill-rule="evenodd" clip-rule="evenodd" d="M13.5913 6.3999C19.5734 6.40001 23.1999 10.1524 23.1999 15.9999C23.1999 21.8474 19.5734 25.5998 13.5913 25.5999H6.3999V6.3999H13.5913ZM11.2976 10.7155V21.253H13.3429C16.5045 21.253 18.2718 19.2207 18.2718 15.9999C18.2718 12.7478 16.5045 10.7155 13.3429 10.7155H11.2976Z" fill="#ffffff"/>
    <path d="M41.1999 10.7155H32.7507V13.7171H40.478V17.939H32.7507V21.253H41.1999V25.5999H27.9999V6.3999H41.1999V10.7155Z" fill="#ffffff"/>
    <path d="M61.5046 10.0897L52.5819 21.253H61.5999V25.5999H45.9999V21.8788L55.0179 10.7155H46.0952V6.3999H61.5046V10.0897Z" fill="#ffffff"/>
    <path d="M79.5999 10.7155H71.1507V13.7171H78.878V17.939H71.1507V21.253H79.5999V25.5999H66.3999V6.3999H79.5999V10.7155Z" fill="#ffffff"/>
    <path fill-rule="evenodd" clip-rule="evenodd" d="M92.664 6.3999C96.6163 6.3999 99.3412 8.74505 99.3413 12.9351C99.3413 15.8432 97.9338 17.8446 95.6882 18.7202L99.9999 25.5999H94.6702L90.8374 19.2522H89.1608V25.5999H84.3999V6.3999H92.664ZM89.1608 15.2491H92.1554C93.8618 15.249 94.6405 14.3421 94.6405 12.9351C94.6404 11.5282 93.8617 10.6219 92.1554 10.6218H89.1608V15.2491Z" fill="#ffffff"/>
    <path d="M112.109 18.814L116.448 6.3999H121.6L114.451 25.5999H109.549L102.4 6.3999H107.769L112.109 18.814Z" fill="#ffffff"/>
</svg>
```

---

## Swiss Modern — Data-Focused Variant

**Vibe:** Minimal, precise, data-focused, professional

**Layout:** Clean grid system with strong typography hierarchy, optimized for financial data.

### Typography

**Fonts:** `Cabinet Grotesk` (display) + `Satoshi` (body) — both from Fontshare

```html
<link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=satoshi@400,500,700,900&f[]=cabinet-grotesk@500,700,800&display=swap">
```

### Complete Color System

```css
:root {
    /* ===========================================
       BACKGROUNDS
       =========================================== */
    --bg-primary: #ffffff;
    --bg-secondary: #f8f9fa;
    --bg-dark: #0d0d0d;
    --bg-card: #f1f3f5;
    
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

### Typography Scale

```css
:root {
    /* Font families */
    --font-display: 'Cabinet Grotesk', sans-serif;
    --font-body: 'Satoshi', -apple-system, sans-serif;
    
    /* Responsive type scale */
    --title-size: clamp(2.5rem, 7vw, 6rem);
    --h2-size: clamp(1.5rem, 4vw, 3rem);
    --h3-size: clamp(1rem, 2vw, 1.5rem);
    --body-size: clamp(0.875rem, 1.2vw, 1.125rem);
    --small-size: clamp(0.75rem, 1vw, 0.875rem);
    --micro-size: clamp(0.625rem, 0.8vw, 0.75rem);
}
```

### Spacing Scale

```css
:root {
    --slide-padding: clamp(2rem, 5vw, 6rem);
    --content-gap: clamp(1.5rem, 3vw, 3rem);
    --grid-gap: clamp(1rem, 2vw, 2rem);
}
```

### Animation Timing

```css
:root {
    --ease-out: cubic-bezier(0.25, 0.46, 0.45, 0.94);
    --duration-fast: 0.25s;
    --duration-normal: 0.4s;
}
```

---

## Data Visualization Components

### Data Cards

```css
.data-card {
    background: var(--bg-card);
    padding: clamp(1.25rem, 2.5vw, 2rem);
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.data-card.accent {
    background: var(--bg-dark);
    color: var(--bg-primary);
}

.data-label {
    font-size: var(--micro-size);
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-weight: 500;
}

.data-value {
    font-family: var(--font-display);
    font-size: clamp(1.75rem, 4vw, 3rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    line-height: 1;
}

.data-sub {
    font-size: var(--small-size);
    color: var(--text-muted);
}
```

### Allocation Tables

```css
.allocation-table {
    width: 100%;
    border-collapse: collapse;
}

.allocation-table th,
.allocation-table td {
    padding: clamp(0.75rem, 1.5vw, 1rem) 0;
    text-align: left;
    border-bottom: 1px solid var(--bg-card);
    font-size: var(--body-size);
}

.allocation-table th {
    font-size: var(--micro-size);
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-weight: 500;
}

.allocation-bar {
    height: 4px;
    background: var(--bg-card);
    position: relative;
    overflow: hidden;
}

.allocation-bar-fill {
    height: 100%;
    background: var(--text-primary);
    transition: width 0.8s var(--ease-out);
}
```

### Stacked Bar Charts

```css
.stacked-bar {
    height: clamp(24px, 4vh, 32px);
    display: flex;
    background: var(--bg-card);
    overflow: hidden;
}

.stacked-segment {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: var(--micro-size);
    font-weight: 600;
    color: var(--bg-primary);
    transition: width 0.8s var(--ease-out);
}

.stacked-segment.dark { background: var(--data-1); }
.stacked-segment.mid { background: var(--data-3); }
.stacked-segment.light { background: var(--data-4); }
.stacked-segment.pale { background: var(--data-5); color: var(--text-primary); }
```

### Donut Charts

```css
.donut-chart {
    width: clamp(160px, 20vw, 220px);
    height: clamp(160px, 20vw, 220px);
    border-radius: 50%;
    position: relative;
    /* Use conic-gradient for segments */
    /* Example: background: conic-gradient(var(--data-1) 0deg 216deg, var(--data-3) 216deg 316deg, ...); */
}

.donut-center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 65%;
    height: 65%;
    background: var(--bg-primary);
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
```

---

## Semantic Color Classes

```css
/* ===========================================
   PORTFOLIO PERFORMANCE INDICATORS
   =========================================== */

/* Positive: gains, success, growth */
.positive, .gain, .up {
    color: var(--color-positive);
}

.bg-positive {
    background-color: var(--color-positive);
    color: #ffffff;
}

/* Negative: losses, errors, decline */
.negative, .loss, .down {
    color: var(--color-negative);
}

.bg-negative {
    background-color: var(--color-negative);
    color: #ffffff;
}

/* Warning/Info: caution, pending */
.warning, .info, .pending {
    color: var(--color-warning);
}

.bg-warning {
    background-color: var(--color-warning);
    color: #ffffff;
}
```

---

## Grid System

```css
.grid-2 {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--grid-gap);
}

.grid-3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--grid-gap);
}

.grid-4 {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: var(--grid-gap);
}

@media (max-width: 900px) {
    .grid-3, .grid-4 {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .grid-2, .grid-3, .grid-4 {
        grid-template-columns: 1fr;
    }
}
```

---

## Slide Types

### Title Slide (Dark)

```css
.title-slide {
    background: var(--bg-dark);
    color: var(--bg-primary);
}

.title-slide h1 {
    font-family: var(--font-display);
    font-size: var(--title-size);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -0.03em;
    text-transform: uppercase;
}
```

### Content Slide Header

```css
.slide-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-bottom: clamp(1rem, 2vw, 1.5rem);
    margin-bottom: var(--content-gap);
    border-bottom: 1px solid var(--bg-card);
}

.slide-number {
    font-size: var(--micro-size);
    color: var(--text-muted);
    font-weight: 500;
}
```

### End Slide (Dark)

```css
.end-slide {
    background: var(--bg-dark);
    color: var(--bg-primary);
    text-align: center;
}
```

---

## Font Pairing Quick Reference

| Preset | Display Font | Body Font | Source |
|--------|--------------|-----------|--------|
| Swiss Modern | Cabinet Grotesk | Satoshi | Fontshare |

---

## DO NOT USE (Generic AI Patterns)

**Fonts:** Inter, Roboto, Arial, system fonts as display

**Colors:** `#6366f1` (generic indigo), purple gradients on white

**Layouts:** Everything centered, generic hero sections, identical card grids

**Decorations:** Realistic illustrations, gratuitous glassmorphism, drop shadows without purpose

---

## Viewport Fitting (CRITICAL)

**Every slide MUST fit exactly in the viewport. No scrolling within slides, ever.**

### Content Density Limits

| Slide Type | Maximum Content |
|------------|-----------------|
| Title slide | 1 heading + meta info (client, date) |
| Data overview | 1 heading + 4 data cards (grid-4) |
| Chart slide | 1 heading + 1 chart + legend |
| Table slide | 1 heading + max 6 rows |
| Summary | 1 heading + 4 summary items |

### Required Base CSS

```css
html, body {
    height: 100%;
    overflow-x: hidden;
}

html {
    scroll-snap-type: y mandatory;
    scroll-behavior: smooth;
}

.slide {
    width: 100vw;
    height: 100vh;
    height: 100dvh;
    overflow: hidden;
    scroll-snap-align: start;
    display: flex;
    flex-direction: column;
    position: relative;
    padding: var(--slide-padding);
}

.slide-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    max-height: 100%;
    overflow: hidden;
}
```

### Responsive Breakpoints

```css
@media (max-height: 700px) {
    :root {
        --slide-padding: clamp(1.5rem, 4vw, 3rem);
        --content-gap: clamp(1rem, 2vw, 1.5rem);
    }
}

@media (max-height: 600px) {
    :root {
        --slide-padding: clamp(1rem, 3vw, 2rem);
    }
    
    .keyboard-hint, .nav-dots {
        display: none;
    }
}

@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.15s !important;
    }
}
```
