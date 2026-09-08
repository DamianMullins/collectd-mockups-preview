# Variant: Cream content on live themes

Round: landing-redesign-round-02 (single-variant: the "smaller tidy up" check).

## Design stance
Not a new look — a re-skin of the **cream editorial** composition (round-01,
001) onto collectd's **live theme tokens** from `app/globals.css`, rendered in
both the light (`:root`) and dark (`.dark`) site themes. Tests whether the
editorial content + typography alone lift the homepage without a brand change.

## What changed vs 001-cream-editorial
- Palette: cream `#f6f1e7` / rust `#9a5b33` / brown ink → collectd tokens:
  `--background`/`--card`/`--border`/`--foreground` and green primary
  `oklch(0.55 0.15 145)` light / `oklch(0.7 0.15 145)` dark, exactly as shipped.
  Text on primary follows the real theme (white on light green, dark on the
  lighter dark-mode green).
- Dark theme is a genuine second pass (cards `0.2 0.01 260`, premium band becomes
  a bordered green-tinted panel instead of the cream mock's brown slab), not a
  brightness inversion.
- Fonts kept from the cream mock: **Literata** serif display + italic accents,
  **Inter** UI.
- Paper-grain overlay removed; hero blobs recoloured to green glows.

## Pages in this folder
- `index.html` — homepage in both themes. Toggle in the nav (🌙/☀️);
  `?theme=dark` forces dark (used for headless captures). Content = cream
  editorial's copy verbatim (hero, marquee tags, three editorial feature rows,
  quotes, gallery-theme demos, premium band, FAQ, final CTA).
- `fun-bits.html` — interaction/motion pick-list: 13 demos (dashed ring, text
  stamp, record-player, cursor parallax, scroll-drift collage, direction-flipping
  marquee, clickable pills, count-ups, applying chips, featured flipper, magnetic
  CTA, theme ripple, Konami). Same tokens/fonts, light+dark, touch fallbacks,
  honours prefers-reduced-motion. Picked numbers get wired into `index.html`.

## Theme tokens used (from app/globals.css)
Light `:root`: bg oklch(0.98 0 0) · card oklch(1 0 0) · border oklch(0.88 0 0) ·
primary oklch(0.55 0.15 145) · muted-fg oklch(0.45 0 0) ·
foreground oklch(0.13 0.01 260).
Dark `.dark`: bg oklch(0.13 0.01 260) · card oklch(0.2 0.01 260) ·
border oklch(0.34 0.01 260) · primary oklch(0.7 0.15 145) ·
muted-fg oklch(0.6 0 0). Wordmark ll green = `#429a53` family.

## Trade-offs
- Strong at: showing content can carry the page while the brand stays green;
  both themes actually work because tokens come from prod.
- Weak at: literal fidelity to the editorial warmth — cream's paper+rust
  personality is gone by design; neutral-grey quote band in light theme is
  subtler than cream's tan band.

## Best for
- Deciding whether the homepage "tidy-up" should ship as copy/typography only
  (this) or as the full 002-warm-green-modern redesign.
