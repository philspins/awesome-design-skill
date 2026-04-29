# BuildDistributedSystem — Networker Track

**URL**: https://builddistributedsystem.com/tracks/networker
**Archetype**: `cinematic-dark` / `developer-minimal`

---

## 1) Visual Theme & Atmosphere

A deep-dark, neon-accented visual system built around immersive near-black surfaces and a single vivid teal interactive color. The page projects authority and forward momentum through dramatic contrast and deliberate use of glowing accents — effects that would be equally at home on a marketing site, a blog, a product landing page, or a company info page.

- **Product context**: Any content-forward site that wants a confident, modern dark aesthetic with strong visual hierarchy and glowing accent interactivity.
- **Brand mood keywords**: nocturnal, energetic, precise, luminous, confident, immersive
- **Density strategy**: balanced — generous whitespace around content blocks, with accent color and subtle light effects providing richness without clutter
- **Personality contrast**: dramatic darkness + approachable warmth from the teal accent; imposing without being cold

---

## 2) Color Palette & Roles

| Token | Hex | Role |
|---|---|---|
| `bg.base` | `#0B0E1A` | Page / outermost background |
| `bg.surface` | `#111827` | Card and panel backgrounds |
| `bg.elevated` | `#1A2235` | Elevated panels, modals, popovers |
| `bg.subtle` | `#1E2D45` | Hover surfaces, code blocks |
| `fg.primary` | `#E8EDF5` | Primary text |
| `fg.secondary` | `#8B9BB4` | Secondary labels, metadata |
| `fg.muted` | `#4E5F78` | Placeholder, disabled, fine print |
| `accent.primary` | `#00D4FF` | Teal — primary interactive, links, CTA, active glow |
| `accent.secondary` | `#7C3AED` | Violet — secondary brand color, category / tag badges |
| `accent.highlight` | `#F97316` | Orange — emphasis callouts, warning states |
| `accent.positive` | `#10B981` | Green — positive / live / success indicators |
| `border.default` | `#1E3A5F` | Standard borders |
| `border.glow` | `rgba(0,212,255,0.35)` | Neon glow border on focus / hover |
| `success` | `#10B981` | Success, confirmed, positive |
| `warning` | `#F97316` | Warning, attention required |
| `error` | `#EF4444` | Error, failed, destructive |
| `info` | `#3B82F6` | Info, in-progress |

**Contrast notes**:
- `fg.primary #E8EDF5` on `bg.base #0B0E1A`: 16.2:1 — AAA ✓
- `accent.primary #00D4FF` on `bg.surface #111827`: 10.4:1 — AAA ✓
- `fg.secondary #8B9BB4` on `bg.surface #111827`: 4.6:1 — AA ✓ (body minimum)
- Never use `fg.muted` for interactive text — contrast is below 3:1 on dark surfaces.

---

## 3) Typography Rules

- **Display family**: `"Inter"` (semibold/bold headings) — clean geometric sans-serif that reads with authority at large display sizes
- **Body family**: `"Inter"`, fallback `system-ui, -apple-system, sans-serif`
- **Monospace family**: `"JetBrains Mono"`, fallback `"Fira Code", "Cascadia Code", monospace` — used sparingly for code snippets, dates, numeric data, and any content that benefits from fixed-width alignment

| Role | Size | Weight | Line Height | Use |
|---|---:|---:|---:|---|
| Hero / Display | 48px | 700 | 1.1 | Hero section headings |
| H1 | 36px | 700 | 1.15 | Page titles |
| H2 | 28px | 600 | 1.2 | Section headings |
| H3 | 22px | 600 | 1.25 | Card / panel headings |
| H4 | 18px | 600 | 1.3 | Sub-section headings |
| Body Large | 18px | 400 | 1.6 | Intro paragraphs |
| Body | 16px | 400 | 1.6 | General content |
| Body Small | 14px | 400 | 1.5 | Secondary content, descriptions |
| Caption | 12px | 400 | 1.4 | Timestamps, metadata labels |
| Code / Mono | 14px | 400 | 1.6 | Inline code, terminal blocks |
| Label / Badge | 11px | 600 | 1 | Category badges, status labels (uppercase) |

**Rules**:
- Monospace is reserved for code blocks, dates/timestamps, numeric data columns, and any content where fixed-width alignment adds clarity. Do not apply it to prose.
- Heading color defaults to `fg.primary`; interactive headings may use `accent.primary` with a hover state.
- Never italicise headings; reserve italics for inline asides or pull-quotes only.

---

