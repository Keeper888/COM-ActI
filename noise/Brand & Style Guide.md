# C.O.M. - Brand & Style Guide
## UI/UX and Visual Identity Documentation

---

## 1. BRAND ESSENCE

| Attribute | Value |
|-----------|-------|
| **Name** | C.O.M. (Count of Monte Cristo) |
| **Archetype** | The Secret Society / The Oracle |
| **Tone** | Cryptic, Elegant, Exclusive, Ancient-yet-Digital |
| **Feeling** | "You've stumbled upon something you weren't meant to find" |
| **Inspiration** | Cicada 3301 + Secret Societies + Cold War Intelligence |

---

## 2. COLOR PALETTE

### Primary Colors

| Name | Hex | Usage |
|------|-----|-------|
| **Void Black** | `#0a0a0a` | Primary background |
| **Surface Dark** | `#111111` | Cards, containers |
| **Border Gray** | `#1a1a1a` | Borders, dividers |

### Text Colors

| Name | Hex | Usage |
|------|-----|-------|
| **Primary Text** | `#e0e0e0` | Body text, epigraphs |
| **White** | `#f5f5f5` | Headlines, emphasis |
| **Dim** | `#888888` | Secondary, hints, metadata |
| **Muted** | `#555555` | Barely visible hints |

### Accent Colors

| Name | Hex | Usage |
|------|-----|-------|
| **Gold** | `#d4af37` | Primary accent, sigils, highlights |
| **Blood Red** | `#8b0000` | Warnings, errors, danger |
| **Muted Red** | `#8b4444` | Soft warnings, expiry notices |
| **Dark Red BG** | `#3d0000` | Warning box borders |

### CSS Variables
```css
:root {
    --black: #0a0a0a;
    --dark: #111;
    --gray: #1a1a1a;
    --text: #e0e0e0;
    --dim: #888;
    --accent: #d4af37;
    --white: #f5f5f5;
}
```

---

## 3. TYPOGRAPHY

### Font Stack

| Type | Font | Fallback | Usage |
|------|------|----------|-------|
| **Serif** | EB Garamond | Georgia, serif | Body text, quotes, epigraphs |
| **Mono** | JetBrains Mono | Consolas, monospace | Code, ciphers, labels, UI elements |

### Google Fonts Import
```css
@import url('https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400;0,500;1,400&family=JetBrains+Mono:wght@300;400&display=swap');
```

### Type Scale

| Element | Font | Size | Weight | Spacing |
|---------|------|------|--------|---------|
| Sigil/Symbol | - | 6rem | - | - |
| Page Title | EB Garamond | 1.8rem | 400 | normal |
| Section Title | EB Garamond | 1.4rem | 400 | normal |
| Body Text | EB Garamond | 1rem | 400 | normal |
| Epigraph | EB Garamond | 1.1rem | 400 italic | 0.5px |
| UI Label | JetBrains Mono | 0.65-0.75rem | 400 | 2-4px |
| Cipher Text | JetBrains Mono | 1.1rem | 400 | 8px |
| Button | JetBrains Mono | 0.75-0.8rem | 400-500 | 2-3px |

### Line Height
- Body: 1.7
- UI Elements: 1.4

---

## 4. VISUAL ELEMENTS

