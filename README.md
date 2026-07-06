# Funded Apes — Static Site Mirror (Cleaned)

This is a static mirror of fundedapes.trade, cleaned up for reliable hosting.

## What works
- All visible content: hero, "Pick Your Battlefield" pricing (1-Step tab), features, footer, legal pages
- All images, fonts, CSS styling
- All internal links (terms.html, priorityaccess.html, risk-disclaimer.html, privacy-policy.html)
- All external links (Discord, challenge purchase links to propaccount.com)

## What was removed
- Next.js "hydration" bootstrap scripts that only work when served by a real Next.js server.
  Without them, the site loads faster and throws no console errors — but a couple of
  JS-only features are gone as a result:
  - The email popup/gate modal (it never rendered any visible content in the static
    HTML to begin with — it's 100% JS-driven)
  - The "2-Step Challenge" / "Training Challenge" pricing tab buttons — clicking them
    won't swap in different pricing cards, since that data was never present in the
    static HTML. Only the "1-Step Challenge" data (which is fully visible on the page)
    was ever server-rendered.

## To get those features back
The real fix is exporting the actual Next.js source from v0.app (Push to GitHub button
in the v0 project) rather than patching this compiled/minified static snapshot.

## Hosting this as-is
Any static host works: GitHub Pages, Netlify, Vercel (static), Cloudflare Pages.
No build step needed — just point the host at this folder.
