Reskin setup: Metalab-inspired
================================

What changed
- Added a skin switch via `site.skin` in `_config.yml`.
- New include `_includes/head.html` loads CSS based on the skin.
- New CSS scaffold at `assets/metalab/metalab.css` to approximate a Metalab-like look.

How to toggle
- Use the Metalab skin: set `skin: metalab` in `_config.yml` (already set).
- Revert to the old skin: remove or change to any other value. The site falls back to the existing `css23` styles.

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
