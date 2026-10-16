# NoxCipher Brand Guide

Reference for the NoxCipher logo, colors and type. Everything here matches `index.html` and `noxcipher-mark.svg`.

---

## 1. Logo

### Concept
The mark is a geometric **N** cut into three horizontal bands. The middle band is shifted to the right, the way a Caesar cipher shifts letters along the alphabet. The outer bands are off-white and the shifted band is mint.

- **N** stands for *Nox* (night).
- **The shift** stands for *cipher*.
- One mark carries the full name, with no shields, locks or glowing X.

### Construction (48 × 48 grid)

| Element | Value |
|---|---|
| Canvas | 48 × 48 units |
| N outline | `M10 8H16L32 30V8H38V40H32L16 18V40H10Z` |
| Stroke weight | 6 units (verticals and diagonal) |
| Top band | y 0 – 18 |
| Middle band | y 20 – 28, shifted **+4** on x |
| Bottom band | y 30 – 48 |
| Gaps between bands | 2 units |

For small sizes (favicon at 16–32 px), reduce the shift to **+3** so the band stays attached to the letter.

### SVG source

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48">
  <defs>
    <path id="n" d="M10 8H16L32 30V8H38V40H32L16 18V40H10Z"/>
    <clipPath id="top"><rect x="0" y="0" width="48" height="18"/></clipPath>
    <clipPath id="mid"><rect x="0" y="20" width="48" height="8"/></clipPath>
    <clipPath id="bot"><rect x="0" y="30" width="48" height="18"/></clipPath>
  </defs>
  <g clip-path="url(#top)"><use href="#n" fill="#EDEDEA"/></g>
  <g clip-path="url(#mid)"><use href="#n" fill="#3DFFA2" transform="translate(4 0)"/></g>
  <g clip-path="url(#bot)"><use href="#n" fill="#EDEDEA"/></g>
</svg>
```

### Wordmark
- Written lowercase: **nox**cipher.
- "nox" in Geist SemiBold (600), Text color `#EDEDEA`.
- "cipher" in Geist Medium (500), Muted color `#8B9094`.
- Letter spacing: −0.01em.
- In running text, write the name as **NoxCipher**.

### Lockup
- Mark on the left, wordmark on the right.
- Gap between mark and wordmark: 1/3 of the mark height (30 px mark → 10 px gap).
- Wordmark cap height is about 55% of the mark height.

### Clear space and minimum size
- Clear space: at least the width of one N stroke (6/48 of the mark) on every side.
- Minimum mark size: 16 px (use the +3 shift version).
- Minimum lockup width: 100 px.

### Color versions

| Version | Outer bands | Middle band | Background |
|---|---|---|---|
| Primary (dark) | `#EDEDEA` | `#3DFFA2` | `#08090A` |
| On light | `#08090A` | `#0FA968` | `#FFFFFF` / `#EDEDEA` |
| Mono light | `#EDEDEA` | `#EDEDEA` | dark |
| Mono dark | `#08090A` | `#08090A` | light |

On light backgrounds, use the darker mint `#0FA968`, because `#3DFFA2` is too low-contrast on white.

### Don'ts
- Don't add glow, gradients, bevels or drop shadows to the mark.
- Don't move the shift to the top or bottom band, or shift it left.
- Don't rotate, stretch or outline the mark.
- Don't put the full-strength mint mark on busy photos; use a mono version instead.
- Don't set the wordmark in all caps or with wide letter spacing.

---

## 2. Color palette

Dark-first, neutral surfaces, **one accent**. Mint is a signal color: use it for the brand mark, primary buttons, "good/healthy" states and small highlights, never for large fills.

### Core

