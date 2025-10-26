# KnowledgeWall - Retro Design System

> A bold, vintage-inspired design system featuring thick lines, heavy typography, and chromatic aberration effects that evoke 80s/90s computer graphics and retro gaming aesthetics.

---

## 🎨 Design Philosophy

The KnowledgeWall retro design system draws inspiration from:
- **1980s Computer Graphics**: CRT monitors, pixel art, scan lines
- **Vintage Print Design**: Bold Swiss style posters, Brutalist typography
- **Retro Gaming**: Arcade cabinets, 8-bit/16-bit aesthetics
- **VHS & Analog Media**: Chromatic aberration, glitch effects

### Core Principles
1. **BOLD EVERYTHING**: Thick borders, heavy fonts, strong contrast
2. **Chromatic Aberration**: Strategic RGB split for retro CRT effect
3. **Limited Color Palette**: High-contrast, punchy colors
4. **Grid-Based Layouts**: Rigid, geometric, terminal-inspired
5. **Pixel-Perfect Details**: Sharp edges, no subtle gradients

---

## 🎭 Color System

### Primary Retro Palette

```javascript
const retroColors = {
  // Core Colors (CRT Monitor Inspired)
  terminal: {
    green: '#00FF41',      // Classic terminal green
    amber: '#FFBB00',      // Amber monitor
    cyan: '#00FFFF',       // Electric cyan
    magenta: '#FF00FF',    // Hot magenta
    white: '#FFFFFF',      // Pure white
  },

  // Background Colors
  backgrounds: {
    darkVoid: '#0A0A0F',   // Deep space black
    deepNavy: '#1A1A2E',   // Retro navy
    charcoal: '#16213E',   // Dark charcoal
    midnight: '#0F0E17',   // Midnight black
  },

  // Accent Colors (80s Inspired)
  accents: {
    neonPink: '#FF006E',   // Hot pink
    electricBlue: '#0080FF', // Electric blue
    laserRed: '#FF0033',   // Laser red
    acidYellow: '#FFFF00', // Acid yellow
    retroOrange: '#FF6F00', // Retro orange
    synthPurple: '#B942FF', // Synth purple
  },

  // Chromatic Aberration Channels
  chromatic: {
    red: '#FF0044',        // R channel shift
    green: '#00FF88',      // G channel shift
    blue: '#0088FF',       // B channel shift
  },

  // Semantic Colors
  semantic: {
    success: '#00FF41',    // Terminal green
    error: '#FF0033',      // Laser red
    warning: '#FFBB00',    // Amber
    info: '#00FFFF',       // Cyan
  }
};
```

### Theme Configurations

#### Dark Retro (Default)
```javascript
const darkRetroTheme = {
  background: '#0A0A0F',
  surface: '#1A1A2E',
  text: '#FFFFFF',
  textSecondary: '#00FF41',
  accent: '#FF006E',
  border: '#00FFFF',
  borderWidth: '4px',
  shadow: '0 0 20px rgba(255, 0, 110, 0.5)',
  glow: '0 0 30px currentColor',
};
```

#### Light Retro (High Contrast)
```javascript
const lightRetroTheme = {
  background: '#F0F0F0',
  surface: '#FFFFFF',
  text: '#000000',
  textSecondary: '#FF006E',
  accent: '#0080FF',
  border: '#000000',
  borderWidth: '5px',
  shadow: '8px 8px 0 rgba(0, 0, 0, 0.8)',
};
```

#### Synthwave Sunset
```javascript
const synthwaveTheme = {
  background: 'linear-gradient(180deg, #2E1B4D 0%, #4A1942 50%, #7C1E3F 100%)',
  surface: '#1A0B2E',
  text: '#FFFFFF',
  textSecondary: '#FF00FF',
  accent: '#00FFFF',
  border: '#FF006E',
  borderWidth: '4px',
  shadow: '0 0 40px rgba(255, 0, 255, 0.6)',
  glow: '0 0 50px currentColor',
};
```

---

## 📐 Typography System

### Font Families