### The Sigil
- Symbol: `◆` (Unicode: &#9670;)
- Color: Gold (#d4af37)
- Usage: Brand mark, section dividers, emphasis
- Animation: Slow breathe (4s ease-in-out, opacity 0.7-1, scale 1-1.02)

### Runic Decorations
- Characters: `ᚥ ᚯ ᚰ ᚲ` (Elder Futhark-style)
- Color: Dim (#555) at 15% opacity
- Usage: Side borders, footer decoration
- Orientation: Vertical, writing-mode: vertical-rl

### Scanlines Overlay
```css
background: repeating-linear-gradient(
    0deg,
    rgba(0,0,0,0.1) 0px,
    rgba(0,0,0,0.1) 1px,
    transparent 1px,
    transparent 2px
);
```

---

## 5. UI COMPONENTS

### Buttons

**Primary (Gold)**
```css
background: var(--accent);
color: var(--black);
border: none;
padding: 15px 40px;
font-family: 'JetBrains Mono';
font-size: 0.8rem;
letter-spacing: 2px;
```

**Secondary (Outline)**
```css
background: transparent;
border: 1px solid var(--dim);
color: var(--text);
padding: 12px 40px;
```

**Hover State**
- Gold buttons: brightness(1.1), translateY(-2px), box-shadow
- Outline buttons: background fills, color inverts

### Input Fields
```css
background: transparent;
border: 1px solid var(--gray);
color: var(--white);
font-family: 'JetBrains Mono';
text-align: center;
letter-spacing: 2px;
padding: 15px 20px;
```
- Focus: border-color changes to gold

### Cards/Containers
```css
background: var(--dark);
border: 1px solid var(--gray);
padding: 25px;
```

### Warning Boxes
```css
background: rgba(139, 0, 0, 0.1);
border: 1px solid #3d0000;
color: #8b4444;
font-family: 'JetBrains Mono';
font-size: 0.75rem;
```

### Classified Data Display
```css
.classified-line {
    display: flex;
    justify-content: space-between;
    padding: 8px 0;
    border-bottom: 1px solid var(--gray);
}
.classified-key { color: var(--dim); }
.classified-val { color: var(--text); }
.classified-val.gold { color: var(--accent); }
```

---

## 6. ANIMATIONS

### Breathe (Sigil)
```css
@keyframes breathe {
    0%, 100% { opacity: 0.7; transform: scale(1); }
    50% { opacity: 1; transform: scale(1.02); }
}
animation: breathe 4s ease-in-out infinite;
```

### Glitch Transition
```css
@keyframes glitchFade {
    0% { opacity: 1; }
    20% { opacity: 0.8; transform: translateX(-5px); }
    40% { opacity: 0.9; transform: translateX(5px); }
    60% { opacity: 0.7; transform: translateX(-3px); }
    100% { opacity: 0; }
}
```

### Flicker (Text)
```css
@keyframes flicker {
    0%, 95%, 100% { opacity: 1; }
    96%, 98% { opacity: 0.3; }
}
```

### Fade Pulse
```css
@keyframes fade {
    0%, 100% { opacity: 0.3; }
    50% { opacity: 0.7; }
}
```

---

## 7. SPACING & LAYOUT

### Container Widths
- Max content width: 500-600px
- Centered with margin: 0 auto
- Padding: 40px 20px

### Spacing Scale
- xs: 8px
- sm: 15px
- md: 25px
- lg: 40px
- xl: 50px

### Phase Structure
- Full viewport height (min-height: 100vh)
- Flexbox centered (align-items: center, justify-content: center)
- Relative positioning for decorative elements

---

## 8. TONE OF VOICE

### Writing Style
- **Cryptic but clear**: Mysterious without being confusing
- **Short sentences**: Punchy. Direct. No fluff.
- **Second person**: "You have proven worthy"
- **Present tense**: Creates immediacy
- **No exclamation marks**: Calm authority, never excited

### Example Phrases
| Do | Don't |
|----|-------|
| "You found the signal." | "Congratulations! You found it!" |
| "The worthy will understand." | "Smart people will get this!" |
| "Entry is final." | "Once you join, you can't unjoin!" |
| "Prove you are not one of them." | "Show us you're smart enough!" |

### Epigraph Style
- Philosophical or literary quotes
- Attributed with "- Name" or "- Source, Date"
- Italic, slightly dimmed

---

## 9. PSYCHOLOGICAL FRAMEWORK

### Core Techniques Used

| Technique | How We Apply It |
|-----------|-----------------|
| **Mystery Box** | Golden sigil - unexplained, invites click |
| **Self-Selection** | Cipher test filters "worthy" |
| **Commitment** | Each phase deepens investment |
| **Endowment** | Unique token feels owned |
| **Loss Aversion** | Token expires, countdown |
| **Information Gap** | Partial info, redacted fields |
| **Authority** | Quotes from known figures |
| **Exclusivity** | "94% failed", node designations |
| **Social Proof** | Subtle seeker count |

---

## 10. ICON & SYMBOL REFERENCE

| Symbol | Unicode | Usage |
|--------|---------|-------|
| ◆ | &#9670; | Primary sigil |
| ◇ | &#9671; | Secondary/outline sigil |
| ▶ | &#9654; | Action/enter |
| ● | &#9679; | Status dot |
| ᚥ | &#5765; | Runic decoration |
| ᚯ | &#5791; | Runic decoration |
| ᚰ | &#5792; | Runic decoration |
| ᚲ | &#5794; | Runic decoration |

---

## 11. FILE STRUCTURE

```
countofmontecristo/
├── landing.html          # Main acquisition page
├── index.html            # Game (Level 1)
├── Brand & Style Guide.md    # This document
├── Operational Framework.md  # Psychology techniques
└── Landing Page.md           # Landing page documentation
```

---

## 12. QUICK REFERENCE

### Starting a New Page
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>C.O.M.</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400;0,500;1,400&family=JetBrains+Mono:wght@300;400&display=swap');

        :root {
            --black: #0a0a0a;
            --dark: #111;
            --gray: #1a1a1a;
            --text: #c4c4c4;
            --dim: #555;
            --accent: #d4af37;
            --white: #e8e8e8;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'EB Garamond', serif;
            background: var(--black);
            color: var(--text);
            min-height: 100vh;
            line-height: 1.7;
        }
    </style>
</head>
<body>
    <!-- Content -->
</body>
</html>
```

---

## 13. DON'TS

- No emojis (use symbols instead)
- No bright colors
- No rounded corners (sharp edges only)
- No playful language
- No exclamation marks
- No generic stock imagery
- No gradients (except subtle scanlines)
- No drop shadows (except subtle glow on sigil)

---

*Document Version: 1.0*
*Last Updated: December 2024*
*Project: Count of Monte Cristo (C.O.M.)*
