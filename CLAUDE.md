# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## Project Overview

**KnowledgeWall** is a static HTML/CSS/JavaScript educational wallpaper generator with a retro design system featuring bold typography, thick borders, and chromatic aberration effects inspired by 1980s CRT monitors, arcade cabinets, and VHS aesthetics.

**Tech Stack:**
- Pure HTML5/CSS3/JavaScript (no build system or dependencies)
- Google Fonts for retro typography
- Static site deployment (GitHub Pages / Vercel)

---

## Development Commands

### Local Development

Start a local server (required for fonts and relative paths):

```bash
# Python 3 (recommended)
python3 -m http.server 8000
# Then open: http://localhost:8000

# Node.js alternative
npx http-server -p 8000

# VS Code: Use "Live Server" extension
```

**No build, compile, or transpile steps needed** - just serve the files.

### Deployment

```bash
# Push to GitHub
git add .
git commit -m "Your changes"
git push origin <branch-name>

# GitHub Pages: Enable in repo Settings → Pages
# Vercel: Import repository via dashboard
```

See `DEPLOYMENT.md` for detailed deployment instructions.

---

## Architecture

### File Structure & Relationships

```
Core Files (must maintain relationships):
├── index.html                      → Main landing page
├── wallpaper-template-retro.html   → Wallpaper generator
├── retro-components-examples.html  → Component showcase
└── retro-styles.css                → Shared stylesheet (ALL HTML files use this)

Theme Configuration:
└── retro-theme-config.json         → Theme definitions (reference for CSS variables)

Documentation:
├── retro-design-system.md          → Complete design system guide
└── DEPLOYMENT.md                   → Deployment instructions
```

**Critical Dependency:** All HTML files MUST link to `retro-styles.css`. Any new HTML page must include:
```html
<link rel="stylesheet" href="retro-styles.css">
```

### Theme System Architecture

The design system uses **CSS Custom Properties** (CSS variables) for theming, with theme switching via `data-theme` attribute on the root element.

**Theme Implementation:**
1. Base colors defined in `:root` (retro-styles.css)
2. Theme-specific overrides in `[data-theme="theme-name"]` selectors
3. JavaScript switches themes by setting `document.documentElement.setAttribute('data-theme', 'theme-name')`
4. All components reference CSS variables (e.g., `var(--theme-accent)`)

**Available Themes:** `dark-retro`, `light-retro`, `synthwave`, `terminal-green`, `amber-monitor`

**Example Theme Switch:**
```javascript
document.documentElement.setAttribute('data-theme', 'synthwave');
```

### Design System Constraints

**Critical Rules (must be maintained):**

1. **Bold Borders Only:** Minimum border width is **3px**. Never use 1px or 2px borders.
   ```css
   border: var(--border-width-thick);  /* 4px minimum */
   ```

2. **Bold Typography:** All text uses minimum **700 font-weight**. Body text is bold by default.
   ```css
   font-weight: var(--font-weight-medium);  /* 700 */
   ```

3. **Chromatic Aberration:** Use on headings and accent elements ONLY, not body text.
   ```css
   .chromatic-text-heavy {
     text-shadow:
       5px 0 0 var(--color-chromatic-red),
       -5px 0 0 var(--color-chromatic-cyan);
   }
   ```

4. **Grid-Based Spacing:** All spacing uses 8px increments.
   ```css
   padding: var(--space-md);  /* 24px = 3 × 8px */
   ```

5. **Sharp Corners Preferred:** Use `border-radius: 0` by default. Only use rounded corners when specified.

### Chromatic Aberration System

Chromatic aberration (RGB split) is a core design feature simulating CRT monitor color fringing.

**Implementation Layers:**
- **Text:** via `text-shadow` with red/cyan channel shifts
- **Boxes:** via `::before`/`::after` pseudo-elements with transformed borders
- **Images:** via `filter: drop-shadow()` (less common)

**4 Intensity Levels:**
- `subtle`: 1px shift (body text, if needed)
- `standard`: 3px shift (h2, h3)
- `heavy`: 5px shift (h1, hero text)
- `extreme`: 8px shift (special effects)

**Usage Guidelines:**
- ✅ Use on: H1, H2, hero text, CTA buttons, decorative borders
- ❌ Avoid on: Body text, small text (<16px), form inputs, data tables

**Technical Implementation (Text):**
```css
text-shadow:
  3px 0 0 rgba(255, 0, 68, 0.8),    /* Red channel shift right */
  -3px 0 0 rgba(0, 255, 255, 0.8);  /* Cyan channel shift left */
```

