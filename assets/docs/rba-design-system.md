# Rosaries by Anna — Design System
*Version 1.0 | Homepage Build Reference*

---

## 1. Design Direction

**Aesthetic:** Refined devotional — warm, editorial, artisan. Think a high-end Catholic gift shop crossed with a personal letter. Not sterile e-commerce; not overly ornate. Quietly elevated.

**Tone:** Personal, reverent, unhurried. The design should feel like it was made by one person for one person — because it was.

**One thing to remember:** The warmth of the porcelain background, the serif headings, and Anna's story told without apology.

---

## 2. Colour Tokens

```css
:root {
  /* Primary Palette */
  --color-navy:       #0e3a80;   /* Primary CTA, nav active, footer bg */
  --color-porcelain:  #fcfaf5;   /* Page background, light sections */
  --color-brick:      #c14953;   /* Secondary CTA, accent highlights, hover states */
  --color-cornflower: #5b97ed;   /* Logo accent, inline links, subtle highlights */

  /* Supporting Neutrals */
  --color-warm-white: #F5F4F2;   /* Alternate section backgrounds */
  --color-ink:        #1a1a1a;   /* Body text */
  --color-muted:      #6b6b6b;   /* Captions, meta text, secondary body */
  --color-rule:       #e2ddd6;   /* Dividers, borders */

  /* Overlays */
  --color-navy-overlay:  rgba(14, 58, 128, 0.55);   /* Hero image overlay */
  --color-dark-overlay:  rgba(20, 15, 10, 0.45);    /* Testimonial section overlay */
}
```

### Colour Usage Rules

| Token | Use |
|---|---|
| `--color-navy` | Primary buttons, nav bg (scrolled), footer, section headers on light bg |
| `--color-porcelain` | Default page bg, button text on navy |
| `--color-brick` | Secondary/ghost buttons, hover states, accent underlines, sale badges |
| `--color-cornflower` | Logo "Anna" wordmark, inline text links, subtle icon accents |
| `--color-warm-white` | Alternating section bg (product grid, quote section) |
| `--color-ink` | All body text, headings on light bg |
| `--color-muted` | Subheadings, captions, bylines, read-more links |
| `--color-rule` | HR elements, card borders, input borders |

**Never:** Use brick and cornflower together in the same component. They clash. Navy + brick or Navy + cornflower are the safe pairings.

---

## 3. Typography

### Font Stack

```css
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,500&family=DM+Sans:wght@300;400;500&display=swap');

:root {
  --font-display: 'Cormorant Garamond', Georgia, serif;
  --font-body:    'DM Sans', system-ui, sans-serif;
}
```

### Type Scale

```css
:root {
  /* Display — Cormorant Garamond */
  --text-display-xl: clamp(2.75rem, 5vw, 4.5rem);   /* Hero headline */
  --text-display-lg: clamp(2rem, 3.5vw, 3rem);       /* Section headlines */
  --text-display-md: clamp(1.5rem, 2.5vw, 2rem);     /* Sub-section heads, card titles */
  --text-display-sm: clamp(1.25rem, 2vw, 1.5rem);    /* Pull quotes, callouts */

  /* Body — DM Sans */
  --text-body-lg:  1.125rem;   /* Lead paragraphs */
  --text-body-md:  1rem;       /* Standard body */
  --text-body-sm:  0.875rem;   /* Captions, labels, nav items */
  --text-body-xs:  0.75rem;    /* Footer small print, legal */
}
```

### Typography Rules

- **Headings:** Cormorant Garamond, weight 400 or 500. Use italic (`font-style: italic`) for emphasis within headings — it's beautiful in Cormorant. Never bold (700+) for display text; it loses elegance.
- **Body:** DM Sans, weight 300 or 400. Weight 500 for labels and nav only.
- **Line height:** `1.8` for body, `1.15` for display headings, `1.4` for sub-headings.
- **Letter spacing:** `-0.02em` on display-xl and display-lg headings. `0.08em` on all-caps labels/nav items.
- **Maximum line length:** `65ch` for body text blocks. Never full-width prose.
- **Quotes:** Cormorant Garamond italic, display-sm size. Use a proper opening `"` and closing `"` character, not straight quotes.

### Type Pairings in Practice

| Element | Font | Size token | Weight | Style |
|---|---|---|---|---|
| Hero headline | Cormorant Garamond | display-xl | 400 | Normal |
| Hero subhead | DM Sans | body-lg | 300 | Normal |
| Section headline | Cormorant Garamond | display-lg | 400 | Normal |
| Section sub-label | DM Sans | body-sm | 500 | Uppercase, tracked |
| Body paragraph | DM Sans | body-md | 300 | Normal |
| Pull quote | Cormorant Garamond | display-sm | 400 | Italic |
| Quote attribution | DM Sans | body-sm | 400 | Normal, muted |
| Button | DM Sans | body-sm | 500 | Uppercase, tracked |
| Nav item | DM Sans | body-sm | 400 | Normal |
| Footer | DM Sans | body-xs | 300 | Normal |