```javascript
const retroFonts = {
  // Primary Display Fonts
  display: {
    primary: '"Press Start 2P", "Courier New", monospace',    // Pixel/retro gaming
    secondary: '"Bebas Neue", "Arial Black", sans-serif',     // Bold condensed
    tertiary: '"Orbitron", "Futura", sans-serif',             // Sci-fi/tech
  },

  // Body Fonts
  body: {
    primary: '"Space Mono", "Courier New", monospace',        // Monospace readable
    secondary: '"IBM Plex Mono", monospace',                  // Clean mono
    tertiary: '"JetBrains Mono", monospace',                  // Modern mono
  },

  // Accent Fonts
  accent: {
    neon: '"Monoton", cursive',                               // Neon sign effect
    arcade: '"VT323", monospace',                             // Terminal style
    chunky: '"Bungee", sans-serif',                           // Chunky display
  }
};
```

### Font Scale (Bold-First)

```javascript
const retroTypography = {
  // All sizes use BOLD as minimum weight
  scale: {
    mega: {
      size: '72px',
      weight: '900',
      lineHeight: '1.1',
      letterSpacing: '0.05em',
      textTransform: 'uppercase',
    },
    hero: {
      size: '56px',
      weight: '900',
      lineHeight: '1.1',
      letterSpacing: '0.04em',
      textTransform: 'uppercase',
    },
    h1: {
      size: '42px',
      weight: '900',
      lineHeight: '1.2',
      letterSpacing: '0.03em',
      textTransform: 'uppercase',
    },
    h2: {
      size: '32px',
      weight: '800',
      lineHeight: '1.2',
      letterSpacing: '0.02em',
      textTransform: 'uppercase',
    },
    h3: {
      size: '24px',
      weight: '800',
      lineHeight: '1.3',
      letterSpacing: '0.02em',
      textTransform: 'uppercase',
    },
    h4: {
      size: '20px',
      weight: '700',
      lineHeight: '1.4',
      letterSpacing: '0.01em',
    },
    body: {
      size: '16px',
      weight: '700',        // Body text is BOLD
      lineHeight: '1.6',
      letterSpacing: '0.01em',
    },
    small: {
      size: '14px',
      weight: '700',
      lineHeight: '1.5',
      letterSpacing: '0.01em',
    },
    caption: {
      size: '12px',
      weight: '600',
      lineHeight: '1.4',
      letterSpacing: '0.02em',
      textTransform: 'uppercase',
    }
  },

  // Text Effects
  effects: {
    chromaticAberration: {
      textShadow: `
        2px 0 0 #FF0044,
        -2px 0 0 #00FFFF,
        0 0 10px rgba(255, 255, 255, 0.5)
      `,
    },
    neonGlow: {
      textShadow: `
        0 0 10px currentColor,
        0 0 20px currentColor,
        0 0 40px currentColor,
        0 0 80px currentColor
      `,
    },
    retroShadow: {
      textShadow: '4px 4px 0 rgba(0, 0, 0, 0.8)',
    },
    scanlines: {
      background: 'repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0, 0, 0, 0.2) 2px, rgba(0, 0, 0, 0.2) 4px)',
    }
  }
};
```

---

## 🔲 Border & Line System

### Border Widths (BOLD ONLY)

```javascript
const retroBorders = {
  // Minimum border width is 3px - NO THIN LINES
  widths: {
    medium: '3px',
    thick: '4px',
    chunky: '5px',
    mega: '6px',
    ultra: '8px',
    extreme: '10px',
  },

  // Border Styles
  styles: {
    solid: 'solid',
    double: 'double',
    dashed: 'dashed',      // Large dashes only
    dotted: 'dotted',      // Large dots only
  },

  // Border Patterns
  patterns: {
    allSides: '4px solid currentColor',
    topBottom: '4px solid currentColor 0',
    leftRight: '0 4px solid currentColor',
    bottom: '0 0 4px solid currentColor',
    neon: '3px solid currentColor',
    cyberpunk: '4px double currentColor',
  },

  // Corner Radius (Sharp Preferred)
  radius: {
    none: '0',            // Sharp corners (preferred)
    subtle: '2px',        // Barely rounded
    soft: '4px',          // Slightly rounded
    round: '8px',         // Rounded
    pill: '999px',        // Full pill
  }
};
```

### Divider Styles

```javascript
const retroDividers = {
  horizontal: {
    thin: {
      height: '3px',
      background: 'currentColor',
      margin: '16px 0',
    },
    thick: {
      height: '5px',
      background: 'currentColor',
      margin: '24px 0',
    },
    gradient: {
      height: '4px',
      background: 'linear-gradient(90deg, #FF006E 0%, #00FFFF 100%)',
      margin: '20px 0',
    },
    dashed: {
      height: '4px',
      borderTop: '4px dashed currentColor',
      margin: '16px 0',
    }
  },

  vertical: {
    thin: {
      width: '3px',
      background: 'currentColor',
      margin: '0 16px',
    },
    thick: {
      width: '5px',
      background: 'currentColor',
      margin: '0 24px',
    }
  }
};
```