**Technical Implementation (Borders):**
```css
.chromatic-box::before,
.chromatic-box::after {
  content: '';
  position: absolute;
  border: var(--border-width-thick) solid transparent;
}
.chromatic-box::before {
  border-color: rgba(255, 0, 68, 0.6);
  transform: translate(4px, 0);
}
.chromatic-box::after {
  border-color: rgba(0, 255, 255, 0.6);
  transform: translate(-4px, 0);
}
```

### Wallpaper Generator Architecture

**Canvas Specifications:**
- Default size: 1080×2340px (Android standard)
- Safe zone: 1000×2180px (40px margins, 80px top/bottom)
- Ensures content visibility when set as wallpaper (avoids notches/system UI)

**Layout Templates:**
1. **Terminal:** Border frame, scanlines, monospace fonts, code blocks
2. **Arcade:** Bold colors, pixel fonts, game-style UI elements
3. **VHS/Glitch:** Chromatic glitch, tracking effects, VHS symbols (▓▒░)

**Content Sections:**
- Header (300px): Title with heavy chromatic aberration
- Content (variable): Educational content, lists, code blocks
- Footer (200px): Branding and date

**Scaling for Preview:**
The canvas is rendered at full resolution but displayed scaled down via CSS `transform: scale(0.3)` for preview.

### Special Effects System

**Available Effects:**
- `scanlines-background`: Horizontal line pattern (CRT monitors)
- `grid-background`: Grid overlay (cyberpunk aesthetic)
- `crt-effect`: Flicker animation + scanline overlay
- `glitch-effect`: Position jitter animation
- `chromatic-glitch`: Animated RGB split text-shadow
- `neon-text`: Pulsating glow effect
- `typing-effect`: Terminal typing animation with cursor

Effects are composable - multiple can be applied to the same element.

---

## Component Development

### Adding New Components

1. **Define in retro-styles.css** under the appropriate section
2. **Follow naming convention:** `.retro-componentname` (e.g., `.retro-button`, `.retro-card`)
3. **Use CSS variables** for all colors, spacing, and borders
4. **Ensure bold styling:** Minimum 3px borders, 700+ font-weight
5. **Add chromatic variant** (optional): `.retro-componentname-chromatic`
6. **Document in retro-components-examples.html**

Example component structure:
```css
.retro-component {
  /* Typography */
  font-family: var(--font-body-primary);
  font-size: 16px;
  font-weight: var(--font-weight-medium);

  /* Spacing */
  padding: var(--space-sm) var(--space-md);

  /* Visual */
  background: var(--theme-surface);
  color: var(--theme-text);
  border: var(--border-width-thick) solid var(--theme-border);

  /* Effects (optional) */
  box-shadow: var(--shadow-hard);
}
```

### Modifying Themes

**To add a new theme:**

1. Add theme definition in `retro-theme-config.json`:
```json
"newTheme": {
  "name": "Display Name",
  "id": "new-theme",
  "colors": { ... }
}
```

2. Add CSS variables in `retro-styles.css`:
```css
[data-theme="new-theme"] {
  --theme-bg: #COLOR;
  --theme-surface: #COLOR;
  --theme-text: #COLOR;
  --theme-text-secondary: #COLOR;
  --theme-accent: #COLOR;
  --theme-border: #COLOR;
}
```

3. Update theme switchers in HTML files (button/select elements)

**Theme Variable Naming:**
- `--theme-*` for theme-specific colors (e.g., `--theme-accent`)
- `--color-*` for absolute color values (e.g., `--color-neon-pink`)
- Components use `--theme-*` so they adapt to theme changes

### Typography Guidelines

**Font Stack:**
- Display/Headers: `Bebas Neue`, `Press Start 2P` (pixel), `Orbitron` (sci-fi)
- Body/Code: `Space Mono`, `IBM Plex Mono`, `JetBrains Mono`
- Accent: `VT323` (terminal), `Bungee` (chunky)

**Text Hierarchy:**
- All headings are uppercase and 800-900 weight
- H1 uses heavy chromatic aberration (8px shift)
- H2 uses standard chromatic aberration (3px shift)
- H3+ use accent colors, no chromatic aberration

**Accessibility:**
- All text meets WCAG AAA (7:1 contrast minimum)
- Bold weights improve readability despite effects
- Chromatic aberration avoided on small text
- `prefers-reduced-motion` disables animations

---

## Common Workflows

### Testing Chromatic Aberration

1. Open `retro-components-examples.html`
2. Test with different themes (top-right switcher)
3. Check readability at phone distance (~30cm)
4. Verify effects work on both dark and light themes

### Creating Wallpaper Content

