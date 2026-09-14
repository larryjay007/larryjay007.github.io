# Plant Your Flag: Domain + Badge

## Live URL

https://larryjay007.github.io/

Renamed the repo from `aiFluency` to `larryjay007.github.io` to get GitHub Pages' clean
root-domain convention — a genuine free fallback, no `/aiFluency` path suffix, since budget
for a paid domain was zero.

## Real Issues Found and Fixed Along the Way

This wasn't a clean one-shot deploy — worth logging honestly:

1. After renaming, the site initially served `README.md` content instead of the portfolio,
   caused by GitHub Pages' default GitHub Actions/Jekyll build path. Fixed by switching the
   Pages source to "Deploy from a branch" and adding a `.nojekyll` file to disable Jekyll
   processing entirely.
2. All four HTML files (and later, `styles.css`) had been silently renamed with `(1)`
   suffixes during upload, because the Downloads folder already had earlier copies —
   GitHub Pages requires an exact filename match (`index.html`), so `index (1).html` 404'd.
   Fixed by renaming each file directly on GitHub to its exact correct name.
3. Two links elsewhere (the personal site's "AI Portfolio" button, and the CV's header and
   project bullet) still pointed to the old `larryjay007.github.io/aiFluency/` and
   `github.com/larryjay007/aiFluency/...` addresses, both broken by the rename. Fixed both,
   redeployed, and verified.

## Analytics

Google Analytics (GA4) installed on all four pages via the standard gtag.js snippet.
Verified genuinely working: visited the live site, then confirmed "1 active user" appeared
in GA's Realtime overview within a minute (screenshot attached separately).

## Launch Hygiene

- **Favicon:** confirmed showing correctly in the browser tab.
- **Page titles:** confirmed correct and specific per page (not blank or generic).
- **Social-share preview:** Open Graph and Twitter Card meta tags added to all four pages
  during the prior "Break Your Own Site" task; OG URLs updated this session to point to the
  new clean domain instead of the old broken one.
- **Phone check:** confirmed the new URL loads correctly and looks right on mobile.

## Graduate Badge

Real FlyRank credential badge installed in the footer of all four pages, linking to:
https://internship.flyrank.ai/verify?id=FR-D1-T668H-R789R&first_name=Lanre

Confirmed visible and clickable on the live site.