## 4) Component Stylings

### Buttons

| Variant | Background | Border | Text | Radius | Use |
|---|---|---|---|---|---|
| Primary | `accent.primary #00D4FF` | none | `bg.base #0B0E1A` | 6px | Primary CTA, main action |
| Secondary | transparent | `1.5px solid #00D4FF` | `#00D4FF` | 6px | Secondary actions |
| Ghost | transparent | `1px solid #1E3A5F` | `fg.primary` | 6px | Tertiary, nav actions |
| Danger | `#EF4444` | none | white | 6px | Destructive confirmations |
| Disabled | `#1A2235` | `1px solid #1E3A5F` | `fg.muted` | 6px | — |

- Hover (Primary): `box-shadow: 0 0 12px rgba(0,212,255,0.45)` — glow effect
- Hover (Secondary): background fills to `rgba(0,212,255,0.08)`
- Focus ring: `outline: 2px solid #00D4FF; outline-offset: 2px`
- Minimum size: 36px height, 12px horizontal padding; 44px for touch targets

### Inputs

- Background: `bg.subtle #1E2D45`
- Border: `1px solid #1E3A5F`
- Border focus: `1.5px solid #00D4FF` + glow `0 0 0 3px rgba(0,212,255,0.2)`
- Text: `fg.primary`
- Placeholder: `fg.muted`
- Radius: 6px
- Height: 40px

### Cards / Content Panels

- Background: `bg.surface #111827`
- Border: `1px solid #1E3A5F`
- Radius: 10px
- Padding: 24px
- Hover: border transitions to `border.glow`, subtle `translateY(-2px)` lift + `box-shadow: 0 8px 32px rgba(0,0,0,0.4)`
- Optional status indicator (top-left): small circle `12px` in `accent.positive` green, with a pulsing ring animation for "live" or "active" states
- Cards accommodate any content shape: article previews, feature lists, team members, product tiers — the visual treatment is content-agnostic

### Navigation

- Top nav: sticky, `bg.base #0B0E1A`, `border-bottom: 1px solid #1E3A5F`, height 64px
- Logo left, nav links centered (desktop), CTA button right
- Active nav link: `accent.primary` color + 2px underline
- Hover: `accent.primary` color fade-in
- Mobile: hamburger → full-height overlay drawer, dark bg, links stacked at 20px body
- Breadcrumb: `fg.muted` / `fg.secondary`, monospace separator `›`

### Tables / Data Views

- Header row: `bg.elevated #1A2235`, `fg.secondary`, uppercase 11px 600 weight
- Row: `bg.surface`, `1px solid #1E3A5F` bottom border
- Row hover: `bg.subtle`
- Numeric / date columns: JetBrains Mono 14px
- Status cell: color dot + text label (never color alone)

---

## 5) Layout Principles

- **Grid model**: 12-column CSS Grid; gutter 24px; content pages use a 2-up or 3-up card grid on wide, single column on mobile
- **Container widths**:
  - Max content width: `1280px`
  - Narrow editorial: `768px` (long-form body copy, blog posts, detail pages)
  - Full-bleed: hero sections and decorative background pattern sections only
- **Spacing scale** (8px base):
  `4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 · 128px`
- **Rhythm / whitespace rules**:
  - Section padding: `96px` top/bottom on desktop, `64px` on mobile
  - Card gap: `24px`
  - Heading margin-bottom: half the heading size (e.g., H2 28px → 14px margin)
  - Body paragraphs: `1em` bottom margin
  - Full-bleed decorative sections may extend to full viewport width; constrain any text overlay to `768px`

---

## 6) Depth & Elevation

| Level | Background | Border | Shadow / Effect | Usage |
|---|---|---|---|---|
| 0 | `#0B0E1A` | — | — | Page canvas |
| 1 | `#111827` | `1px solid #1E3A5F` | — | Cards, panels |
| 2 | `#1A2235` | `1px solid #1E3A5F` | `0 4px 16px rgba(0,0,0,0.4)` | Elevated cards, hover state |
| 3 | `#1E2D45` | `1px solid rgba(0,212,255,0.35)` | `0 8px 32px rgba(0,0,0,0.5)` | Modals, dropdowns |
| Glow | — | `border.glow` | `0 0 20px rgba(0,212,255,0.2)` | Active / highlighted elements, CTA hover |

**Blur / glass rules**:
- Frosted glass (`backdrop-filter: blur(12px)`) is allowed only for the sticky nav bar and modal overlays; never on content cards.
- Decorative background sections may use `opacity: 0.08–0.15` SVG pattern overlays (dot grid, geometric mesh, or abstract lines) — never full-opacity graphics that sit behind body text.

