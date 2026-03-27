# pepmaxx Design System
## Inspired by Huberman Lab — "Science should be accessible to everyone"

*Design reference: hubermanlab.com (redesigned by [DoubleUp](https://www.doubleup.agency/case-study/huberman-lab) + [8020](https://www.8020.inc/post/from-podcast-to-platform-crafting-huberman-labs-digital-home-in-webflow))*

---

## 1. Design Philosophy

Huberman Lab's design is guided by one core principle: **science should be accessible to everyone — not just academics or health experts.** The site feels approachable, intuitive, and elegant without sacrificing rigor or depth.

For pepmaxx, we adopt this same principle: **peptide research should be understandable by anyone**, from complete beginners to experienced biohackers. The design should never feel clinical or intimidating.

### Key Principles
- **Clarity over decoration** — every element earns its place
- **Content-first** — the research data is the hero, not the chrome
- **Progressive disclosure** — start simple, let users dig deeper
- **Trust through transparency** — every claim links to its source
- **Effortless navigation** — search, browse by topic, or explore related content

---

## 2. Color System

### Core Palette (from Huberman Lab screenshot analysis)

| Token | Value | Usage |
|-------|-------|-------|
| `--bg-primary` | `#FFFFFF` | Page background, navbar, modal |
| `--bg-surface` | `#F2F2F2` | Cards, input fields, interactive surfaces |
| `--bg-surface-hover` | `#E8E8E8` | Card hover state |
| `--bg-surface-active` | `#E0E0E0` | Card pressed/active state |
| `--text-primary` | `#1A1A1A` | Headings, primary content, active nav |
| `--text-secondary` | `#666666` | Body text, descriptions |
| `--text-muted` | `#999999` | Metadata, timestamps, tertiary info |
| `--text-on-accent` | `#FFFFFF` | Text on accent-colored backgrounds |
| `--accent-primary` | `#00B4D8` | CTAs, links, active states, primary buttons |
| `--accent-hover` | `#0096B7` | Accent hover state |
| `--border-subtle` | `#E8E8E8` | Dividers, navbar bottom border |
| `--border-none` | `transparent` | Cards have NO borders — use bg contrast |

### Semantic Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--color-success` | `#2E7D32` | Compatible interactions, positive states |
| `--color-warning` | `#E65100` | Monitor interactions, caution states |
| `--color-danger` | `#C62828` | Avoid interactions, error states |
| `--color-info` | `#1565C0` | Informational badges, links |

### Evidence Grade Colors

| Grade | Background | Text | Usage |
|-------|-----------|------|-------|
| A | `#E8F5E9` | `#2E7D32` | Strong human evidence |
| B | `#E3F2FD` | `#1565C0` | Good evidence |
| C | `#F5F5F5` | `#666666` | Moderate evidence |
| D | `#FFF3E0` | `#E65100` | Limited evidence |
| F | `#FFEBEE` | `#C62828` | Very limited / concerning |

### Compound Tier Colors

Used for left-border accents on compound cards and tier badge dots.

| Tier | Color | Dot |
|------|-------|-----|
| FDA Approved | `#2E7D32` | Green |
| Approved (Non-US) | `#1565C0` | Blue |
| Phase 2-3 Trials | `#00B4D8` | Cyan |
| Established Research | `#666666` | Gray |
| Emerging Research | `#E65100` | Orange |
| Peptide-Adjacent | `#7B1FA2` | Purple |
| Experimental/Limited | `#999999` | Light gray |

---

## 3. Typography

### Font Stack

Huberman Lab uses a clean system sans-serif with Helvetica/SF vibes. For pepmaxx:

```css
--font-primary: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', 'Helvetica Neue', Helvetica, Arial, sans-serif;
--font-mono: 'SF Mono', 'Fira Code', 'Cascadia Code', monospace;
```

### Type Scale

| Element | Size | Weight | Line Height | Letter Spacing | Color |
|---------|------|--------|-------------|----------------|-------|
| Hero heading (h1) | 48px | 700 | 1.1 | -0.02em | `--text-primary` |
| Section heading (h2) | 32px | 700 | 1.2 | -0.01em | `--text-primary` |
| Card heading (h3) | 20px | 600 | 1.3 | 0 | `--text-primary` |
| Subheading (h4) | 16px | 600 | 1.4 | 0 | `--text-primary` |
| Body | 16px | 400 | 1.6 | 0 | `--text-secondary` |
| Small body | 14px | 400 | 1.5 | 0 | `--text-secondary` |
| Caption/meta | 12px | 500 | 1.4 | 0.02em | `--text-muted` |
| Badge text | 11px | 600 | 1 | 0.04em | varies |
| Nav link | 15px | 500 | 1 | 0 | `--text-secondary` |
| Nav link active | 15px | 600 | 1 | 0 | `--text-primary` |

### Key Typography Rules
- **Headings are BOLD** — 700 weight, tight line-height, slightly negative letter-spacing
- **Body text is light** — 400 weight, generous line-height (1.6) for readability
- **NO italic** for emphasis — use weight or color instead
- **Uppercase** only for tiny labels (12px, letter-spacing 0.04em)
- **Text alignment** is always left-aligned (never center for body text)

---

## 4. Layout & Spacing

### Grid System

```css
--max-width: 1200px;        /* Content max width */
--gutter: 24px;             /* Grid gutter */
--section-padding: 80px 0;  /* Vertical section spacing */
--card-gap: 16px;           /* Gap between cards */
```

### Spacing Scale (8px base)

| Token | Value | Usage |
|-------|-------|-------|
| `--space-1` | 4px | Tight gaps (badge padding) |
| `--space-2` | 8px | Small gaps (between related items) |
| `--space-3` | 12px | Medium gaps (card internal padding) |
| `--space-4` | 16px | Standard gaps (between cards, list items) |
| `--space-5` | 24px | Section internal padding |
| `--space-6` | 32px | Between sections within a page |
| `--space-7` | 48px | Major section breaks |
| `--space-8` | 64px | Page section separators |
| `--space-9` | 80px | Hero/top-level section spacing |

### Layout Patterns

**Card Grid**: 4 columns on desktop, 2 on tablet, 1 on mobile
```css
display: grid;
grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
gap: 16px;
```

**Content + Sidebar**: 70/30 split on desktop, stacked on mobile
```css
display: grid;
grid-template-columns: 1fr 320px;
gap: 32px;
```

---

## 5. Components

### Navbar

```
┌─────────────────────────────────────────────────────┐
│  pepmaxx              Home   Browse   Stacks   ...  │
│─────────────────────────────────────────────────────│ ← 1px #E8E8E8 border
└─────────────────────────────────────────────────────┘
```

- Background: `#FFFFFF`
- Height: 64px
- Logo: `--text-primary` (#1A1A1A), 20px, weight 800, lowercase
- Nav links: `--text-secondary` (#666666), 15px, weight 500
- Active nav: `--text-primary` (#1A1A1A), weight 600
- Bottom border: 1px solid `#E8E8E8`
- No shadow
- Sticky on scroll

### Cards (Compound Cards)

```
┌──────────────────────────────────────┐
│ ▎ Semaglutide                    [A] │  ← 3px left border in tier color
│ ▎ FDA Approved · 47 studies          │
│ ▎                                    │
│ ▎ GLP-1 receptor agonist that...     │
└──────────────────────────────────────┘
```

- Background: `#FFFFFF`
- Container background (behind cards): `#F2F2F2` or page white
- Border: **none** (or very subtle 1px `#F0F0F0` if on white bg)
- Left accent: 3px solid `tier-color`
- Border-radius: 12px
- Padding: 20px
- Hover: background shifts to `#F8F8F8`
- Transition: `background 150ms ease`
- Cursor: pointer
- **NO box-shadow**

### Filter Chips

```
[ All ] [ FDA Approved ] [ Phase 2-3 ] [ Established ] ...
```

- Default: background `#F2F2F2`, color `#666666`, border: none
- Active: background `#1A1A1A`, color `#FFFFFF`
- Border-radius: 999px (pill)
- Padding: 8px 20px
- Font: 14px, weight 500
- Gap between chips: 8px
- Transition: `all 150ms ease`

### Buttons

**Primary (CTA)**
- Background: `#00B4D8`
- Color: `#FFFFFF`
- Border-radius: 999px (pill)
- Padding: 12px 28px
- Font: 15px, weight 600
- Hover: `#0096B7`
- No border, no shadow

**Secondary**
- Background: `#F2F2F2`
- Color: `#1A1A1A`
- Border-radius: 999px
- Padding: 10px 24px
- Font: 14px, weight 500
- Hover: `#E8E8E8`

### Grade Badges

```
[A]  [B]  [C]  [D]  [F]
```

- Border-radius: 8px
- Padding: 4px 10px
- Font: 12px, weight 700
- Background + text color per grade (see color table above)
- No border

### Tier Badges (on compound cards)

Small, understated pill:
- Font: 11px, weight 600, uppercase, letter-spacing 0.04em
- Background: tier color at 10% opacity
- Color: tier color
- Border-radius: 4px
- Padding: 2px 8px

### Search Input

```
┌──────────────────────────────────────────┐
│  🔍  What are you looking for?           │
└──────────────────────────────────────────┘
```

- Background: `#F2F2F2`
- Border: none
- Border-radius: 12px (or 999px for pill)
- Padding: 14px 20px 14px 44px (room for icon)
- Font: 16px, weight 400
- Placeholder color: `#999999`
- Focus: outline 2px solid `#00B4D8`
- No shadow

### Modal

```
┌──────────────────────────────────────┐
│  Semaglutide                      ✕  │
│  FDA Approved · Grade A              │
│──────────────────────────────────────│
│  Overview  Benefits  Studies  ...    │
│──────────────────────────────────────│
│                                      │
│  [Tab content area]                  │
│                                      │
└──────────────────────────────────────┘
```

- Background: `#FFFFFF`
- Border-radius: 16px
- Box-shadow: `0 20px 60px rgba(0,0,0,0.12)` (modals ARE the exception to no-shadow rule)
- Overlay: `rgba(0,0,0,0.5)`
- Max-width: 680px
- Max-height: 85vh
- Padding: 32px
- Close button: 32px circle, `#F2F2F2` background, `#666666` × icon

### Modal Tabs

- Font: 14px, weight 500
- Default: color `#999999`
- Active: color `#1A1A1A`, bottom border 2px solid `#1A1A1A`
- Gap between tabs: 24px
- Bottom divider: 1px solid `#E8E8E8`

### Study Cards (inside modal)

```
┌──────────────────────────────────────┐
│  [RCT]  2021 · NEJM                 │
│                                      │
│  STEP 1 Trial: Semaglutide 2.4mg    │
│  weekly for chronic weight mgmt      │
│                                      │
│  PMID: 34670107   n=1,961            │
└──────────────────────────────────────┘
```

- Background: `#F8F8F8`
- Border: none
- Border-left: 3px solid (study type color)
- Border-radius: 10px
- Padding: 16px
- Hover: background `#F2F2F2`
- Link: entire card clickable → PubMed

### Popular Stack Cards (homepage)

```
┌──────────────────────────────────────┐
│                                      │
│  The Wolverine Stack                 │
│                                      │
│  Maximum tissue healing and          │
│  recovery from injuries              │
│                                      │
│  bpc-157  ·  tb-500                  │
│                                      │
└──────────────────────────────────────┘
```

- Background: `#F2F2F2`
- Border: none
- Border-radius: 12px
- Padding: 24px
- Hover: background `#E8E8E8`
- Cursor: pointer
- **No shadow, no border**

---

## 6. Interactions & Animation

### Transitions
- All hover effects: `150ms ease`
- Modal open/close: `200ms ease-out` (fade + slight scale)
- Page transitions: none (instant — keeps it feeling fast)

### Hover States
- Cards: background lightens/darkens slightly
- Links: underline appears
- Buttons: background darkens
- Nav links: color shifts to `--text-primary`

### Focus States (Accessibility)
- All interactive elements: `outline: 2px solid #00B4D8; outline-offset: 2px;`
- Never remove focus outlines — just style them

### Touch Targets
- Minimum 44×44px for all clickable elements
- Cards have generous padding to expand hit area

---

## 7. Responsive Breakpoints

| Breakpoint | Width | Layout Changes |
|-----------|-------|---------------|
| Desktop | ≥1024px | 4-col grid, sidebar visible, full nav |
| Tablet | 768-1023px | 2-col grid, sidebar collapses, full nav |
| Mobile | <768px | 1-col grid, hamburger nav, stacked layout |

### Mobile-Specific Rules
- Horizontal scroll for filter chips (with snap)
- Modal goes full-screen on mobile
- Stack Finder goals become 2-column
- Larger touch targets (48px minimum)

---

## 8. Iconography

Huberman Lab uses simple line icons in their topic cards. For pepmaxx:

- Use **no icons** on compound cards (data-dense, icons add noise)
- Use minimal icons on category/topic selector if added later
- Icons should be: 24px, 1.5px stroke, `#666666` color
- Source: Lucide Icons or Phosphor Icons (open source, consistent)

---

## 9. Content Patterns

### Information Hierarchy on Compound Cards
1. **Name** — largest, boldest (20px, 600)
2. **Tier badge** — small pill, understated
3. **Stats** — study count, grade badge
4. **Description** — truncated to 2 lines
5. **CTA** — "View research data →" in accent color

### Modal Information Hierarchy
1. **Title + tier + grade** — header area
2. **Tab navigation** — Overview, Benefits, Studies, Trials, Safety
3. **Primary content** — fills the tab area
4. **Sources** — always linked, always at the bottom of each section

### Empty States
- Clean illustration or icon (optional)
- Short helpful message
- CTA to take action
- Example: "No compounds match your search. Try broadening your filters."

---

## 10. Design Don'ts

- ❌ No gradients anywhere
- ❌ No decorative borders on cards (use background contrast)
- ❌ No box-shadows on cards (flat design, shadows only on modals)
- ❌ No colored backgrounds for sections (white + white/gray alternation only)
- ❌ No all-caps headings (only tiny labels)
- ❌ No more than 2 accent colors on screen at once
- ❌ No emoji in the UI (use subtle colored dots or small icons instead)
- ❌ No underlined links by default (underline on hover only)
- ❌ No centered body text
- ❌ No animated decorations or parallax

---

## 11. Accessibility Requirements

- **WCAG 2.1 AA** compliance minimum
- All text ≥ 4.5:1 contrast ratio against background
- Large text (≥24px or ≥19px bold) ≥ 3:1 contrast ratio
- Focus-visible on all interactive elements
- All images have alt text
- Modal traps focus when open
- Escape key closes modal
- Skip-to-content link
- Semantic HTML (nav, main, section, article)
- Screen reader announcements for dynamic content

### Contrast Verification
| Combo | Ratio | Pass? |
|-------|-------|-------|
| #1A1A1A on #FFFFFF | 17.4:1 | ✅ AAA |
| #666666 on #FFFFFF | 5.74:1 | ✅ AA |
| #999999 on #FFFFFF | 2.85:1 | ⚠️ Fail — use only for decorative/non-essential |
| #00B4D8 on #FFFFFF | 2.81:1 | ⚠️ Fail for small text — use as bg with white text instead |
| #FFFFFF on #00B4D8 | 2.81:1 | ⚠️ Marginal — use #0096B7 for better contrast (3.4:1) |
| #FFFFFF on #1A1A1A | 17.4:1 | ✅ AAA |
| #2E7D32 on #E8F5E9 | 4.8:1 | ✅ AA |
| #1565C0 on #E3F2FD | 5.2:1 | ✅ AA |
| #C62828 on #FFEBEE | 5.7:1 | ✅ AA |

**Important**: `#00B4D8` cyan fails AA as text on white. Use it ONLY as:
- Background with white text (buttons)
- Decorative accent (icons, borders)
- For text links, use `#0096B7` (darker cyan, 3.4:1) or `#007B94` (4.5:1 AA pass)

---

## 12. Implementation Notes

### CSS Custom Properties
```css
:root {
  /* Backgrounds */
  --bg-primary: #FFFFFF;
  --bg-surface: #F2F2F2;
  --bg-surface-hover: #E8E8E8;
  --bg-elevated: #F8F8F8;

  /* Text */
  --text-primary: #1A1A1A;
  --text-secondary: #666666;
  --text-muted: #999999;

  /* Accent */
  --accent: #00B4D8;
  --accent-hover: #0096B7;
  --accent-text: #007B94; /* AA-safe for text links */

  /* Borders */
  --border: #E8E8E8;
  --border-focus: #00B4D8;

  /* Radius */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-pill: 999px;

  /* Shadows (modal only) */
  --shadow-modal: 0 20px 60px rgba(0,0,0,0.12);

  /* Typography */
  --font: -apple-system, BlinkMacSystemFont, 'SF Pro Display',
          'Segoe UI', 'Helvetica Neue', Helvetica, Arial, sans-serif;

  /* Transitions */
  --transition: 150ms ease;
}
```

### File: pepmaxx-preview.html
This design system should be applied to the single-file HTML preview. All CSS custom properties should be defined in the `<style>` block, and JavaScript template strings should reference the same values consistently.