---

## ✨ Chromatic Aberration Effects

### Implementation Methods

#### 1. Text Chromatic Aberration
```css
.chromatic-text {
  position: relative;
  color: #FFFFFF;
  font-weight: 900;

  text-shadow:
    3px 0 0 rgba(255, 0, 68, 0.8),    /* Red channel shift right */
    -3px 0 0 rgba(0, 255, 255, 0.8);  /* Cyan channel shift left */
}

.chromatic-text-heavy {
  text-shadow:
    5px 0 0 #FF0044,
    -5px 0 0 #00FFFF,
    0 0 20px rgba(255, 255, 255, 0.5);
}
```

#### 2. Box/Container Chromatic Aberration
```css
.chromatic-box {
  position: relative;
  background: #1A1A2E;
  border: 4px solid #FFFFFF;
}

.chromatic-box::before,
.chromatic-box::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border: 4px solid transparent;
  pointer-events: none;
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

#### 3. Image Chromatic Aberration
```css
.chromatic-image {
  position: relative;
  filter: drop-shadow(3px 0 0 #FF0044) drop-shadow(-3px 0 0 #00FFFF);
}

/* Alternative: Using multiple backgrounds */
.chromatic-image-layered {
  background-blend-mode: screen;
  background-image:
    url('image.png'),
    url('image.png'),
    url('image.png');
  background-position:
    3px 0,
    -3px 0,
    0 0;
}
```

#### 4. Animated Glitch Effect
```css
@keyframes glitch-chromatic {
  0%, 100% {
    text-shadow:
      2px 0 0 #FF0044,
      -2px 0 0 #00FFFF;
  }
  25% {
    text-shadow:
      -2px 0 0 #FF0044,
      2px 0 0 #00FFFF;
  }
  50% {
    text-shadow:
      4px 0 0 #FF0044,
      -4px 0 0 #00FFFF;
  }
  75% {
    text-shadow:
      -3px 0 0 #FF0044,
      3px 0 0 #00FFFF;
  }
}

.chromatic-glitch {
  animation: glitch-chromatic 3s infinite;
}
```

### Chromatic Aberration Presets

```javascript
const chromaticPresets = {
  // Subtle - for body text
  subtle: {
    redShift: '1px',
    cyanShift: '-1px',
    opacity: 0.4,
  },

  // Standard - for headings
  standard: {
    redShift: '3px',
    cyanShift: '-3px',
    opacity: 0.7,
  },

  // Heavy - for hero text
  heavy: {
    redShift: '5px',
    cyanShift: '-5px',
    opacity: 0.9,
  },

  // Extreme - for special effects
  extreme: {
    redShift: '8px',
    cyanShift: '-8px',
    opacity: 1.0,
    blur: '1px',
  },

  // Glitch - animated
  glitch: {
    redShift: 'random(2-6)px',
    cyanShift: 'random(-6, -2)px',
    opacity: 0.8,
    animation: 'glitch-chromatic 2s infinite',
  }
};
```

---

## 📦 Spacing & Layout

### Spacing Scale (Grid-Based)

```javascript
const retroSpacing = {
  // 8px base unit (chunky spacing)
  base: '8px',

  scale: {
    xs: '8px',      // 1 unit
    sm: '16px',     // 2 units
    md: '24px',     // 3 units
    lg: '32px',     // 4 units
    xl: '40px',     // 5 units
    '2xl': '48px',  // 6 units
    '3xl': '64px',  // 8 units
    '4xl': '80px',  // 10 units
    '5xl': '96px',  // 12 units
  },

  // Component-specific spacing
  components: {
    buttonPadding: '16px 32px',
    cardPadding: '24px',
    sectionPadding: '48px 24px',
    containerMaxWidth: '1200px',
  }
};
```

### Layout Grid

```css
.retro-grid {
  display: grid;
  gap: 24px;
  padding: 24px;

  /* Mobile-first */
  grid-template-columns: 1fr;

  /* Tablet */
  @media (min-width: 768px) {
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
    padding: 32px;
  }

  /* Desktop */
  @media (min-width: 1024px) {
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
    padding: 48px;
  }
}
```

---

## 🎯 Component Specifications

### Buttons

```css
/* Primary Retro Button */
.retro-button {
  /* Typography */
  font-family: "Press Start 2P", monospace;
  font-size: 14px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;

  /* Spacing */
  padding: 16px 32px;

  /* Visual */
  background: #FF006E;
  color: #FFFFFF;
  border: 4px solid #FFFFFF;
  border-radius: 0;

  /* Effects */
  box-shadow:
    6px 6px 0 rgba(0, 0, 0, 0.8),
    0 0 20px rgba(255, 0, 110, 0.5);

  transition: all 0.1s ease;
  cursor: pointer;
}

.retro-button:hover {
  transform: translate(2px, 2px);
  box-shadow:
    4px 4px 0 rgba(0, 0, 0, 0.8),
    0 0 30px rgba(255, 0, 110, 0.8);
}

.retro-button:active {
  transform: translate(6px, 6px);
  box-shadow: none;
}

/* Chromatic Aberration Button */
.retro-button-chromatic {
  position: relative;
  background: #000000;
  border: 4px solid #FFFFFF;
  color: #FFFFFF;
  font-weight: 900;
  padding: 16px 32px;

  text-shadow:
    2px 0 0 #FF0044,
    -2px 0 0 #00FFFF;
}

.retro-button-chromatic::before,
.retro-button-chromatic::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border: 4px solid transparent;
  pointer-events: none;
}

