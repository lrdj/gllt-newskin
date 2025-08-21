Reskin setup: Metalab-inspired
================================

What changed
- Added a skin switch via `site.skin` in `_config.yml`.
- New include `_includes/head.html` loads CSS based on the skin.
- New CSS scaffold at `assets/metalab/metalab.css` to approximate a Metalab-like look.
 - Local fonts (Inter + DM Serif Display) bundled for improved typography.
 - Theme toggle button in the Metalab header with sun/moon and persistence.
 - Grid utilities: 12-col CSS grid helpers (`mlb-container`, `mlb-grid`, `col-*`).

How to toggle
- Use the Metalab skin: set `skin: metalab` in `_config.yml` (already set).
- Revert to the old skin: remove or change to any other value. The site falls back to the existing `css23` styles.
 - Choose theme variant (Metalab skin only): set `skin_theme: light` or `skin_theme: dark` in `_config.yml`.

Local testing with Jekyll
- Build: `bundle exec jekyll build`
- Serve: `bundle exec jekyll serve --livereload`

Using actual metalab.com CSS
- The scaffold avoids copying proprietary CSS. If you have permission and want pixel-accurate styles:
  - Save the relevant compiled CSS from metalab.com to `assets/metalab/metalab.css` (replacing the scaffold).
  - Keep in mind Next.js hashed filenames change; embedding a local copy is more reliable for Jekyll.

Notes
- Current header/footer markup is unchanged; the CSS is designed to make it cleaner. If you want a closer match, we can also swap header/footer includes behind the same `skin` switch.

Fetched reference (for derivation only)
- HTML: `assets/metalab/_fetched/home.html`
- CSS: `assets/metalab/_fetched/main.css`
- Derived tokens used: accent `#584dff`, border `#c7c7c7`, subtle text `#79767a`, rounded corners ~`8–12px`, spacing unit `1.6rem` equivalents.

Utilities and classes
- Container: wrap sections in `mlb-container`.
- Grid: add `mlb-grid` to a container then use `col-12/6/4/3` plus responsive `md-col-*`, `lg-col-*`.
- Typography: `kicker`, `eyebrow`, `lede`, `overline` for emphasis.

Licensed fonts (optional)
- Metalab uses Basis Grotesque Pro (sans) and PP Eiko (display). These are licensed; not bundled here.
- If you have licenses, place files in `assets/metalab/fonts/` with these names:
  - `basis-grotesque-off-white-pro.woff2` (weight 300)
  - `basis-grotesque-regular-pro.woff2` (weight 400)
  - `basis-grotesque-medium-pro.woff2` (weight 500)
  - `ppeiko-light.woff2` (weight 300)
  - `ppeiko-regular.woff2` (weight 400)
- The CSS already has `@font-face` entries for these. If files are present, they’ll be used; otherwise it falls back to Inter + DM Serif Display.
