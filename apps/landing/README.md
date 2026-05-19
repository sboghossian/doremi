# Doremi — Landing page

Public-facing site at **doremi.dashable.dev**.

## Stack

- Single `index.html` (plain HTML)
- Tailwind CSS via CDN (no build step)
- Inter font (Google Fonts)
- Inline SVG for the three-wave logo

This is intentionally **build-step-free** for v1. When it needs interactivity, animations, or a CMS, migrate to Astro.

## Preview locally

```bash
cd apps/landing
python3 -m http.server 8000
# open http://localhost:8000
```

Or any static server (`npx serve`, `php -S`, etc.).

## Deploy

The site is one file. Drop `index.html` on any static host:

- Cloudflare Pages
- Vercel (zero config)
- Netlify (drag & drop)
- GitHub Pages
- Your own server

The email-capture form currently logs to console — wire up a real backend before launch (Resend, Loops, ConvertKit, or a Google Form).

## TODOs

- [ ] Hook email-capture form to a real backend
- [ ] Replace placeholder GitHub URL once repo is created
- [ ] Add OG image (`og.png`, 1200×630)
- [ ] Add favicon (use the three-wave logo)
- [ ] Add a demo video / GIF once the OS app has something to show
- [ ] Light/dark mode toggle (optional)