.retro-button-chromatic::before {
  border-color: rgba(255, 0, 68, 0.5);
  transform: translate(3px, 0);
}

.retro-button-chromatic::after {
  border-color: rgba(0, 255, 255, 0.5);
  transform: translate(-3px, 0);
}
```

### Cards

```css
.retro-card {
  background: #1A1A2E;
  border: 5px solid #00FFFF;
  padding: 24px;
  position: relative;

  /* Hard shadow */
  box-shadow: 8px 8px 0 rgba(0, 255, 255, 0.3);
}

.retro-card-header {
  font-family: "Bebas Neue", sans-serif;
  font-size: 32px;
  font-weight: 900;
  text-transform: uppercase;
  color: #00FF41;
  margin-bottom: 16px;
  padding-bottom: 16px;
  border-bottom: 4px solid #00FFFF;

  /* Chromatic effect on header */
  text-shadow:
    2px 0 0 #FF0044,
    -2px 0 0 #00FFFF;
}

.retro-card-body {
  font-family: "Space Mono", monospace;
  font-size: 16px;
  font-weight: 700;
  line-height: 1.6;
  color: #FFFFFF;
}
```

### Input Fields

```css
.retro-input {
  font-family: "IBM Plex Mono", monospace;
  font-size: 16px;
  font-weight: 700;

  padding: 16px;
  background: #0A0A0F;
  color: #00FF41;
  border: 4px solid #00FFFF;
  border-radius: 0;

  /* Terminal cursor effect */
  caret-color: #00FF41;
}

.retro-input:focus {
  outline: none;
  border-color: #FF006E;
  box-shadow:
    0 0 0 4px rgba(255, 0, 110, 0.2),
    0 0 20px rgba(255, 0, 110, 0.5);
}

