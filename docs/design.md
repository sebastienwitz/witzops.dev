# Design

Visual and UX design direction for witzops.dev.

## Identity

The site should feel like an engineering notebook, not a marketing page.
It prioritizes readability and information density over visual
decoration. Think field notes from someone running real infrastructure.

## Typography

- **Primary**: IBM Plex Sans (sans-serif for body and UI).
- **Monospace**: IBM Plex Mono (for code, labels, data).
- **Scale**: Clamped heading sizes (`clamp()`) so titles remain readable
  from mobile to wide displays.

## Color palette

A dark-ship engineering palette — high contrast, cool blues, amber
accents.

| Token         | Hex       | Usage                       |
|---------------|-----------|-----------------------------|
| `--bg`        | `#0b1116` | Page background             |
| `--bg-elevated` | `#121922` | Cards, surfaces             |
| `--bg-muted`  | `#0f151d` | Inactive regions            |
| `--line`      | `#213040` | Subtle borders              |
| `--line-strong` | `#31465d` | Focused borders             |
| `--text`      | `#e7edf4` | Body copy                   |
| `--text-soft` | `#9fb0c2` | Secondary text, muted labels|
| `--accent`    | `#8fb7de` | Links, highlights           |
| `--accent-soft` | `rgba(143, 183, 222, 0.14)` | Hover backgrounds |

### Background treatment

```css
background:
  radial-gradient(circle at top, rgba(74, 97, 123, 0.18), transparent 30%),
  linear-gradient(180deg, #0a0f14 0%, var(--bg) 100%);
```

A subtle blue bloom at the top of the page, fading into the dark
base. Gives depth without being decorative.

## Layout

- **Max content width**: 72rem (`--content-width`).
- **Centered**, with responsive padding (1rem on mobile, 2rem on desktop).
- **Sticky header** with blurred backdrop for navigation context while
  scrolling.
- **Footer** at the bottom of every page.
- No sidebar. Single-column content layout.

## Component vocabulary

### Surfaces (cards)

```css
.surface {
  border: 1px solid var(--line);
  border-radius: var(--radius);           /* 0.85rem */
  background: linear-gradient(180deg,
    rgba(18, 25, 34, 0.92),
    rgba(13, 19, 27, 0.96));
  box-shadow: var(--shadow);              /* 0 16px 48px rgba(0,0,0,0.22) */
}
```

Cards use a subtle gradient and shadow to lift them off the background.

### Section eyebrows

```css
.section-eyebrow {
  color: var(--accent);
  font-family: var(--font-mono);
  font-size: 0.8rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
```

A small mono label with a leading line that introduces sections. Used
sparingly.

### Navigation

Pill-shaped links in the header. Active and hover states use a border +
background highlight. Works as a horizontal row on desktop, stacks on
mobile.

## Responsive behavior

- Single breakpoint at 48rem (768px).
- Header switches from row to column layout.
- Hero grid collapses from two columns to one.
- Content width tightens from 2rem padding to 1.25rem.

## What to avoid

- Gradient-heavy hero sections with large illustrations.
- Animated counters, carousels, or scroll-triggered effects.
- Decorative icons for every section.
- Overly branded color palette (neon, rainbow, gradients everywhere).
- Generic tech startup aesthetic (white backgrounds, blue buttons,
  illustrated heroes).
