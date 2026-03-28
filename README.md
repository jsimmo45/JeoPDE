# 🧬 JeoPDE!

A Jeopardy-style quiz game about **programmed DNA elimination (PDE)** in nematodes. Single HTML file — no install, no server, just open and play.

Perfect for lab meetings, journal clubs, teaching, and conference booths.

## Play It

**Locally:** Download `index.html` and open in any browser.

**Online via GitHub Pages:**
1. Fork this repo
2. Settings → Pages → Source: `main` branch
3. Game is live at `https://YOUR-USERNAME.github.io/JeoPDE/`

Generate a QR code to the URL at [qrcode.tec-it.com](https://qrcode.tec-it.com/en) (free, no account, no watermark) and put it on a poster or slide.

## Features

- 54 questions across 10 PDE categories + Final JeoPDE!
- **TV-show flow**: clue appears → 5s reading period → 10s buzz-in window (tap or press Q/W/E) → 30s answer timer. If nobody buzzes, question is skipped
- 30-second countdown timer (gold bar in modal, turns red at 8s)
- Random Daily Doubles (1 in Round 1, 2 in Round 2, re-randomized each game)
- 1–3 players with score tracking; correct answerer keeps board control
- Skip buttons to jump to Round 2 or Final JeoPDE!
- Explanations after every answer
- Single-player friendly — buzz-in phase skipped automatically
- **Shared leaderboard** via Firebase (falls back to localStorage if not configured)
- **Admin controls** — password-protected clear all / delete individual scores
- Synthesized sound effects with mute button (no audio files needed)

## Firebase Setup (Shared Leaderboard)

Without Firebase, scores save locally per browser. To enable a shared leaderboard everyone can see:

1. Go to [Firebase Console](https://console.firebase.google.com) and create a free project
2. Click **Build → Realtime Database → Create Database** (start in test mode)
3. Click the gear icon → **Project Settings → General**, scroll to "Your apps", click the web icon (`</>`)
4. Register the app, then copy the config values
5. Open `index.html` and replace the placeholder values in `FIREBASE_CONFIG` near the top of the `<script>` block
6. Change `ADMIN_PASS` to your own password (default: `pde2026`)

Firebase's free tier handles thousands of score entries easily.

## Admin Controls

Click **🏆 Scores** → click the small **Admin** button at the bottom → enter your password. You can then delete individual entries (hover over a score to see the ✕ button) or clear all scores. Useful for resetting between conference sessions or breakout groups.

## Categories

**Round 1** ($100–$500): Elimin-8 or Not · Chromosomal Shenanigans · Germline vs Soma · Model Organisms · PDE Mechanisms

**Round 2** ($200–$1000): Hi-C & 3D Genome · CBRs & Breaks · Comparative Genomics · Epigenetic Marks · Evolution of PDE

## Adding Questions

All questions live in the `Q` object inside `index.html`. Each question follows this format:

```javascript
300: {
    q: "Your clue text here.",
    c: [
        "What is the correct answer?",
        "What is wrong answer 1?",
        "What is wrong answer 2?",
        "What is wrong answer 3?"
    ],
    a: 0,       // index of correct choice (0-3)
    exp: "Explanation shown after answering."
},
```

To add a new category, add a new key under `round1` or `round2` in the `Q` object. To add Final JeoPDE! questions, append to the `Q.final` array.

## Repository Structure

```
JeoPDE/
├── index.html   # Entire game (single file)
├── README.md
└── LICENSE
```

## Notes

- **Sound** is generated via Web Audio API — no audio files needed. Toggle with the 🔊 button.
- **GitHub Pages** serves `index.html` automatically — no build step, no server.
- The Firebase SDK loads from Google's CDN at runtime, so the game works offline too (just without the shared leaderboard).

## License

MIT — see [LICENSE](LICENSE)

## Author

**James Ryan Simmons, PhD** · University of Tennessee, Knoxville
