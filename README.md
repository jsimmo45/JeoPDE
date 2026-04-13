# 🧬 JeoPDE!

A Jeopardy-style quiz game about **programmed DNA elimination (PDE)** across the tree of life. Single HTML file — no install, no server, just open and play.

Perfect for lab meetings, journal clubs, teaching, and conference booths.

## Play It

**Locally:** Download `index.html` and open in any browser.

**Online via GitHub Pages:** `https://jsimmo45.github.io/JeoPDE/`


## Features

- **120+ questions** across 24 categories — 5 randomly selected per round each game, so every playthrough is different
- **TV-show flow**: clue appears → 5s reading period → 10s buzz-in window (tap or press Q/W/E) → 30s answer timer. If nobody buzzes, question is skipped
- Random Daily Doubles (1 in Round 1, 2 in Round 2)
- 1–3 players; correct answerer keeps board control
- Skip buttons (Round 2, Final)
- Explanations after every answer
- Single-player friendly
- **Shared leaderboard** via Firebase (localStorage fallback)
- **Admin controls** — password-protected score management
- Synthesized sound effects with mute button
- Mobile-friendly with horizontal scroll on portrait

## Question Topics

**Round 1 pool** (12 categories, 5 randomly chosen):
Elimin-8 or Not · Chromosomal Shenanigans · Germline vs Soma · Model Organisms · PDE Mechanisms · Songbirds & the GRC · Nematode Diversity · PDE by the Numbers · Repeats & Satellites · History of PDE · Caenorhabditis Surprise · PDE Across Life

**Round 2 pool** (10 categories, 5 randomly chosen):
Hi-C & 3D Genome · CBRs & Breaks · Comparative Genomics · Epigenetic Marks · Evolution of PDE · Karyotype Evolution · Cell Biology of PDE · Beyond Nematodes · Sex & Elimination · Techniques & Tools

**Final JeoPDE!:** 8 questions randomly selected

Covers: *Ascaris*, *Parascaris*, *Oscheius tipulae*, *Mesorhabditis*, *Auanema rhodensis*, *Caenorhabditis* (Stevens et al. 2025), *Baylisascaris*, *Toxocara*, *Strongyloides*, songbird GRC, lampreys, hagfish, ciliates, bandicoots, and more.

## Adding Questions

Find the `Q` object in `index.html`. Each question:

```javascript
300: {
    q: "Your clue text.",
    c: ["What is correct?", "Wrong 1", "Wrong 2", "Wrong 3"],
    a: 0,
    exp: "Explanation shown after answering."
},
```

Add new categories freely — the game randomly picks 5 per round, so more categories = more variety.

## Firebase Setup (Shared Leaderboard)

1. [Firebase Console](https://console.firebase.google.com) → create project → Realtime Database (test mode)
2. Project Settings → Web app → copy config
3. Replace `FIREBASE_CONFIG` values in `index.html`
4. Change `ADMIN_PASS` (default: `pde2026`)

## Repository Structure

```
JeoPDE/
├── index.html
├── README.md
└── LICENSE
```

## License

MIT — see [LICENSE](LICENSE)

## Author

**James Ryan Simmons, PhD** · University of Tennessee, Knoxville