---

## 4. Spacing System

Based on an 8px base unit. All spacing values are multiples of 4 or 8.

```css
:root {
  --space-1:   4px;
  --space-2:   8px;
  --space-3:   12px;
  --space-4:   16px;
  --space-5:   24px;
  --space-6:   32px;
  --space-7:   48px;
  --space-8:   64px;
  --space-9:   96px;
  --space-10:  128px;
  --space-11:  160px;
}
```

### Spacing Rules

| Context | Token |
|---|---|
| Section vertical padding (desktop) | `--space-10` top/bottom |
| Section vertical padding (mobile) | `--space-8` top/bottom |
| Component internal padding | `--space-5` or `--space-6` |
| Card padding | `--space-5` |
| Button padding | `--space-3` vertical, `--space-6` horizontal |
| Nav height | 72px |
| Max content width | 1200px |
| Text column max-width | 720px |
| Gutter (grid) | `--space-5` (24px) |

---

## 5. Layout & Grid

```css
:root {
  --layout-max:     1200px;
  --layout-text:    720px;
  --layout-gutter:  var(--space-5);   /* 24px */
  --layout-margin:  var(--space-6);   /* 32px, collapses to space-5 on mobile */
}
```

### Grid Patterns Used on Homepage

| Section | Layout |
|---|---|
| Hero | Full-bleed, image bg with overlay, content left-aligned at 50% width |
| Intro text | Single centred column, max 720px |
| Product grid | 3-column CSS grid, equal columns, gap `--space-3` |
| About | 2-column: image left (40%), text right (60%) |
| Testimonial | Full-bleed bg image with overlay, centred text column max 680px |
| Footer | 2-column: logo/tagline left, nav right |

---

## 6. Component Specifications

### Navigation

```
Height: 72px
Background: transparent (over hero), --color-porcelain (scrolled)
Logo: left-aligned
Nav links: right-aligned, DM Sans 400, body-sm, letter-spacing 0.03em
Active link: --color-navy underline
Sticky: yes, transition bg on scroll
Mobile: hamburger at 768px breakpoint, full-screen overlay nav
```

### Buttons

Two variants only:

**Primary (Filled)**
```
Background:   --color-navy
Text:         --color-porcelain
Font:         DM Sans 500, body-sm, uppercase, letter-spacing 0.1em
Padding:      12px 32px
Border-radius: 2px (near-square — refined, not pill)
Hover:        background --color-brick, transition 200ms ease
```

**Secondary (Outlined)**
```
Background:   transparent
Border:       1.5px solid --color-navy
Text:         --color-navy
Font:         DM Sans 500, body-sm, uppercase, letter-spacing 0.1em
Padding:      12px 32px
Border-radius: 2px
Hover:        background --color-navy, text --color-porcelain, transition 200ms ease
```

**Never:** Pill buttons, shadow-heavy buttons, gradient buttons, or more than 2 button variants on a single page.

### Cards (Product)

```
Background:   white (#ffffff)
Border:       none
Border-radius: 0 (flat edges — artisan feel)
Shadow:       none by default; subtle on hover: 0 4px 20px rgba(0,0,0,0.08)
Image:        full-width, aspect-ratio 1/1, object-fit cover
Title:        Cormorant Garamond, display-sm, below image, --space-3 padding
Price:        DM Sans, body-sm, --color-muted
Hover:        image subtle scale (transform: scale(1.03)), transition 300ms ease
```

### Section Labels (Pre-headline)

Small uppercase DM Sans label above major section headings — acts as a category signal.

```
Font:         DM Sans 500, body-xs
Color:        --color-brick
Text-transform: uppercase
Letter-spacing: 0.15em
Margin-bottom: --space-3
```

Example: "Handcrafted in England" above "Every Bead a Prayer"

### Dividers

```css
hr {
  border: none;
  border-top: 1px solid var(--color-rule);
  margin: var(--space-8) auto;
  width: 64px;  /* Short centred rule used as section ornament */
}
```

---

## 7. Section-by-Section Specifications

### Hero

**Issues in mockup:** Text gets lost against image. CTA buttons are too close together. Subheading font size too small relative to headline.

**Corrected spec:**
- Full-bleed image, min-height 90vh
- Navy overlay at 55% opacity over image
- Headline: display-xl, Cormorant Garamond, white, max-width 600px
- Subhead: body-lg, DM Sans 300, white at 85% opacity, max-width 520px, margin-top `--space-4`
- CTA row: margin-top `--space-7`, gap `--space-4` between buttons
- Button 1 (Primary): "See the collection" — filled porcelain on navy
- Button 2 (Secondary): "About Anna" — outlined white
- Content padding-left: `--space-10` desktop, `--space-5` mobile

