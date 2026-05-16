# Consequence Map

> Map the ripple effects of any decision — 1st, 2nd, and 3rd order consequences, powered by Claude AI.

## Deploy in 3 minutes (free)

### Option A — Vercel CLI (fastest)
```bash
npm i -g vercel
vercel
```
Done. You'll get a live URL like `consequence-map.vercel.app`.

### Option B — Vercel Dashboard (no terminal)
1. Go to [vercel.com](https://vercel.com) → New Project
2. Upload this folder (drag & drop)
3. Click Deploy

## How it works
- Pure HTML/CSS/JS — no build step, no framework
- Calls Anthropic Claude API directly from the browser
- Users enter their own API key (stored in browser localStorage only)
- Zero backend, zero database, zero ongoing cost

## Customization ideas
- Add a "share this map" button (encode state in URL)
- Export to PNG using html2canvas
- Save maps to localStorage history
- Add a visual tree/graph layout using D3.js
- Support multiple languages

## Stack
- Frontend: Vanilla HTML/CSS/JS
- AI: Anthropic Claude API (claude-sonnet-4)
- Fonts: Google Fonts (DM Serif Display, DM Sans, DM Mono)
- Hosting: Vercel (free tier)