| Token | Hex | Use |
|---|---|---|
| `--bg` | `#08090A` | Page background |
| `--surface` | `#0E1011` | Cards, panels, dashboard frame |
| `--surface-2` | `#131617` | Tags, selected tabs |
| Panel inner | `#0B0D0E` | KPI tiles and chart panels inside dashboards |
| Code / terminal | `#060707` | Code blocks, terminal |
| `--line` | `rgba(255,255,255,.08)` | Default borders and dividers |
| `--line-2` | `rgba(255,255,255,.14)` | Emphasised borders, buttons |
| `--text` | `#EDEDEA` | Primary text (warm off-white) |
| `--muted` | `#8B9094` | Body copy, secondary text |
| `--faint` | `#5B6064` | Labels, axis text, footnotes |
| `--accent` | `#3DFFA2` | Brand mint: logo, primary CTA, success |
| Accent hover | `#6BFFBB` | Primary button hover |
| `--accent-dim` | `rgba(61,255,162,.10)` | Accent backgrounds (tags, selected state) |
| Text on accent | `#04140B` | Text on mint buttons |

### Data and status colors
Used only in dashboards, charts and status pills.

| Name | Hex | Meaning |
|---|---|---|
| Red | `#FF6B6B` (text `#FF7A7A`) | High severity, risky action |
| Amber | `#FFB547` | Medium severity, warning, metrics trending the wrong way |
| Blue | `#7FB8FF` | Low severity, informational, second data series |
| Mint | `#3DFFA2` | Healthy, contained, first data series |

Status pill backgrounds are the same color at 10% opacity, e.g. `rgba(255,107,107,.10)`.

**Vendor series convention:** FortiGate = Mint, Palo Alto = Blue.

### Code syntax colors (KQL blocks)

| Element | Hex |
|---|---|
| Table name | `#3DFFA2` |
| Keyword / operator | `#7FB8FF` |
| String | `#E6C07B` |
| Number | `#F78C6C` |
| Comment | `#5B6064` |

### CSS tokens (copy-paste)

```css
:root {
  --bg: #08090a;
  --surface: #0e1011;
  --surface-2: #131617;
  --line: rgba(255,255,255,.08);
  --line-2: rgba(255,255,255,.14);
  --text: #ededea;
  --muted: #8b9094;
  --faint: #5b6064;
  --accent: #3dffa2;
  --accent-dim: rgba(61,255,162,.10);
  --warn: #ffb547;
  --danger: #ff6b6b;
  --info: #7fb8ff;
}
```

---

## 3. Typography

| Role | Font | Weight | Notes |
|---|---|---|---|
| Headlines | Geist | 600 | Tight tracking: −0.035em to −0.045em, line-height 0.95–1.02 |
| Body | Geist | 400 | 16–18 px, line-height 1.6 |
| UI / buttons | Geist | 500–600 | 14–15 px |
| Labels, eyebrows | Geist Mono | 500 | 11–12 px, UPPERCASE, +0.08em tracking |
| Code, terminal, data | Geist Mono | 400 | 12–13 px |

Both fonts are free on Google Fonts:

```html
<link href="https://fonts.googleapis.com/css2?family=Geist:wght@400;500;600;700&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
```

Fallbacks: `system-ui, sans-serif` and `ui-monospace, monospace`.

---

## 4. UI conventions

- **Corner radius:** 8 px for buttons, 12–14 px for cards and panels, 16–18 px for large frames.
- **Borders over shadows:** separate surfaces with 1 px `--line` borders. Keep shadows for the one hero card.
- **Accent budget:** about one mint element per screen area. If everything glows, nothing stands out.
- **Headline pattern:** short statements ending in a mint period: Detect**.** Defend**.** Automate**.**
- **Background:** subtle dot grid (28 px) fading out from the top. No scanlines and no neon gradients.
- **Data honesty:** every demo, chart and terminal is labelled as synthetic. Use documentation IP ranges (`192.0.2.0/24`, `198.51.100.0/24`, `203.0.113.0/24`) and `contoso.example` accounts.

---

## 5. Voice

- Plain and specific: "Detections that hold up in production", not "next-generation cyber resilience".
- Name the real tools (Sentinel, Defender XDR, FortiGate, PAN-OS, KQL).
- Short sentences. No hype words like "premium", "cutting-edge" or "world-class".
- Never put notes about the design itself into page copy.

---

## 6. Files

| File | Contents |
|---|---|
| `noxcipher-mark.svg` | Logo mark, primary dark version |
| `index.html` | Landing page; the logo is defined once as an SVG `<symbol id="nx-mark">` and reused in the header and footer |