.retro-input::placeholder {
  color: rgba(0, 255, 65, 0.4);
  font-weight: 700;
}
```

---

## 📱 Wallpaper-Specific Design

### Canvas Configuration (Retro Style)

```javascript
const retroWallpaperConfig = {
  // Canvas dimensions
  dimensions: {
    width: 1080,
    height: 2340,
    safeZone: {
      x: 40,
      y: 80,
      width: 1000,
      height: 2180,
    }
  },

  // Background styles
  backgrounds: {
    scanlines: {
      base: '#0A0A0F',
      overlay: 'repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0, 255, 65, 0.03) 2px, rgba(0, 255, 65, 0.03) 4px)',
    },
    grid: {
      base: '#1A1A2E',
      lines: '#00FFFF',
      lineWidth: '2px',
      spacing: '40px',
    },
    gradient: {
      type: 'linear',
      angle: '180deg',
      stops: [
        { color: '#0A0A0F', position: '0%' },
        { color: '#1A1A2E', position: '50%' },
        { color: '#0A0A0F', position: '100%' },
      ]
    }
  },

  // Border frame
  frame: {
    enabled: true,
    width: '8px',
    color: '#00FFFF',
    style: 'double',
    chromatic: true,
  },

  // Header section
  header: {
    height: '180px',
    background: '#000000',
    borderBottom: '6px solid #FF006E',
    padding: '24px',

    title: {
      font: '"Press Start 2P", monospace',
      size: '28px',
      weight: '900',
      color: '#FFFFFF',
      chromatic: true,
      chromaticStrength: 'heavy',
    }
  },

  // Content area
  content: {
    padding: '32px 24px',

    text: {
      font: '"Space Mono", monospace',
      size: '18px',
      weight: '700',
      lineHeight: '1.6',
      color: '#FFFFFF',
    },

    headings: {
      font: '"Bebas Neue", sans-serif',
      size: '32px',
      weight: '900',
      color: '#00FF41',
      borderBottom: '4px solid #00FFFF',
      marginBottom: '16px',
      paddingBottom: '8px',
    },

    highlights: {
      background: '#FF006E',
      color: '#FFFFFF',
      padding: '4px 8px',
      border: '3px solid #FFFFFF',
      fontWeight: '900',
    },

    lists: {
      bulletStyle: 'square',
      bulletColor: '#00FFFF',
      bulletSize: '8px',
      spacing: '12px',
    }
  },

  // Footer section
  footer: {
    height: '100px',
    background: '#000000',
    borderTop: '6px solid #00FFFF',
    padding: '16px 24px',

    text: {
      font: '"Press Start 2P", monospace',
      size: '10px',
      color: '#00FF41',
      align: 'center',
    }
  }
};
```

### Layout Templates

#### 1. Terminal Style
```
┌────────────────────────────────────────────┐
│ ▓▓▓ KNOWLEDGE TERMINAL v2.0 ▓▓▓           │
├────────────────────────────────────────────┤
│                                            │
│ > TOPIC: QUANTUM PHYSICS                   │
│ > LEVEL: ADVANCED                          │
│                                            │
│ ╔═══════════════════════════════════════╗ │
│ ║  WAVE-PARTICLE DUALITY               ║ │
│ ╚═══════════════════════════════════════╝ │
│                                            │
│ • Light exhibits both wave and particle    │
│   properties                               │
│                                            │
│ • Double-slit experiment demonstrates      │
│   interference patterns                    │
│                                            │
│ ┌─────────────────────────────────────┐   │
│ │ E = hf                              │   │
│ │ where h = 6.626 × 10⁻³⁴ J·s        │   │
│ └─────────────────────────────────────┘   │
│                                            │
├────────────────────────────────────────────┤
│ ▓▓▓ KNOWLEDGEWALL.APP ▓▓▓                 │
└────────────────────────────────────────────┘
```

#### 2. Arcade Style
```
╔══════════════════════════════════════════╗
║  ★ ★ ★  KNOWLEDGE ARCADE  ★ ★ ★         ║
╠══════════════════════════════════════════╣
║                                          ║
║  ▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀  ║
║   ANCIENT CIVILIZATIONS - LEVEL 1        ║
║  ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄  ║
║                                          ║
║  ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓   ║
║  ┃  THE GREAT PYRAMID OF GIZA      ┃   ║
║  ┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛   ║
║                                          ║
║  ■ Built around 2560 BC                  ║
║  ■ 2.3 million stone blocks              ║
║  ■ 146.5 meters tall (originally)        ║
║  ■ Aligned to true north                 ║
║                                          ║
║  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  ║
║                                          ║
╚══════════════════════════════════════════╝
```

#### 3. VHS Glitch Style
```
▓▒░ KNOWLEDGE REWIND ░▒▓

████████████████████████████████
█ TOPIC: SPACE EXPLORATION     █
█ [▓▓▓▓▓▓▓░░░░░] 60% LOADED   █
████████████████████████████████

╭─────────────────────────────╮
│ ≋≋ THE VOYAGER MISSIONS ≋≋  │
╰─────────────────────────────╯

▸ VOYAGER 1: Launched 1977
  ├─ Farthest human-made object
  └─ 14.5 billion miles from Earth

▸ VOYAGER 2: Launched 1977
  ├─ Only craft to visit Uranus/Neptune
  └─ Still transmitting data

┌───────────────────────────────┐
│  "Pale Blue Dot" - 1990       │
│  Photo taken from 4 billion   │
│  miles away                    │
└───────────────────────────────┘

