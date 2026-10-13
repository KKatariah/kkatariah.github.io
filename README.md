# Katariah's Website

A Morrowind-themed personal site built with [Next.js](https://nextjs.org) (App Router).

```sh
npm install
npm run dev     # http://localhost:3000
npm run build   # static site in out/ (copy its contents to the web server)
```

- `src/app/` — one folder per route (`page.tsx`), plus `layout.tsx` and `globals.css`
- `src/components/` — shared UI: `Window` (frame + title bar), `Panel` (page window with banners), `MapNav`, `Dialogue`, `Inventory`, `Tooltip`, …
- `src/components/ui/` — building blocks: `Button` (link or button with the Morrowind frame) and `Frame` (thin gold-bordered box; `scroll` gives it the Morrowind scrollbar)
- `src/lib/locations.ts` — every page and the Vvardenfell town it sits at (drives the nav and the map)
- `public/` — Morrowind UI textures, fonts, and photos, served from `/`
- `src/assets/cat_photos/` — pet photos, imported by `src/app/pets/page.tsx` so `next/image` can blur-preview them (static export serves them unresized). To add one: drop it in that folder and add an `import` + entry in the page.

Colours in `globals.css` are the game's own UI palette from `Morrowind.ini`. Body text uses [Pelagiad](https://github.com/Isaskar/Pelagiad) (SIL OFL 1.1, licence in `public/fonts/`).
- `legacy/` — the original static HTML version, kept for reference

## Music page (Last.fm)

The Music page shows what I'm listening to via [Last.fm](https://www.last.fm) (Spotify → Settings → connect Last.fm to scrobble). Get an API key from [Last.fm's API page](https://www.last.fm/api/account/create), then create `.env.local`:

```sh
NEXT_PUBLIC_LASTFM_API_KEY=your_api_key
NEXT_PUBLIC_LASTFM_USER=your_lastfm_username
```

Set the same two variables on the host. Without them the page shows a short "coming soon" note.
