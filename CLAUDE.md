# cook.sankhacooray.com

See README.md for content format and deploy steps.

## Lighthouse
<!-- lighthouse-optimized: 2026-10-31 -->
- Baseline (mobile): performance 99, accessibility 98, best-practices 100, SEO 100.
- Fixed: Google Fonts CSS loads non-blocking (preconnect + print/onload + noscript), unused DM Sans 300/700 dropped; post card titles are `h2` (were `h3` straight after the `h1`); `public/_headers` gives images/icons a 30-day TTL.
- Left: shared footer/analytics scripts, gtag and Cloudflare Insights findings are handled centrally.
