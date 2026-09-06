# Nexwear Innovations — website

Marketing site for Nexwear Innovations Private Limited. Cloud-based IIoT retrofit
and AI vision monitoring for garment sewing floors and quality checking areas.

---

## What's in this package

```
dist/index.html      Deploy-ready. Single self-contained file, everything inlined.
source/              Editable source.
  Nexwear Website.dc.html   The page (markup + logic in one file)
  support.js                Runtime it loads
  assets/                   Logo, product photos, team portraits, partner logos
  _ds/industry-.../         Design-system stylesheet + bundle
```

## Deploying (fastest path)

`dist/index.html` needs no build step and no server-side anything. Any of these
work as-is:

- **GitHub Pages** — push this folder, rename `dist/index.html` to `index.html`
  at the repo root (or set Pages source to `/dist`), enable Pages.
- **Netlify / Vercel / Cloudflare Pages** — drag the `dist` folder in. Done.
- **Any shared host / cPanel** — upload `index.html` to `public_html`.

Custom domain: point an A/CNAME record at the host, then add the domain in the
host's dashboard. Nothing in the page hardcodes a URL.

## Editing

Open `source/Nexwear Website.dc.html` in a browser to preview. It is one file:

- **Markup** — the `<x-dc>` template. Inline styles only; theme variables are
  declared at the top (`--acc`, `--bg`, `--ink`, `--hd`, `--bd`, `--mn`).
- **Content** — the `Component` class near the bottom. All copy, team members,
  partner logos, dashboard demo numbers and the machine map live in plain JS
  arrays there (`TEAM`, `VIEWS`, `LINES`, `MATRIX`, and the objects returned
  from `renderVals()`). Change text there, not in the markup.

After editing source, regenerate `dist/index.html` (any single-file inliner, or
re-export from the design tool this was authored in).

## Two things still to wire up

1. **Hero background video.** The hero looks for `assets/factory-loop.mp4` and
   plays it automatically if present; otherwise it cross-fades the three floor
   photos. Add a silent 10–20s loop of the sewing floor (operators working,
   several units running, ideally a Nexwear device and a dashboard TV in frame)
   at that path.
2. **Contact form.** The form is presentational — the submit button only shows a
   confirmation state. Wire it to a form backend (Formspree, Web3Forms, Google
   Apps Script) or your own endpoint. The submit handler is `submit()` in the
   `Component` class.

## Content notes

- Dashboard figures are **demonstration data**, labelled as such on the page.
  They animate to feel live. Replace with real pilot numbers when you have
  permission from the customer.
- Claims currently on the page: 10–20% production increase, 6–12 month ROI,
  up to 70% cost saving vs replacement, under 10 minutes setup per machine.
  Confirm these before launch.
- Scope is stated deliberately: sewing machines and quality checking only;
  cutting, fusing, embroidery, washing and finishing are excluded.

## Contact details on the page

- founder.nexwear@outlook.com
- +91 81909 07213, +91 80989 86269
- Nexwear Innovations Private Limited, 5/55A Chettiyar Street,
  Jambunathapuram, Musiri (TK), Tiruchirapalli (DT), Tamil Nadu — 621211

## Design

Dark technical theme. Space Grotesk (headings), IBM Plex Sans (body),
IBM Plex Mono (labels and figures), loaded from Google Fonts — already inlined
in `dist`. Accent green `#5cbf6a`, amber `#e39a3c` for warnings, red `#e2564f`
for breakdown, cyan `#4aa9c4` for maintenance. Background `#0a0c0c`.
