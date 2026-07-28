# Claude Exporter — checkout pages

Static pages served via GitHub Pages that host the Paddle checkout flow for
the [Claude Exporter Chrome extension](https://github.com/nikogdanekupluslona-svg/download-claude-conversations).

This repo exists only because the main extension repo is **private**, and
GitHub Pages on a free plan can't publish a public site from a private repo.
These two files are also duplicated at `docs/` in the main repo for
reference — keep them in sync if you change one.

- `checkout.html` — loads Paddle.js and opens the hosted checkout for the
  Pro subscription price. Reads `?deviceId=...` from the query string.
- `success.html` — plain "thank you" page Paddle redirects to after a
  successful payment. It has no logic of its own; the extension's
  background service worker detects navigation to this URL and refreshes
  the subscription status.

No build step, no server — just two static HTML files.
