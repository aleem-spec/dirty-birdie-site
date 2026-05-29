# CLAUDE.md — Dirty Birdie Summer Classic website

This file gives Claude Code the context it needs to edit this site safely.

## What this is
A static website (plain HTML + CSS, **no build step, no framework, no JavaScript
required**) for the Dirty Birdie Summer Classic — an annual invitational golf
tournament, est. 2012. Deployed as static files to a host like Cloudflare Pages,
Netlify, or GitHub Pages.

## Files
- `index.html` — homepage (hero, 2025 champion, 2026 host, Champions Dinner, champions preview, footer)
- `champions.html` — Champions Wall / history (stats strip + 14-edition grid + two-time champions)
- `results-2025.html` — per-year results page. **This is the template** — clone it to `results-YYYY.html` for other years.
- `styles.css` — the entire design system (tokens + components). Edit here for anything global.
- `images/` — all photos. Filenames are referenced directly in the HTML.

## How to make common edits
- **Add a champion (new year won):**
  1. In `champions.html`, add a new `.plaque` card at the top of `.grid` (year, name, location). Tag two-time winners with `<span class="tag">Two-Time Champion</span>` and class `plaque two`.
  2. Update the reigning-champion feature (`.reign`) and the `.stats` numbers.
  3. In `index.html`, update the 2025 champion section and the first card of `.wall`.
- **Add a results page for a year:** copy `results-2025.html` → `results-YYYY.html`; edit the header (year · location · champion), intro paragraph, champion callout, group photo, and results image. If a year has no results image, delete the "FINAL RESULTS" `<section>`. Archive links already point to `results-YYYY.html`, so it's linked automatically. See `ADD-YEAR-PAGES.md` for the full data table and a ready-to-paste prompt.
- **Swap a photo:** replace the file in `images/` keeping the same name, or add a new file and update the matching `<img src>`.
- **Edit copy:** text lives directly in the HTML inside semantic tags — edit in place.

## Design conventions (do not drift from these)
- **Palette (defined in `styles.css :root`, oklch):** cream `--bone`, deep green `--forest` / `--forest-deep`, brighter `--fairway`, trophy `--gold`, ink `--ink`. Use these tokens — don't introduce new colors.
- **Type:** Cormorant Garamond (display/headings, via `.display`), Archivo (body/labels). Loaded from Google Fonts in `styles.css`.
- **Components:** buttons `.btn` + `.btn-primary/.btn-ghost/.btn-gold/.btn-on-dark`; eyebrow labels `.eyebrow`; cards `.plaque` / `.champ-card`. Reuse these rather than inventing new styles.
- **No emoji as icons.** Use typographic/numeric treatments (the original site's emoji were deliberately removed).
- Section structure is marked with `<!-- ===== NAME ===== -->` comments — keep them.
- Radius: `--r` (4px buttons), `--r-lg` (8px cards). Max width `--maxw` (1240px).

## Deploy
Static hosting. Any commit to the connected repo redeploys automatically — no build
command, output/publish directory is the repo root (`/`).