**Glow effects**:
- Teal glow (`accent.primary`) for active/hover interactive elements.
- Orange glow (`accent.highlight`) for call-to-action emphasis only.
- Do not stack multiple glow layers — one glow per element maximum.

---

## 7) Do's and Don'ts

**Do**
- Apply teal glow exclusively to primary interactive elements — it is the system's key interactive signal.
- Use color + shape + label for all status indicators (accessibility).
- Provide a visible, high-contrast focus ring on every interactive element.
- Animate only with purpose: pulsing rings for "live" or "active" states, subtle card lift on hover, smooth color transitions (150–200ms ease).
- Keep decorative background graphics at very low opacity (≤0.12) — they are atmospheric, not informational.
- Use the monospace family for code snippets, numeric data, and dates where alignment matters.

**Don't**
- Do not use light mode — this system is dark-only; no light theme.
- Do not use more than one glow effect on a single element at a time.
- Do not use `accent.highlight` (orange) for anything other than emphasis callouts or warnings — never as the main brand color.
- Do not use thin (< 400 weight) text below 14px on dark surfaces — legibility degrades.
- Do not add decorative gradients to text (gradient headings) — reserve gradients for background surfaces and decorative elements only.
- Do not use the violet `accent.secondary` for primary CTAs — it competes with the teal interactive signal.
- Do not represent status with color alone — always pair with an icon or label.

---

## 8) Responsive Behavior

| Breakpoint | Width | Behavior |
|---|---|---|
| `xs` | < 480px | Single column, full-width cards, 16px body |
| `sm` | 480–767px | Single column, slight padding (16px horizontal) |
| `md` | 768–1023px | 2-column card grid, nav condenses |
| `lg` | 1024–1279px | 2–3 column grid, full nav |
| `xl` | ≥ 1280px | 3-column card grid, max-width container |

- **Touch target minimum**: 44×44px for all interactive controls
- **Layout collapse behavior**:
  - 3-column card grid → 2-column at `md` → single column at `sm`
  - Sticky nav collapses to hamburger menu at `md` and below
  - Full-bleed decorative sections stack vertically; background graphics move above text on mobile
  - Tables gain horizontal scroll wrapper at `sm`
- **Mobile nav pattern**: Hamburger → slide-in full-screen overlay, dark background (`bg.base`), `bg.elevated` dividers between sections, close button top-right

---

## 9) Agent Prompt Guide

**One-shot prompt for generating a page from this design system:**
> Build a page using the BuildDistributedSystem Networker visual style. Dark base `#0B0E1A`, surface cards `#111827`, elevated panels `#1A2235`. Primary interactive teal `#00D4FF` with glow hover (`box-shadow: 0 0 12px rgba(0,212,255,0.45)`). Violet `#7C3AED` for category / tag badges. Orange `#F97316` for callout emphasis and warnings only. Inter for all prose and headings; JetBrains Mono for code snippets, numeric data, and dates. H1 36px/700, body 16px/400, mono 14px/400. Cards: 10px radius, `1px solid #1E3A5F` border, 24px padding, hover lifts 2px with teal glow border. Nav: sticky 64px, dark bg, teal active underline. Spacing 8px base. 12-column grid, 1280px max-width. Focus ring: `2px solid #00D4FF, offset 2px`. No light mode. No decorative gradients on text. Status indicators always pair color with label.

**Negative prompt (what to avoid):**
- No light mode or light-colored backgrounds
- No gradient text effects
- No multiple stacked glows on a single element
- No orange as a primary or brand color (callouts and warnings only)
- No color-only status indicators
- No rounded corners > 12px (cards) or > 6px (buttons/inputs)
- No serif or slab typography

**Fast checklist for review:**
- [ ] All backgrounds are dark (`#0B0E1A` / `#111827` / `#1A2235`)
- [ ] Interactive elements use teal `#00D4FF` with glow on hover/focus
- [ ] Monospace is used only for code, numeric data, and dates — not prose
- [ ] Focus rings are visible and 2px teal
- [ ] Status indicators use color + label (not color alone)
- [ ] No element has more than one active glow effect simultaneously
- [ ] Card hover applies border glow + 2px lift
- [ ] Orange is used only for callout emphasis or warnings, never as the primary CTA color
- [ ] Touch targets ≥ 44px on all interactive controls
- [ ] Background decorative graphics are ≤ 12% opacity
