# Consequence Map

> Type any decision. See where it leads — 1st, 2nd, and 3rd order consequences mapped as an interactive visual tree, powered by local AI via Ollama.

---

## What it does

Most people think one step ahead. Consequence Map forces you to think three.

You type a decision or event — *"I quit my job to freelance"*, *"My city bans cars downtown"*, *"We go fully remote"* — and the app generates a branching tree of consequences:

- **1st order** — direct, immediate effects
- **2nd order** — reactions to those reactions
- **3rd order** — systemic, long-term shifts nobody sees coming

Each node is labeled **Positive**, **Negative**, or **Neutral**, with color-coded bezier lines tracing every pathway from root to outcome. Click any node for a deep-dive analysis.


---

## Stack

| Layer | Choice |
|---|---|
| Frontend | Vanilla HTML + CSS + JS — no framework, no build step |
| AI | [Ollama](https://ollama.com) running locally |
| Fonts | Instrument Serif, Geist, Geist Mono (Google Fonts) |
| Hosting | Vercel (free tier) |

Zero backend. Zero database. Zero ongoing cost.

---

## Prerequisites

You need [Ollama](https://ollama.com) installed and running locally with CORS enabled:

```bash
OLLAMA_ORIGINS=* ollama serve
```

Pull a model if you haven't already:

```bash
ollama pull llama3.2
```

Any instruction-following model works — `mistral`, `gemma2`, `phi3`, `qwen2.5`, etc. Larger models give more specific, insightful consequences.

---

## Deploy in 3 minutes

### Option A — Vercel CLI

```bash
npm i -g vercel
vercel
```

Done. You'll get a live URL like `consequence-map.vercel.app`.

### Option B — Vercel Dashboard (no terminal)

1. Go to [vercel.com](https://vercel.com) → **New Project**
2. Drag and drop this folder
3. Click **Deploy**

### Option C — Run locally (no deploy needed)

Just open `index.html` directly in your browser. Since AI calls go to `localhost:11434`, no server is needed.

---

## Usage

1. Make sure Ollama is running (`OLLAMA_ORIGINS=* ollama serve`)
2. Open the app
3. Enter your Ollama host (default: `http://localhost:11434`) and model name
4. Hit **Test** to confirm the connection
5. Type any decision and click **Map the consequences**

### Example prompts that work well

**Personal**
- I quit my job to become a full-time content creator
- I delete all my social media permanently
- I move from New York to a small town in rural Montana

**Policy**
- A city bans cars from its downtown core
- The US implements a 4-day work week nationally
- A government makes voting mandatory

**Business**
- A startup offers lifetime subscriptions at $50 to get early traction
- A company gives all employees unlimited PTO
- A major retailer closes all physical stores

**Edge cases** (best for testing model quality)
- A small town gets a Costco for the first time
- A country legalizes all drugs
- OpenAI releases AGI publicly and for free

---

## Features

- **Interactive tree** with SVG bezier connectors between parent and child nodes
- **Sentiment coloring** — green for positive, red for negative, slate for neutral — on cards, left borders, and connector lines
- **Summary bar** showing the overall sentiment balance across all 9 consequences
- **Deep-dive panel** — click any node for a 3-paragraph AI analysis covering why it's underestimated, who it hits hardest, and what amplifies or dampens it
- **Example chips** for one-click prompts
- Keyboard shortcut: `⌘ Enter` to generate

---

## Customization ideas

- **Add a share button** — encode the map state in the URL so it's shareable
- **Export to PNG** — use `html2canvas` to screenshot the tree
- **Save history** — persist past maps to `localStorage`
- **Switch to Claude API** — swap `callAI()` for a direct Anthropic API call for better JSON reliability
- **D3 layout** — replace the CSS flex layout with a proper D3 tree for larger maps
- **More nodes** — increase from 3-3-3 to 4-4-4 or add a 4th order tier

---

## Project structure

```
consequence-map/
├── index.html      # Everything — HTML, CSS, JS in one file
├── vercel.json     # Vercel rewrite rule (SPA fallback)
└── README.md
```

---

## License

MIT — do whatever you want with it.
