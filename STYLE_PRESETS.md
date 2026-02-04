# Style Presets Reference

Curated visual styles for Frontend Slides. Each preset is inspired by real design references—no generic "AI slop" aesthetics. **Abstract shapes only—no illustrations.**

---

## ⚠️ CRITICAL: Viewport Fitting (Non-Negotiable)

**Every slide MUST fit exactly in the viewport. No scrolling within slides, ever.**

### Content Density Limits Per Slide

| Slide Type | Maximum Content |
|------------|-----------------|
| Title slide | 1 heading + 1 subtitle |
| Content slide | 1 heading + 4-6 bullets (max 2 lines each) |
| Feature grid | 1 heading + 6 cards (2x3 or 3x2) |
| Code slide | 1 heading + 8-10 lines of code |
| Quote slide | 1 quote (max 3 lines) + attribution |

**Too much content? → Split into multiple slides. Never scroll.**

### Required Base CSS (Include in ALL Presentations)

```css
/* ===========================================
   VIEWPORT FITTING: MANDATORY
   Copy this entire block into every presentation
   =========================================== */

/* 1. Lock document to viewport */
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
    height: 100dvh; /* Dynamic viewport for mobile */
    overflow: hidden; /* CRITICAL: No overflow ever */
    scroll-snap-align: start;
    display: flex;
    flex-direction: column;
    position: relative;
}

/* 3. Content wrapper */
.slide-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    max-height: 100%;
    overflow: hidden;
    padding: var(--slide-padding);
}

/* 4. ALL sizes use clamp() - scales with viewport */
:root {
    /* Typography */
    --title-size: clamp(1.5rem, 5vw, 4rem);
    --h2-size: clamp(1.25rem, 3.5vw, 2.5rem);
    --body-size: clamp(0.75rem, 1.5vw, 1.125rem);
    --small-size: clamp(0.65rem, 1vw, 0.875rem);

    /* Spacing */
    --slide-padding: clamp(1rem, 4vw, 4rem);
    --content-gap: clamp(0.5rem, 2vw, 2rem);
}

/* 5. Cards/containers use viewport-relative max sizes */
.card, .container {
    max-width: min(90vw, 1000px);
    max-height: min(80vh, 700px);
}

/* 6. Images constrained */
img {
    max-width: 100%;
    max-height: min(50vh, 400px);
    object-fit: contain;
}

/* 7. Grids adapt to space */
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 220px), 1fr));
    gap: clamp(0.5rem, 1.5vw, 1rem);
}

/* ===========================================
   RESPONSIVE BREAKPOINTS - Height-based
   =========================================== */

/* Short screens (< 700px height) */
@media (max-height: 700px) {
    :root {
        --slide-padding: clamp(0.75rem, 3vw, 2rem);
        --content-gap: clamp(0.4rem, 1.5vw, 1rem);
        --title-size: clamp(1.25rem, 4.5vw, 2.5rem);
    }
}

/* Very short (< 600px height) */
@media (max-height: 600px) {
    :root {
        --slide-padding: clamp(0.5rem, 2.5vw, 1.5rem);
        --title-size: clamp(1.1rem, 4vw, 2rem);
        --body-size: clamp(0.7rem, 1.2vw, 0.95rem);
    }

    .nav-dots, .keyboard-hint, .decorative {
        display: none;
    }
}

/* Extremely short - landscape phones (< 500px) */
@media (max-height: 500px) {
    :root {
        --slide-padding: clamp(0.4rem, 2vw, 1rem);
        --title-size: clamp(1rem, 3.5vw, 1.5rem);
        --body-size: clamp(0.65rem, 1vw, 0.85rem);
    }
}

/* Narrow screens */
@media (max-width: 600px) {
    .grid {
        grid-template-columns: 1fr;
    }
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.2s !important;
    }
}
```

### Viewport Fitting Checklist

Before finalizing any presentation, verify:

- [ ] Every `.slide` has `height: 100vh; height: 100dvh; overflow: hidden;`
- [ ] All font sizes use `clamp(min, preferred, max)`
- [ ] All spacing uses `clamp()` or viewport units
- [ ] Breakpoints exist for heights: 700px, 600px, 500px
- [ ] Content respects density limits (max 6 bullets, max 6 cards)
- [ ] No fixed pixel heights on content elements
- [ ] Images have `max-height` constraints

---

## Swiss Modern (Light Theme Only)

### 1. Swiss Modern — Clean, Bauhaus-inspired, geometric (Light)

**Vibe:** Clean, precise, Bauhaus-inspired, geometric

**Layout:** Asymmetric grid with strong alignment, generous whitespace.

**Typography:** `Archivo` (800) + `Nunito` (400)

**Colors:**
```css
:root {
    --bg-primary: #ffffff;
    --text-primary: #000000;
    --text-secondary: #1a1a1a;
    --accent: #ff3300;
    --grid-line: rgba(0, 0, 0, 0.06);
}
```

**Signature Elements:**
- Visible grid (subtle line texture)
- Asymmetric layouts with strong margins
- Geometric shapes (circle, line, square) as accents
- Red accent used sparingly for emphasis

---

## Font Pairing Quick Reference

| Preset | Display Font | Body Font | Source |
|--------|--------------|-----------|--------|
| Swiss Modern | Archivo | Nunito | Google |

---

## DO NOT USE (Generic AI Patterns)

**Fonts:** Inter, Roboto, Arial, system fonts as display

**Colors:** `#6366f1` (generic indigo), purple gradients on white

**Layouts:** Everything centered, generic hero sections, identical card grids

**Decorations:** Realistic illustrations, gratuitous glassmorphism, drop shadows without purpose

---

## Troubleshooting Viewport Issues

### Content Overflows the Slide

**Symptoms:** Scrollbar appears, content cut off, elements outside viewport

**Solutions:**
1. Check slide has `overflow: hidden` (not `overflow: auto` or `visible`)
2. Reduce content — split into multiple slides
3. Ensure all fonts use `clamp()` not fixed `px` or `rem`
4. Add/fix height breakpoints for smaller screens
5. Check images have `max-height: min(50vh, 400px)`

### Text Too Small on Mobile / Too Large on Desktop

**Symptoms:** Unreadable text on phones, oversized text on big screens

**Solutions:**
```css
/* Use clamp with viewport-relative middle value */
font-size: clamp(1rem, 3vw, 2.5rem);
/*              ↑       ↑      ↑
            minimum  scales  maximum */
```

### Content Doesn't Fill Short Screens

**Symptoms:** Excessive whitespace on landscape phones or short browser windows

**Solutions:**
1. Add `@media (max-height: 600px)` and `(max-height: 500px)` breakpoints
2. Reduce padding at smaller heights
3. Hide decorative elements (`display: none`)
4. Consider hiding nav dots and hints on short screens

### Testing Recommendations

Test at these viewport sizes:
- **Desktop:** 1920×1080, 1440×900, 1280×720
- **Tablet:** 1024×768 (landscape), 768×1024 (portrait)
- **Mobile:** 375×667 (iPhone SE), 414×896 (iPhone 11)
- **Landscape phone:** 667×375, 896×414

Use browser DevTools responsive mode to quickly test multiple sizes.