1. Edit content in `wallpaper-template-retro.html`
2. Modify the `sampleTopics` array in `<script>` section
3. Structure: `{ title, section, text, list, highlight, code, info }`
4. Use template literals for multi-line code blocks
5. Test random button to verify all content renders properly

### Responsive Design

Breakpoints:
- Mobile: < 768px
- Tablet: 768px - 1023px
- Desktop: ≥ 1024px

**Mobile-first approach:** Base styles for mobile, then add `@media (min-width: ...)` for larger screens.

---

## Key Constraints & Gotchas

### CSS Specificity

**DO NOT use `!important`** except for:
- Accessibility overrides (`prefers-reduced-motion`)
- Print styles

The design system uses a flat specificity structure (single class selectors) to avoid specificity battles.

### Font Loading

Google Fonts are loaded from CDN. If fonts fail to load:
- Fallbacks are specified in font-family declarations
- System fonts (Courier New, Arial Black) are always available

### Theme Persistence

Themes are saved to `localStorage` by JavaScript in each HTML file:
```javascript
localStorage.setItem('knowledgewall-theme', themeName);
```

When adding new pages, include theme loading logic to maintain consistency across sessions.

### Chromatic Aberration Performance

Heavy chromatic effects use multiple `text-shadow` layers. On low-end devices:
- Limit chromatic elements to 20% of screen
- Use `will-change: transform` for animated effects
- Test on mobile (performance matters for wallpaper viewing)

---

## File Modification Guidelines

### retro-styles.css

**Organization (maintain this structure):**
1. Reset & Base Styles
2. CSS Variables (`:root` and theme overrides)
3. Base Typography
4. Chromatic Aberration Utilities
5. Components (buttons, cards, inputs, etc.)
6. Special Effects
7. Utility Classes
8. Accessibility
9. Responsive Design
10. Print Styles

**When adding new variables:**
- Add to `:root` for global values
- Add to `[data-theme="..."]` for theme-specific values
- Follow naming convention: `--category-name` (e.g., `--color-neon-pink`, `--space-lg`)

### HTML Files

**All HTML files share this structure:**
```html
<!DOCTYPE html>
<html lang="en" data-theme="dark-retro">
<head>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/..." rel="stylesheet">
  <!-- Retro Styles -->
  <link rel="stylesheet" href="retro-styles.css">
</head>
<body>
  <!-- Content -->
  <script>
    // Theme switching logic
    // Local functionality
  </script>
</body>
</html>
```

**Script Placement:** Keep JavaScript inline in `<script>` tags at end of body (no external JS files - keeps project simple).

### retro-theme-config.json

This is a **reference document**, not loaded by the application. It documents theme definitions for:
- Programmatic theme generation (future)
- Design documentation
- Consistency across platforms

Changes here must be manually synced to `retro-styles.css`.

---

## Accessibility Requirements

### Contrast Requirements

All color combinations must meet **WCAG AAA (7:1 for normal text, 4.5:1 for large text):**
- Background `#0A0A0F` vs Text `#FFFFFF` = 19.5:1 ✓
- Background `#0A0A0F` vs Cyan `#00FFFF` = 15.2:1 ✓
- Background `#0A0A0F` vs Green `#00FF41` = 14.8:1 ✓

**Test tool:** Use WebAIM Contrast Checker when adding new color combinations.

### Keyboard Navigation

All interactive elements must be keyboard accessible:
- Native buttons/links (automatic)
- Custom focus states via `:focus-visible`
- Focus indicators: 3px solid cyan outline with 4px offset

### Screen Readers

- Use semantic HTML (`<button>`, `<nav>`, `<main>`, etc.)
- Provide `aria-label` for icon-only buttons
- Include `.sr-only` class for screen-reader-only text

### Reduced Motion

Always wrap animations in:
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

---

## Deployment Architecture

### GitHub Pages

- Serves static files from branch root
- `.nojekyll` file prevents Jekyll processing
- Automatic HTTPS via GitHub
- Cache: 1 hour for HTML, 1 year for CSS

### Vercel

- `vercel.json` configures static site build
- Automatic deployment on push
- Preview URLs for branches
- Cache headers optimize performance

Both platforms require **no build step** - they serve files as-is.

---

## Documentation Files

- **retro-design-system.md**: Complete design system (colors, typography, components)
- **DEPLOYMENT.md**: Step-by-step deployment guide for GitHub Pages and Vercel
- **retro-theme-config.json**: Structured theme definitions (reference only)
- **README.md**: High-level project description

When making significant changes, update relevant documentation files to maintain consistency.

---

## Version: 1.0.0
**Last Updated:** October 2025