▓▒░ KNOWLEDGE//WALL ░▒▓
```

---

## 🎬 Animation & Effects

### Retro Animations

```css
/* CRT Screen Flicker */
@keyframes crt-flicker {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.98; }
}

.crt-effect {
  animation: crt-flicker 0.15s infinite;
}

/* Scanline Animation */
@keyframes scanline {
  0% { transform: translateY(-100%); }
  100% { transform: translateY(100%); }
}

.scanline-overlay {
  position: absolute;
  width: 100%;
  height: 100px;
  background: linear-gradient(transparent, rgba(255, 255, 255, 0.1), transparent);
  animation: scanline 8s linear infinite;
}

/* Glitch Effect */
@keyframes glitch {
  0%, 90%, 100% {
    transform: translate(0);
  }
  92% {
    transform: translate(-2px, 2px);
  }
  94% {
    transform: translate(2px, -2px);
  }
  96% {
    transform: translate(-2px, -2px);
  }
}

.glitch-effect {
  animation: glitch 5s infinite;
}

/* Neon Pulse */
@keyframes neon-pulse {
  0%, 100% {
    text-shadow:
      0 0 10px currentColor,
      0 0 20px currentColor,
      0 0 40px currentColor;
  }
  50% {
    text-shadow:
      0 0 5px currentColor,
      0 0 10px currentColor,
      0 0 20px currentColor;
  }
}

.neon-text {
  animation: neon-pulse 2s ease-in-out infinite;
}

/* Terminal Typing */
@keyframes typing {
  from { width: 0; }
  to { width: 100%; }
}

@keyframes blink-caret {
  0%, 100% { border-color: transparent; }
  50% { border-color: #00FF41; }
}

.typing-effect {
  overflow: hidden;
  border-right: 4px solid #00FF41;
  white-space: nowrap;
  animation: typing 3s steps(40, end), blink-caret 0.75s step-end infinite;
}
```

---

## ♿ Accessibility Considerations

### High Contrast Retro

While maintaining the retro aesthetic, ensure:

1. **Contrast Ratios**: Minimum 7:1 for normal text (AAA standard)
   - Background #0A0A0F vs Text #FFFFFF = 19.5:1 ✓
   - Background #0A0A0F vs Cyan #00FFFF = 15.2:1 ✓
   - Background #0A0A0F vs Green #00FF41 = 14.8:1 ✓

2. **Bold Text**: All body text minimum 700 weight improves readability

3. **Chromatic Aberration**: Use sparingly
   - Only on headings and accent elements
   - Avoid on body text for better readability
   - Provide option to disable effects

4. **Reduced Motion**: Respect `prefers-reduced-motion`
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 📋 Usage Guidelines

### When to Use Chromatic Aberration

**✅ DO USE on:**
- Main headings (H1, H2)
- Hero text
- Call-to-action buttons
- Brand elements
- Decorative borders

**❌ DON'T USE on:**
- Body text
- Small text (< 16px)
- Input fields
- Long paragraphs
- Tables or data

### Retro Design Checklist

- [ ] All borders are minimum 3px thick
- [ ] Body text is minimum 700 font-weight
- [ ] Headings are 800-900 font-weight
- [ ] Text transform: uppercase used strategically
- [ ] Color contrast meets WCAG AAA (7:1)
- [ ] Chromatic aberration only on 20% of elements
- [ ] Sharp corners preferred (border-radius: 0)
- [ ] Hard shadows (no blur, solid offsets)
- [ ] Grid-based spacing (8px increments)
- [ ] Monospace fonts for code/data
- [ ] Sans-serif bold fonts for headings
- [ ] No subtle gradients (use hard color transitions)

---

## 🎨 Implementation Examples

See companion files:
- `retro-styles.css` - Complete CSS implementation
- `retro-theme.json` - Theme configuration
- `retro-components.html` - Component examples
- `wallpaper-template-retro.html` - Wallpaper generator template

---

## 📚 References & Inspiration

- **Brutalist Web Design**: https://brutalist-web.design/
- **Windows 95 UI**: Classic OS interface patterns
- **Arcade Cabinet Art**: 1980s gaming aesthetics
- **Swiss Poster Design**: Bold typography, grid systems
- **Synthwave Art**: Neon, grids, chromatic aberration
- **Terminal Emulators**: Green screen, amber monitor aesthetics
- **VHS Tracking Errors**: Analog glitch effects

---

**Version**: 1.0.0
**Last Updated**: October 26, 2025
**Status**: Ready for Implementation