### Intro / Product Section

**Issues in mockup:** Section label missing, headline not prominent enough, body text too wide.

**Corrected spec:**
- Background: `--color-porcelain`
- Section label above headline: "Handcrafted with devotion"
- Headline: display-lg, centred
- Body: body-md, DM Sans 300, centred, max-width `--layout-text`, margin `0 auto`
- Product grid below: 3 columns, gap `--space-3`, images square
- CTA below grid: centred, primary button, margin-top `--space-7`

### Testimonial / Quote Section

**Issues in mockup:** Lorem ipsum placeholder. Background image present but not purposeful. Attribution unclear.

**Corrected spec:**
- Full-bleed background image (rosary close-up), dark overlay 55%
- Quote: display-sm, Cormorant Garamond italic, white, centred, max-width 680px
- Use proper curly quotes
- Attribution: DM Sans body-sm, white 70% opacity, margin-top `--space-4`, em dash prefix
- No box, no card — quote floats over the image

### About Section

**Issues in mockup:** Two columns unbalanced. "Community" sub-section feels disconnected. Twitter logo floating awkwardly.

**Corrected spec:**
- Background: `--color-warm-white`
- 2-col layout: image col 40%, text col 60%, gap `--space-8`
- Image: portrait crop, border-radius 2px
- Section label: "The maker" above "Hi, I'm Anna."
- Body text: DM Sans 300, body-md, max-width 560px
- "Read my full story" link: DM Sans 500, body-sm, --color-navy, underline on hover
- Community sub-section: separated by short `<hr>` rule, not a heading — flows as continuation of Anna's voice
- Twitter: inline text link + icon, not a floating logo

### Footer Quote

**Issues in mockup:** Quote at bottom feels tacked on — separate from footer, no clear section identity.

**Corrected spec:**
- Give it its own section: `--color-porcelain` bg, `--space-9` padding
- Short `<hr>` ornament above the quote
- Quote: display-sm, Cormorant Garamond italic, centred, max-width 640px
- Attribution: DM Sans body-sm, muted, centred

### Footer

**Corrected spec:**
- Background: `--color-navy`
- Logo: white version, left-aligned
- Tagline: DM Sans body-sm, porcelain 70%, below logo
- Nav links: right-aligned, DM Sans body-sm, porcelain, no uppercase
- Bottom bar: thin rule `rgba(255,255,255,0.15)`, copyright DM Sans body-xs, porcelain 50%

---

## 8. Interaction & Motion

Keep motion purposeful and restrained — this is a devotional brand, not a tech product.

```
Nav scroll transition:    background fade 300ms ease
Button hover:             color/bg transition 200ms ease
Product card hover:       image scale 300ms ease, shadow fade 300ms ease
Hero load:                headline fade-up 600ms ease, subhead 800ms, CTAs 1000ms
Section entry:            fade-up on scroll (IntersectionObserver), 500ms ease, 30px translateY
```

No parallax. No aggressive scroll-jacking. No looping animations.

---

## 9. Responsive Breakpoints

```css
/* Mobile first */
--bp-sm:  480px;   /* Large phones */
--bp-md:  768px;   /* Tablets / nav collapse */
--bp-lg:  1024px;  /* Small desktop */
--bp-xl:  1200px;  /* Max layout width */
```

Key responsive changes:
- Nav collapses to hamburger at `--bp-md`
- Product grid: 3-col → 2-col at `--bp-md` → 1-col at `--bp-sm`
- About section: 2-col → stacked at `--bp-md`, image above text
- Hero min-height: 90vh → 70vh on mobile
- Section padding: `--space-10` → `--space-8` on mobile

---

## 10. Quick Reference Cheatsheet

```
FONTS
  Headings:  Cormorant Garamond 400/500, normal or italic
  Body:      DM Sans 300/400/500

COLOURS
  Backgrounds:  #fcfaf5 (default), #F5F4F2 (alt), #0e3a80 (footer/nav)
  Text:         #1a1a1a (body), #6b6b6b (muted)
  Accents:      #c14953 (brick), #5b97ed (cornflower)
  Borders:      #e2ddd6

SPACING (8px base)
  Tight:    8–16px    (internal component)
  Medium:   24–48px   (between elements)
  Loose:    64–128px  (section padding)

BUTTONS
  Primary:    Navy bg, porcelain text, 2px radius, uppercase DM Sans
  Secondary:  Navy outline, navy text, same sizing

RULES
  Max content width:  1200px
  Max text width:     720px
  Body line-height:   1.8
  Heading line-height: 1.15
```
