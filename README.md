# Shrey Kapoor — Website

A static personal/academic website (CV / portfolio) for Shrey Kapoor, implemented
from the Claude Design file `Shrey Kapoor.dc.html`.

## What's here

- `index.html` — the page markup and the design-component runtime entry. The page
  uses Claude Design's `<x-dc>` component runtime (a small templating layer with
  `{{ … }}` bindings and `<sc-if>` / `<sc-for>` directives) and renders entirely
  client-side. It has six screens — Home, Research, Publications, Teaching, Photos,
  and CV — with client-side navigation (no page reloads).
- `assets/` — all bundled assets extracted from the original self-contained design
  file and referenced by relative path:
  - the design-component runtime script (`*.js`),
  - the EB Garamond / Frank Ruhl Libre / Newsreader / IBM Plex web fonts (`*.woff2`),
  - photos and figures (`*.jpg`).

The original Claude Design export inlined every asset as base64 inside a single
HTML file. This implementation unpacks those assets into real files under `assets/`
and rewrites the references, so the site is a clean, cacheable static bundle.

## Running locally

It's a fully static site — serve the directory with any static file server:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploying

Deploys as-is on any static host (e.g. Vercel) with no build step — `index.html`
at the repository root is the entry point.
