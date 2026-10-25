# Hatom — Maintainable Source (Best-Effort)

This folder contains a runnable, human-maintainable scaffold of the Hatom clone.

## Run

```bash
npm install
npm run dev
```

Opens http://localhost:5173. The app runs from the production bundle served as
static assets (under `public/`), so it loads exactly like the original clone.

```bash
npm run build
```

Produces `dist/` for deployment (Vercel auto-detects Vite).

## Structure

- `index.html` — original SSR shell (entry point, at project root).
- `public/` — all static assets (assets/, webgl/, audio/, lottie/, images/,
  video/, and locale route pages with payloads). Copied verbatim by Vite.
- `src/main.js` — beautified production bundle (readable reference).
- `src/components/` — one stub file per discovered Vue component (55 total).
- `src/bundles/` — beautified per-chunk bundles (add via decompile-all.js).

## Source reconstruction

The `src/main.js` and `src/components/` are best-effort reconstructions produced
by `scripts/decompile.js` / `scripts/decompile-all.js` from the clone-anything
skill. Original module boundaries are inferred; this will not build as a
from-scratch source project. Use for reading, debugging, and gradual refactoring.

## Notes

- External API calls (MultiversX, Hatom app) require network access.
- To regenerate beautified bundles: `node <skill>/scripts/decompile-all.js public .`
