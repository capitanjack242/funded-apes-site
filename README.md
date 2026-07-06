# Funded Apes — Static Site Mirror (Cleaned + Patched)

This is a static mirror of fundedapes.trade, cleaned up for reliable hosting.

## What works
- All visible content: hero, features, footer, legal pages
- All images, fonts, CSS styling
- All internal links (terms.html, priorityaccess.html, risk-disclaimer.html, privacy-policy.html)
- All external links (Discord, challenge purchase links to propaccount.com)
- **Pricing tabs now fully functional**: 1-Step Challenge, 2-Step Challenge, and Training
  Challenge all switch correctly and show their real pricing/rules. This data was
  extracted directly from the site's own JS bundle (it was present all along, just not
  in the initial static HTML — it only loaded when someone clicked the tab on the live
  site). Rebuilt as plain vanilla JS so it works without a Next.js server.

## What was removed
- Next.js "hydration" bootstrap scripts that only work when served by a real Next.js
  server. Without them, the site loads faster and throws no console errors.
- The email popup/gate modal — this never rendered any visible content in the static
  HTML to begin with (100% JS-driven with no fallback markup), and its trigger logic
  wasn't recoverable from the mirror. Not present in this version.

## To get the email modal back
The real fix is exporting the actual Next.js source from v0.app (Push to GitHub button
in the v0 project) rather than patching this compiled/minified static snapshot.

## Hosting this as-is
Any static host works: GitHub Pages, Netlify, Vercel (static), Cloudflare Pages.
No build step needed — just point the host at this folder. Remember to add a
`.nojekyll` file in the root if hosting on GitHub Pages, or the `_next` folder
(and its CSS/JS) will get silently dropped.
