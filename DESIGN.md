# SkiroLiro design system

This is the starting point for people and agents building any SkiroLiro app or site (web, mobile, and whatever comes next). Read this file, then `tokens.json` (values), then `guidelines/UI.md` and `guidelines/UX.md` (rules).

## Brand

- **Name in the brand and in copy:** SkiroLiro.
- **Technical identifiers:** `skiroliro`, lowercase, no hyphen (GitHub, npm `@skiroliro/*`, domain, bundle id `com.skiroliro.<app>`, URL slugs). Never `skiro-liro`.
- **Idea:** exchange of knowledge and experience between people. Usefulness before decoration. A warm, direct tone without exaggeration.
- **Visual personality:** discreet, geometric, calm. Blue and green. Simple shapes (circles, squares with moderate corners). Nothing flashy.

## Logo

Two equal circles stacked like a colon, followed by the name set in Figtree Bold. The top circle is blue, the bottom one is green.

| File | When to use |
|---|---|
| `logo/skiroliro-lockup-light.svg` | Default on light backgrounds |
| `logo/skiroliro-lockup-dark.svg` | Default on dark backgrounds |
| `logo/skiroliro-lockup-mono-dark.svg` | One color, light backgrounds (documents, stamps, B&W print) |
| `logo/skiroliro-lockup-mono-white.svg` | One color, dark backgrounds or photos |
| `logo/skiroliro-icon-light.svg` / `-dark.svg` | The two dots only, where the name does not fit or appears nearby |
| `logo/skiroliro-app-icon.svg` | App icon (1024 px, rounded square) and favicon |

Rules:
- Text in the SVGs is converted to outlines. They do not depend on an installed font.
- **Clear space:** at least the height of one circle on every side.
- **Minimum size:** full lockup at 96 px wide (web), or an icon at 24 px tall. Below that, use the icon only.
- Do not rotate, stretch, swap the circle colors, or add effects (shadow, glow, gradient).
- On photo backgrounds, use the one-color version.
- The brand green (`#2DB88C`) has low contrast on light backgrounds. It is fine for the logo, but in the interface use the text-safe green (`accent`, `#17795C`).

## Color

Palette "Night and mint". Components must use **semantic roles** (`color.light.*` and `color.dark.*` in `tokens.json`), never primitive values.

| Role | Light | Dark | Use |
|---|---|---|---|
| `bg` | #F6F8FA | #0A101C | Page background |
| `surface` | #FFFFFF | #111B2E | Cards, panels |
| `surface-raised` | #FFFFFF | #182540 | Menus, dialogs (lighter than surface in dark mode) |
| `surface-sunken` | #EAEFF5 | #0A101C | Inputs, recessed areas |
| `border` | #D5DCE6 | #223048 | Decorative dividers |
| `border-strong` | #7A889C | #5A6B88 | Borders of inputs and controls |
| `text` | #0E1B2E | #E9EEF7 | Primary text |
| `text-muted` | #586A82 | #93A3BA | Secondary text |
| `primary` | #16335E | #7E9FE0 | Main action, links, selection |
| `on-primary` | #FFFFFF | #0A101C | Text on `primary` |
| `accent` | #17795C | #4FE0B0 | Green highlight, success, progress |
| `accent-graphic` | #2DB88C | #4FE0B0 | Illustration and logo only, never text |
| `on-accent` | #0E1B2E | #0A101C | Text on green backgrounds |
| `warning` | #8F5600 | #F2B84B | Caution |
| `danger` | #C0303F | #FF8A93 | Error, destructive action |
| `info` | #2F5AA8 | #7E9FE0 | Information |
| `focus-ring` | #16335E | #9DB6EE | Focus ring |

**Usage:** blue is the action color. Green marks results, progress, and things that went well, and appears less often. About 90% of any screen should be neutral.

### Verified contrast (WCAG 2.1)

Normal text needs 4.5:1. Large text and interface elements need 3:1.

| Pair | Ratio |
|---|---|
| Text on background, light | 16.2 |
| Muted text on background, light | 5.2 |
| Primary on background, light | 11.8 |
| White on primary, light | 12.6 |
| Text-safe green on background, light | 5.0 |
| Danger on background, light | 5.3 |
| Warning on background, light | 5.6 |
| Strong border on background, light | 3.4 |
| Text on background, dark | 16.3 |
| Muted text on background, dark | 7.4 |
| Primary on background, dark | 7.2 |
| Green on background, dark | 11.4 |
| Danger on background, dark | 8.4 |
| Warning on background, dark | 10.6 |
| Strong border on background, dark | 3.5 |
| Muted text on `surface-raised`, dark | 5.9 |

Exception: the brand green `#2DB88C` on a light background is 2.4:1, so it is never used for text or interface controls.

## Typography

- **Interface:** Figtree (400, 500, 600, 700). Open source (OFL), variable, with full Portuguese diacritics.
- **Code and tabular numbers:** JetBrains Mono (400, 500).
- Fallback: `system-ui`. In native apps, bundle the fonts with the app.
- Scale (px): 12, 14, 16, 18, 20, 24, 30, 36, 48. Body text is 16 px on a 24 px line height. Ready-made styles (`display`, `h1` to `h4`, `body`, `body-sm`, `label`, `caption`, `code`) are in `typography.style` in `tokens.json`.
- Headings use slightly negative letter spacing (`-0.02em`). Uppercase labels use `+0.06em`.
- Maximum reading width is 65 characters (`size.reading-max`).

## Spacing, shape, and depth

- **4 px grid.** Scale: 0, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80.
- **Radius:** `sm` 4 (tags), `md` 8 (buttons, inputs), `lg` 12 (cards), `xl` 16 (dialogs, sheets), `full` (avatars, chips, the brand dots). The circle is the signature shape; use it for avatars, status indicators, and progress icons.
- **Shadow:** few and soft (`sm`, `md`, `lg`). In dark mode prefer surface contrast and borders over shadow.
- **Motion:** 120 / 200 / 320 ms, curve `cubic-bezier(.2,0,0,1)`. Respect `prefers-reduced-motion`.
- **Breakpoints (web):** 480, 768, 1024, 1280. Design for 360 to 400 px wide first.
- **Touch targets:** at least 44 px (iOS) and 48 px (Android).

## Web and mobile

- `tokens.json` is the source of truth. Web uses `tokens.css` (`--sl-*` variables, dark mode automatic and via `data-theme`).
- **Android (Compose):** build a light and a dark `ColorScheme` from `color.light` and `color.dark`; `space` and `radius` in `dp`; bundle the fonts.
- **iOS (SwiftUI):** one `Color` per role with light and dark variants; `space` and `radius` in points.
- **React Native / Flutter:** one theme object per mode with the same role names.
- Keep **role names identical** on every platform. Only values change per mode.
- Components should behave the same on web and mobile: same states, same copy, same hierarchy. Only platform ergonomics differ (bottom navigation on phones, side bar on desktop).

## Files

```
design-system/
  DESIGN.md           this file
  tokens.json         tokens in DTCG format
  tokens.css          generated CSS variables
  guidelines/UI.md    components, layout, visual content
  guidelines/UX.md    experience principles, flows, copy, accessibility
  logo/*.svg          final logos
```

## Open items

- Icons: no set defined yet. Suggestion: 1.5 px stroke, rounded corners, 24 px grid, in line with the geometric shapes.
- Illustration and photography.
- Ready-made components (code) per platform, once the first app exists.
- Confirm domain, GitHub, and npm availability for `skiroliro`.
