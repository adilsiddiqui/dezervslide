# Dezerv Slides

An internal tool for creating professional, data-focused HTML presentations for Dezerv client reviews and internal communications.

## Overview

**Dezerv Slides** generates zero-dependency HTML presentations optimized for portfolio reviews, client presentations, and internal reports. Every presentation uses the Swiss Modern design system with consistent Dezerv branding.

### Key Features

- **Zero Dependencies** — Single HTML files with inline CSS/JS. No build tools required.
- **Data-Focused Design** — Optimized for financial data, portfolio metrics, and charts.
- **Animated Numbers** — Data values animate from 0 to target for visual impact.
- **Consistent Branding** — Dezerv logo and semantic colors (green/red/orange) built-in.
- **Responsive** — Works on desktop, tablet, and mobile devices.

## Quick Start

### Using with Claude/Cursor

1. Reference the skill in your prompt:
   ```
   Create a portfolio review presentation for [Client Name]
   ```

2. Provide your content (AUM, returns, allocations, etc.)

3. The skill generates a complete HTML presentation with:
   - Dark title slide with Dezerv logo
   - Data cards with animated numbers
   - Charts and allocation visualizations
   - Professional end slide

### Manual Usage

Open `demo-swiss-modern.html` in a browser to see the template in action.

## Design System

### Typography

**Font:** Inter (Google Fonts)
- Display: Inter 700-900
- Body: Inter 400-500

### Colors

| Purpose | Color | Hex |
|---------|-------|-----|
| Positive (gains) | Dezerv Green | `#23625E` |
| Negative (losses) | Dezerv Red | `#AB2626` |
| Warning/Info | Dezerv Orange | `#B1511D` |
| Primary text | Black | `#0d0d0d` |
| Background | White | `#ffffff` |

### Data Scale (for charts)

```
--data-1: #0d0d0d (darkest)
--data-2: #343a40
--data-3: #495057
--data-4: #868e96
--data-5: #adb5bd
--data-6: #dee2e6 (lightest)
```

## Slide Types

### Title Slide (Dark)
- Dark background (#0d0d0d)
- White Dezerv logo
- Client name, date, presentation type

### Content Slides
- White background
- Header with black Dezerv logo + slide number
- Data cards, tables, charts

### End Slide (Dark)
- Dark background
- Centered Dezerv logo
- Thank you message

## Components

- **Data Cards** — Display metrics with labels, values, and sub-text
- **Stacked Bar Charts** — Visualize allocations and distributions
- **Allocation Tables** — Display asset breakdowns with progress bars
- **Donut Charts** — Show portfolio composition (CSS-based)
- **Line Charts** — Performance comparison (SVG-based)

## Navigation

Presentations support multiple navigation methods:
- **Keyboard:** Arrow keys, Space, Page Up/Down
- **Mouse:** Scroll wheel, click navigation dots
- **Touch:** Swipe up/down

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Complete skill instructions and code templates |
| `STYLE_PRESETS.md` | Design system reference (colors, components, CSS) |
| `demo-swiss-modern.html` | Working demo presentation |

## Dezerv Logo Usage

The Dezerv logo must only be used in:
- **Black** (`#000000`) on light backgrounds
- **White** (`#ffffff`) on dark backgrounds

Never use the logo in any other color.

## Development

To modify the skill:

1. Edit `SKILL.md` for instructions and templates
2. Edit `STYLE_PRESETS.md` for design tokens and components
3. Test changes with `demo-swiss-modern.html`

## License

Internal use only — Dezerv proprietary.
