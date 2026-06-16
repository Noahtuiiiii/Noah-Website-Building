# Noah McGill — Design System

A personal-brand design system for **Noah McGill**, a PMO & Business Analyst
working in **ANZ Banking Operations**, holder of a **Master of Project Management
(RMIT)**. The system expresses a professional who brings order to complex
delivery: calm, structured, editorial, and quietly precise.

> **Namespace:** components are exposed at `window.NoahMcGillDesignSystem_b220d4`.
> Consumers link one file — `styles.css` — for all tokens and webfonts.

---

## Sources & provenance

This system was built from three **aesthetic reference** screenshots supplied by
the client (not Noah's existing products — there was no prior codebase or Figma):

1. **SUUPAA** (suupaa.au) — clean white minimalism, heavy sans wordmark with a
   serif-italic accent ("Menu"), monospace metadata footer (INSTAGRAM / TIKTOK /
   LOCATION), soft neumorphic pill buttons, a single hot accent.
2. **REF** (ref.digital) — bold geometric grotesque logo, warm sand neutral +
   deep blue blocks, large confident statement type ("Move fast, build to last.").
3. **Mohamed Shehata** (portfolio) — floating glass **pill navigation**, generous
   contrast, a personal-brand structure.

Brief: *"Use a minimal and clean website style."*

**Synthesis:** a warm-paper, ink-on-light editorial system. Heavy **Space Grotesk**
display, **Space Mono** for the structured "analyst" voice (labels, metadata,
nav), **Instrument Serif** italic for sparing editorial emphasis, and one
restrained **cobalt signal** accent.

---

## Content fundamentals

**Voice:** clear, structured, measured, pragmatic — the register of a senior
analyst who makes complex delivery legible. Confident without hype.

- **Person:** first person ("I bring order to complex delivery"), warm but
  professional. Speaks *to* the reader plainly ("Have a programme that needs
  steadying?").
- **Casing:** Sentence case for prose and headlines. **UPPERCASE** reserved for
  Space Mono labels, eyebrows, nav, and metadata (with wide tracking).
- **Numbers as language:** the system leans on quantified outcomes
  (`98% on-time`, `$120M portfolio`, `40 wks`). Metrics are first-class content.
- **Structure markers:** mono eyebrows are indexed (`01 / Profile`,
  `02 / Selected work`) and use `KEY /` prefixes for data (`ROLE /`, `SECTOR /`).
- **Editorial accent:** one serif-italic word per statement, maximum — used to
  soften an otherwise structural sentence (*order*, *last*, *steadying?*).
- **No emoji.** No exclamatory marketing. No filler. Every line earns its place.

**Examples**
- Hero: "I bring *order* to complex delivery."
- Sub: "I help banking and operations teams turn ambiguous programmes into clear
  plans, measured governance, and outcomes everyone can see."
- CTA labels: "Let's talk", "View work", "Submit" (mono, uppercase on render).

---

## Visual foundations

**Palette.** Warm, paper-based and low-glare.
- *Surfaces:* warm paper neutrals (`--paper-0/1/2`) with a sand secondary
  (`--stone-1/2`) echoing REF. Near-black warm **ink** surfaces for contrast
  moments (footers, contact panel).
- *Text:* warm near-black `--ink-1` → muted `--ink-3`. Emphasis is carried by
  **weight, not colour**.
- *Accent:* a single cobalt **signal** (`#2233E6`) used sparingly — the primary
  CTA, one accent word's period, active states, metric deltas.
- *Semantics:* muted, professional (`on track` green, `at risk` amber, `blocked`
  red, `info` blue) — always as tinted chips, never loud.

**Type.** `Space Grotesk` (geometric grotesque) for display/UI, set tight
(`-0.03em`) at large sizes; `Space Mono` for every label, eyebrow, nav item and
datum (uppercase, `0.10–0.24em` tracking); `Instrument Serif` italic for accents
only — never body. Display runs to 88px; body 16px at `1.65` line-height on a
~680px measure.

**Spacing & layout.** 8px base grid, generous editorial whitespace. Max content
width 1240px; reading measure 680px. Sticky pill nav floats 18px from the top.
Content is centered with comfortable 24px gutters.

**Backgrounds.** Flat warm paper — **no gradients**, no photographic hero washes,
no textures or patterns. Contrast is created by swapping to ink surfaces, not by
decoration. (The reference brands' 3D product renders are *their* content; Noah's
system stays typographic.)

**Borders.** Hairlines (`--line-1`) do most structural work; stronger borders
(`--line-2`) outline inputs and stone fills. Corner radii are restrained
(4/8/14/22px); **pills (999px) are reserved for actions** (buttons, nav, tags).

**Shadows.** Soft, warm-tinted, low-contrast — `shadow-sm` resting, `shadow-md`
on lift. A `shadow-soft` (with inner highlight) is available for the
SUUPAA-style neumorphic pill if needed. Shadow is for gentle elevation only;
never heavy drop-shadows.

**Motion.** Calm and confident. Default ease `cubic-bezier(0.22,1,0.36,1)`,
`120–360ms`. Screen changes fade-and-rise 8px. **Hover:** cards lift 2px +
deepen shadow; nav items fill with stone. **Press:** buttons scale to `0.97`
(tactile, no colour flash). No bounces, no infinite loops, respects
`prefers-reduced-motion` where animated.

**Transparency & blur.** Used in exactly one place — the floating nav uses
`rgba(paper)` + `backdrop-filter: blur(14px)` so content scrolls under it.

**Imagery.** The brand is **typographic, not photographic**. Identity is a bold
wordmark + `NM` monogram; people are represented by initials avatars, not photos.
If photography is ever added, keep it warm-neutral and understated.

---

## Iconography

**System:** [Lucide](https://lucide.dev) line icons, loaded from CDN
(`unpkg.com/lucide@0.456.0`). Stroke weight **1.75**, sized 16–24px, drawn in
`currentColor` so they inherit text colour (ink, muted, or accent).

- Used sparingly and functionally — directional (`arrow-right`,
  `arrow-up-right`), contact (`mail`, `linkedin`, `map-pin`), status (`check`,
  `trending-up`), structure (`file-text`, `calendar`, `menu`).
- **Never emoji.** No multicolour or filled icon sets. No hand-drawn SVG.
- In React, use the kit's `Icon` helper (`<Icon name="arrow-right" />`) and call
  `lucide.createIcons()` after render; in static HTML, drop
  `<i data-lucide="…"></i>` and call `createIcons()` once.

*Substitution flag:* Lucide is a substitute icon system chosen to match the
minimal line aesthetic — no brand icon set was supplied. Swap if Noah has a
preferred set.

---

## Index / manifest

**Root**
- `styles.css` — global entry (import-only). Link this.
- `readme.md` — this guide.
- `SKILL.md` — Agent-Skill front-matter for portable use.
- `_ds_bundle.js`, `_ds_manifest.json`, `_adherence.oxlintrc.json` — **generated**, do not edit.

**Tokens** (`tokens/`) — `fonts.css`, `colors.css`, `typography.css`,
`spacing.css`, `effects.css`. All `@import`ed by `styles.css`.

**Foundation cards** (`foundations/`) — specimen cards for the Design System tab:
type (display / headings / body / mono / serif), colour (paper / ink / signal /
inverse / semantic), spacing (scale / radii / shadows), brand (wordmark / voice),
iconography.

**Components** (`components/`)
- `core/` — `Button`, `Tag`, `Badge`, `Card`, `Avatar`
- `forms/` — `Field`
- `data/` — `MetricStat`

Each has a `.jsx`, `.d.ts`, `.prompt.md`, and a directory `@dsCard` HTML.

**UI kit** (`ui_kits/personal-site/`) — the personal-brand website: Home, Work,
About, Contact + pill nav + footer. See its `README.md`.

---

## Caveats
- **Fonts are Google Fonts substitutes** (Space Grotesk / Space Mono / Instrument
  Serif). No licensed brand fonts were supplied — swap if Noah has them.
- **Lucide** is a substitute icon system (see Iconography).
- All UI-kit copy, metrics, and links are **illustrative placeholders**.



---

## Token reference


### Colors

| Token | Value | Notes |
|---|---|---|
| `--paper-0` | `#FBFAF6` | lifted surface / cards on paper |
| `--paper-1` | `#F4F2EC` | base page background |
| `--paper-2` | `#ECE9DF` | recessed / subtle fill |
| `--stone-1` | `#E3DED1` | secondary surface (REF-like sand) |
| `--stone-2` | `#D5CFBE` | stronger fill / hover on stone |
| `--line-1` | `#E0DACC` | hairline dividers |
| `--line-2` | `#CFC8B6` | stronger borders / input outlines |
| `--ink-1` | `#1A1813` | primary text, headlines |
| `--ink-2` | `#4C473C` | secondary text |
| `--ink-3` | `#847D6C` | muted text, metadata |
| `--ink-4` | `#A8A192` | disabled / faint |
| `--signal-1` | `#2233E6` | primary accent |
| `--signal-2` | `#1A28B8` | accent text on light / pressed |
| `--signal-3` | `#4D5BEC` | hover / lighter accent |
| `--signal-tint` | `#E7E8FB` | accent wash background |
| `--ink-surface-1` | `#1A1813` | near-black panel |
| `--ink-surface-2` | `#262219` | lifted on dark |
| `--on-ink-1` | `#F4F2EC` | primary text on ink |
| `--on-ink-2` | `#B4AD9D` | secondary text on ink |
| `--on-ink-line` | `#3A3528` | borders on ink |
| `--positive-1` | `#2F7D52` |  |
| `--caution-1` | `#B07514` |  |
| `--critical-1` | `#C13A2B` |  |
| `--info-1` | `#2233E6` |  |
| `--bg-page` | `var(--paper-1)` |  |
| `--bg-surface` | `var(--paper-0)` |  |
| `--bg-recessed` | `var(--paper-2)` |  |
| `--bg-secondary` | `var(--stone-1)` |  |
| `--bg-secondary-hover` | `var(--stone-2)` |  |
| `--bg-inverse` | `var(--ink-surface-1)` |  |
| `--text-strong` | `var(--ink-1)` |  |
| `--text-body` | `var(--ink-2)` |  |
| `--text-muted` | `var(--ink-3)` |  |
| `--text-faint` | `var(--ink-4)` |  |
| `--text-accent` | `var(--signal-2)` |  |
| `--text-on-inverse` | `var(--on-ink-1)` |  |
| `--text-on-inverse-muted` | `var(--on-ink-2)` |  |
| `--border-hairline` | `var(--line-1)` |  |
| `--border-strong` | `var(--line-2)` |  |
| `--border-inverse` | `var(--on-ink-line)` |  |
| `--accent` | `var(--signal-1)` |  |
| `--accent-hover` | `var(--signal-3)` |  |
| `--accent-press` | `var(--signal-2)` |  |
| `--accent-wash` | `var(--signal-tint)` |  |
| `--focus-ring` | `var(--signal-1)` |  |


### Typography

| Token | Value | Notes |
|---|---|---|
| `--font-sans` | `'Space Grotesk', ui-sans-serif, system-ui, sans-serif` |  |
| `--font-mono` | `'Space Mono', ui-monospace, 'SFMono-Regular', monospace` |  |
| `--font-serif` | `'Instrument Serif', ui-serif, Georgia, serif` |  |
| `--w-light` | `300` |  |
| `--w-regular` | `400` |  |
| `--w-medium` | `500` |  |
| `--w-semibold` | `600` |  |
| `--w-bold` | `700` |  |
| `--size-display` | `5.5rem` | 88px — hero statements |
| `--size-h1` | `3.5rem` | 56px |
| `--size-h2` | `2.5rem` | 40px |
| `--size-h3` | `1.75rem` | 28px |
| `--size-h4` | `1.25rem` | 20px |
| `--size-body-lg` | `1.125rem` | 18px |
| `--size-body` | `1rem` | 16px |
| `--size-body-sm` | `0.875rem` | 14px |
| `--size-label` | `0.75rem` | 12px — mono labels / eyebrows |
| `--size-micro` | `0.6875rem` | 11px — fine print |
| `--lh-tight` | `1.02` |  |
| `--lh-snug` | `1.15` |  |
| `--lh-normal` | `1.5` |  |
| `--lh-relaxed` | `1.65` |  |
| `--track-tight` | `-0.03em` | display headlines |
| `--track-snug` | `-0.01em` | headings |
| `--track-normal` | `0em` |  |
| `--track-label` | `0.16em` | uppercase mono labels |
| `--track-label-wide` | `0.24em` | eyebrows / nav |
| `--text-display-family` | `var(--font-sans)` |  |
| `--text-label-family` | `var(--font-mono)` |  |
| `--text-accent-family` | `var(--font-serif)` |  |


### Spacing & layout

| Token | Value | Notes |
|---|---|---|
| `--space-0` | `0` |  |
| `--space-1` | `0.25rem` | 4px |
| `--space-2` | `0.5rem` | 8px |
| `--space-3` | `0.75rem` | 12px |
| `--space-4` | `1rem` | 16px |
| `--space-5` | `1.5rem` | 24px |
| `--space-6` | `2rem` | 32px |
| `--space-7` | `3rem` | 48px |
| `--space-8` | `4rem` | 64px |
| `--space-9` | `6rem` | 96px |
| `--space-10` | `8rem` | 128px |
| `--container-max` | `1240px` |  |
| `--container-text` | `680px` | comfortable reading measure |
| `--gutter` | `var(--space-6)` |  |
| `--radius-sm` | `4px` |  |
| `--radius-md` | `8px` |  |
| `--radius-lg` | `14px` |  |
| `--radius-xl` | `22px` |  |
| `--radius-pill` | `999px` |  |


### Effects & motion

| Token | Value | Notes |
|---|---|---|
| `--shadow-xs` | `0 1px 2px rgba(26, 24, 19, 0.05)` |  |
| `--shadow-sm` | `0 1px 3px rgba(26, 24, 19, 0.07), 0 1px 2px rgba(26, 24, 19, 0.04)` |  |
| `--shadow-md` | `0 4px 14px rgba(26, 24, 19, 0.08), 0 2px 4px rgba(26, 24, 19, 0.04)` |  |
| `--shadow-lg` | `0 14px 40px rgba(26, 24, 19, 0.12), 0 4px 10px rgba(26, 24, 19, 0.05)` |  |
| `--shadow-soft` | `0 2px 5px rgba(26, 24, 19, 0.10), inset 0 1px 0 rgba(255, 255, 255, 0.7)` |  |
| `--focus-shadow` | `0 0 0 3px var(--accent-wash), 0 0 0 1px var(--accent)` |  |
| `--ease-out` | `cubic-bezier(0.22, 1, 0.36, 1)` |  |
| `--ease-in-out` | `cubic-bezier(0.65, 0, 0.35, 1)` |  |
| `--dur-fast` | `120ms` |  |
| `--dur-base` | `200ms` |  |
| `--dur-slow` | `360ms` |  |


### Fonts

Loaded via Google Fonts (`@import` in `tokens/fonts.css`):

- **Space Grotesk** (300–700) — display + UI
- **Space Mono** (400/700, italic) — labels, metadata, nav
- **Instrument Serif** (regular + italic) — editorial accent


---

## Components


### Avatar


Typographic monogram avatar — initials in a rounded tile, no photo needed.

```jsx
<Avatar initials="NM" />
<Avatar initials="NM" variant="signal" size={56} />
```

Variants `ink` (default), `signal` (cobalt), `stone`. Uses bold Space Grotesk with tight tracking to match the wordmark.


**Props**

```ts
import * as React from 'react';

/** Typographic initials monogram in a rounded tile (no photo dependency). */
export interface AvatarProps {
  /** @default "NM" */
  initials?: string;
  /** Pixel size. @default 44 */
  size?: number;
  /** @default "ink" */
  variant?: 'ink' | 'signal' | 'stone';
  style?: React.CSSProperties;
}

export function Avatar(props: AvatarProps): JSX.Element;
```


### Badge


Status badge with a leading dot — use for delivery status, states, and flags.

```jsx
<Badge status="positive">On track</Badge>
<Badge status="caution">At risk</Badge>
<Badge status="critical">Blocked</Badge>
<Badge status="info">In review</Badge>
```

Statuses map to the muted semantic palette. Square 4px corners distinguish it from the pill-shaped `Tag`. Set `dot={false}` to hide the indicator.


**Props**

```ts
import * as React from 'react';

/** Small status indicator with leading dot; muted professional semantics. */
export interface BadgeProps {
  children?: React.ReactNode;
  /** @default "neutral" */
  status?: 'positive' | 'caution' | 'critical' | 'info' | 'neutral';
  /** Leading status dot. @default true */
  dot?: boolean;
  style?: React.CSSProperties;
}

export function Badge(props: BadgeProps): JSX.Element;
```


### Button


Pill-shaped action button with a mono uppercase label — use for any primary or secondary action.

```jsx
<Button variant="signal" size="md">Let's talk</Button>
<Button variant="primary" iconRight={<ArrowIcon />}>View work</Button>
<Button variant="secondary">Bookings</Button>
<Button variant="ghost" size="sm">Cancel</Button>
```

Variants: `primary` (ink/near-black), `signal` (cobalt — reserve for the single most important CTA), `secondary` (stone fill, bordered), `ghost` (text only). Sizes `sm` / `md` / `lg`. Set `pill={false}` for soft 8px corners, `full` to stretch. Labels render uppercase via Space Mono — write them in normal case.


**Props**

```ts
import * as React from 'react';

/**
 * The primary action primitive — pill-shaped, mono-label, restrained accent.
 *
 * @startingPoint section="Core" subtitle="Pill action button with 4 variants" viewport="700x200"
 */
export interface ButtonProps {
  children?: React.ReactNode;
  /** Visual style. @default "primary" */
  variant?: 'primary' | 'signal' | 'secondary' | 'ghost';
  /** @default "md" */
  size?: 'sm' | 'md' | 'lg';
  /** Pill radius vs. soft-corner. @default true */
  pill?: boolean;
  iconLeft?: React.ReactNode;
  iconRight?: React.ReactNode;
  disabled?: boolean;
  /** Stretch to container width. @default false */
  full?: boolean;
  style?: React.CSSProperties;
  onClick?: (e: React.MouseEvent<HTMLButtonElement>) => void;
}

export function Button(props: ButtonProps): JSX.Element;
```


### Card


Surface container — the base for case studies, stat tiles and content blocks.

```jsx
<Card pad="lg">…</Card>
<Card interactive onClick={open}>…</Card>
<Card inverse>…</Card>
```

Warm `paper-0` surface, hairline border, soft `shadow-sm`. Set `interactive` for a 2px hover lift, `inverse` for a near-black panel, `pad` for inner spacing (`none`/`sm`/`md`/`lg`).


**Props**

```ts
import * as React from 'react';

/**
 * Surface container with hairline border and soft lift.
 *
 * @startingPoint section="Core" subtitle="Paper surface card with optional hover lift" viewport="700x260"
 */
export interface CardProps {
  children?: React.ReactNode;
  /** Render element/tag. @default "div" */
  as?: any;
  /** Hover lift + pointer. @default false */
  interactive?: boolean;
  /** Near-black surface variant. @default false */
  inverse?: boolean;
  /** Inner padding. @default "md" */
  pad?: 'none' | 'sm' | 'md' | 'lg';
  style?: React.CSSProperties;
  onClick?: (e: React.MouseEvent) => void;
}

export function Card(props: CardProps): JSX.Element;
```


### Tag


Mono uppercase metadata pill — use for categories, skills, and structured key/value labels.

```jsx
<Tag>Project Management</Tag>
<Tag variant="signal">Featured</Tag>
<Tag label="ROLE /">PMO Lead</Tag>
<Tag variant="inverse">Banking Ops</Tag>
```

Variants: `outline` (default, bordered), `solid` (recessed fill), `signal` (cobalt wash), `inverse` (for ink surfaces). Pass `label` for a dimmed prefix to make a structured datum.


**Props**

```ts
import * as React from 'react';

/** Mono metadata pill for labels, categories and key/value data. */
export interface TagProps {
  children?: React.ReactNode;
  /** Optional dimmed prefix, e.g. "ROLE /". */
  label?: React.ReactNode;
  /** @default "outline" */
  variant?: 'outline' | 'solid' | 'signal' | 'inverse';
  style?: React.CSSProperties;
}

export function Tag(props: TagProps): JSX.Element;
```


### Field


Labelled text input with a mono uppercase label — use in forms and newsletter/contact blocks.

```jsx
<Field label="Email Address" type="email" placeholder="you@company.com" />
<Field label="Message" variant="box" hint="Tell me about your project" />
```

`underline` variant (default) is minimal and editorial; `box` is a bordered field with a focus ring. Focus state switches the accent border to cobalt.


**Props**

```ts
import * as React from 'react';

/** Labelled text input — mono uppercase label over underline or boxed input. */
export interface FieldProps {
  label?: React.ReactNode;
  /** @default "text" */
  type?: string;
  placeholder?: string;
  value?: string;
  onChange?: (e: React.ChangeEvent<HTMLInputElement>) => void;
  /** @default "underline" */
  variant?: 'underline' | 'box';
  /** Helper text below the input. */
  hint?: React.ReactNode;
  style?: React.CSSProperties;
}

export function Field(props: FieldProps): JSX.Element;
```


### MetricStat


Big-number statistic — the analyst's signature unit for quantified outcomes.

```jsx
<MetricStat value="120" unit="+" label="Projects delivered" />
<MetricStat value="98" unit="%" label="On-time delivery" delta="+12 pts vs FY23" />
<MetricStat value="40" unit="wks" label="Avg. programme" inverse />
```

Space Grotesk semibold number with a serif-italic `unit`. Optional `delta` line takes a `deltaStatus` colour. Set `inverse` on ink surfaces, `align="center"` for centred stat rows.


**Props**

```ts
import * as React from 'react';

/**
 * Big-number statistic with mono label and optional delta.
 *
 * @startingPoint section="Data" subtitle="Quantified metric with mono label" viewport="700x200"
 */
export interface MetricStatProps {
  value: React.ReactNode;
  label: React.ReactNode;
  /** Serif-italic unit suffix, e.g. "%", "wks". */
  unit?: React.ReactNode;
  /** Secondary delta line, e.g. "+18% vs FY23". */
  delta?: React.ReactNode;
  /** @default "positive" */
  deltaStatus?: 'positive' | 'caution' | 'critical' | 'neutral';
  /** For ink surfaces. @default false */
  inverse?: boolean;
  /** @default "left" */
  align?: 'left' | 'center';
  style?: React.CSSProperties;
}

export function MetricStat(props: MetricStatProps): JSX.Element;
```


---

## UI Kit — Personal Site


A high-fidelity recreation of Noah McGill's personal-brand website: a calm,
editorial, single-surface site for a PMO & Business Analyst in banking operations.

## Screens (single-page, click-through)
- **Home** — hero statement, quantified metric strip, featured programmes.
- **Work** — full case-study grid (`WorkCard` × programme data).
- **About** — identity column + capabilities matrix + toolkit tags.
- **Contact** — inverse panel with a working (faked) message form + success state.

Navigation is a floating glass **pill nav** (`NavBar.jsx`). Selecting a link swaps
the active screen and scrolls to top — no real routing.

## Files
| File | Role |
|---|---|
| `index.html` | App shell — loads React, Babel, Lucide, the DS bundle, then mounts the screens. |
| `shared.jsx` | Pulls DS components off the namespace; `Icon`, `Eyebrow` helpers. |
| `data.js` | `window.WORK_ITEMS` — illustrative programme data. |
| `NavBar.jsx` | Floating pill navigation. |
| `WorkCard.jsx` | Case-study card (composes `Card`, `Tag`, `Badge`). |
| `HomeScreen / WorkScreen / AboutScreen / ContactScreen` | The four views. |
| `SiteFooter.jsx` | Mono metadata footer. |

## Composition
Screens compose the system primitives (`Button`, `Card`, `Tag`, `Badge`,
`MetricStat`, `Avatar`, `Field`) via the global namespace
`window.NoahMcGillDesignSystem_b220d4`. The kit does **not** re-implement primitives.

## Content note
All programme copy, metrics, and contact details are **illustrative placeholders**
to demonstrate the layout. Replace with Noah's real case studies and links.
