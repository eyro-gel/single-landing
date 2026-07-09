# builtbyaero — Aero Gel Umali portfolio

Single-page portfolio funnel for **builtbyaero.dev**, deployed with GitHub Pages.

## What's in here
- `index.html` — the entire site (self-contained: images, styles, and scripts are embedded)
- `favicon.ico` — multi-resolution favicon (also embedded in `index.html` as a fallback)
- `robots.txt` — allows search engines + AI search, blocks AI training crawlers
- `sitemap.xml` — single-page sitemap for search engines
- `CNAME` — custom domain (`builtbyaero.dev`) for GitHub Pages
- `.nojekyll` — tells GitHub Pages to serve files as-is

> Everything the page needs is either embedded or loaded from public CDNs
> (Google Fonts, client logos, live-site screenshots), so there is no
> `assets/` folder to maintain.

## Deploy (GitHub Pages)
1. Put these files at the **root** of your repository (same level as this README).
2. Commit and push to the branch GitHub Pages serves (usually `main`).
3. In **Settings → Pages**, confirm the source branch/folder and that the
   custom domain `builtbyaero.dev` is set (the `CNAME` file handles this).
4. GitHub Pages redeploys automatically within a minute or two.

## Update the site
Edit `index.html` and push. That's it.

## Contact form
The form posts to a Make (Integromat) webhook via `fetch`. A hidden honeypot
field (`website`) silently drops bot submissions before they reach the webhook.
Real submissions send only `fullname`, `email`, and `message`.

## Notes
- GitHub Pages cannot set custom HTTP headers or run a firewall, so bot rules
  here rely on `robots.txt` (an honor system). To hard-block scrapers that
  ignore it, front the domain with Cloudflare and enable "Block AI Scrapers
  and Crawlers."
