# UI guidelines

Values come from `../tokens.json`. This file holds the usage rules.

## Principles

1. **Calm before effect.** Neutral background, one main action per screen, blue for acting, green for results.
2. **Simple geometry.** Basic shapes, moderate corners, strict alignment to the 4 px grid.
3. **Consistency across platforms.** Same color roles, same states, same hierarchy.
4. **Clear information.** State never depends on color alone: also use text, an icon, or a shape.

## Layout

- Content has a maximum width of 1120 px (`size.content-max`); running text at most 680 px.
- Side margins: 16 px on phones, 24 px on tablets, 32 px or more on desktop.
- Space between groups: 24 to 32 px. Between related items: 8 to 12 px. Inside a card: 16 to 24 px.
- Prefer flex and grid with `gap` over per-element margins.
- Phone: one column, bottom navigation with up to 5 destinations. Tablet and desktop: side or top navigation.

## Color in the interface

- Page background: `bg`. Cards and panels: `surface`. Inputs: `surface-sunken` with a `border-strong` border.
- Main action: `primary` with `on-primary`. Only one per screen.
- Links: `link`, underlined in running text.
- Success and progress: `accent`. Warning: `warning`. Error: `danger`. Always together with an icon or text.
- `accent-graphic` and the brand green are for illustration and the logo only.
- In dark mode, higher layers are lighter (`surface`, then `surface-raised`). Do not use heavy shadows.

## Typography

- Body text 16 px (14 px in dense areas). Never below 12 px.
- Headings in Figtree Bold or Semibold. Data, code, IDs, and values aligned in columns use JetBrains Mono (or Figtree with tabular numbers).
- One hierarchy per screen: at most 3 visible size levels at the same time.
- Align left. Avoid centering paragraphs.

## Components

**Button.** Heights 32 / 40 / 48 px, radius `md`, label in `label` style. Variants: primary (filled), secondary (outlined with `border-strong`), tertiary (text only), destructive (`danger`). The label is a verb: "Save", "Send invite". Touch target is at least 44 px even if the visual is smaller.

**Text field.** Height 40 px (48 on phones), radius `md`, `border-strong` border, label always visible above. Focus: 2 px `focus-ring`. Error: `danger` border, icon, and message below. Help text in `text-muted`.

**Card.** `surface`, radius `lg`, `border` or `sm` shadow (not both). Padding 16 to 24 px. A clickable card gets focus and hover states.

**List.** Rows at least 48 px tall. `border` divider. Secondary actions on the right; the main action is tapping the row.

**Chip and tag.** Radius `full`, height 28 to 32 px. Active state: `primary` fill with `on-primary`, or a `primary` outline.

**Avatar and indicators.** Circles. Sizes 24, 32, 40, 56 px. Status indicators are circles of 8 to 10 px with alternative text.

**Dialog and sheet.** `surface-raised`, radius `xl`, `lg` shadow in light mode. On phones, prefer a bottom sheet. One title, one short text, up to two actions. The destructive action is never the default.

**Navigation.** The active item uses `primary` plus an indicator (underline, pill, or dot) in addition to color. Labels are always visible, never icon-only.

**Messages (toast, banner).** A toast disappears after 5 to 8 s and has a close button. Errors that require action go in a persistent banner, not a toast.

**Empty, loading, and error states.** Every data component has all three. Empty: explain what will appear and offer the first action. Loading: a skeleton shaped like the content. Error: what happened, what to do, a retry button.

## Icons

- 1.5 px line, rounded corners, 24 px grid, sizes 16 / 20 / 24.
- Color inherited from the text. An icon on its own needs an accessible label.

## Motion

- Transitions of 120 to 320 ms with the standard curve. Enter with deceleration, exit with acceleration.
- Motion only to explain change (appear, move, confirm). No continuous decorative animation.
- Respect `prefers-reduced-motion` (web) and the reduce-motion setting on iOS and Android.

## Light and dark mode

- Both are first-class. Test every screen in both.
- Follow the system preference and allow a manual choice.
- Images and illustrations need a version or treatment for both modes.

## Checklist before shipping

- [ ] Uses only color roles from the tokens, no loose hex values.
- [ ] Contrast verified (text 4.5:1, controls and input borders 3:1).
- [ ] Focus, hover, pressed, disabled, error, and loading states defined.
- [ ] Works at 360 px wide with no horizontal scroll.
- [ ] Touch targets of 44 px or more.
- [ ] Tested in light and dark.
