# 🧬 JeoPDE!

A Jeopardy-style quiz game about **programmed DNA elimination (PDE)** across the tree of life. Single HTML file — no install, no server, just open and play.

Perfect for lab meetings, journal clubs, teaching, and conference booths.

## Play It

**Locally:** Download `index.html` and open in any browser.

**Online via GitHub Pages:** `https://jsimmo45.github.io/JeoPDE/`

## Features

- **268 clues across 48 categories** — 5 categories drawn per round, so no two games match
- **Four difficulty tiers**: Intro (outreach and undergrads), Standard, Journal club, and **Roscoff 2026** — a tier built from the Jacques Monod conference speakers' own papers, with every explanation citing its source
- **Three ways to answer**: multiple choice, typed free response (fuzzy matched), or host mode — clue on screen, teams answer aloud, host rules
- **TV-show flow**: clue appears → reading period → buzz-in window (tap or press Q/W/E) → answer timer
- **Rebound** — if the player who buzzes misses, the clue opens to everyone else
- No deduction on a timeout; money is only lost on a wrong lock-in
- **Undo** the last ruling, or flip any ruling with "count it as correct"
- Random Daily Doubles (1 in Round 1, 2 in Round 2) with True Double wagering
- **Final JeoPDE!** played one player at a time — private wagers and answers, pass-the-laptop handoffs
- **Projector mode** — scales the interface up, hides chrome, goes fullscreen
- **Session memory** — categories and Finals already played are skipped until the pool runs low
- **Resume after refresh** — an interrupted game is offered back with scores intact
- Answer choices shuffle every draw; explanations after every clue
- **Shared leaderboard** via Firebase (localStorage fallback) with password-protected admin controls
- Synthesized sound effects with mute; keyboard play throughout

## Question Topics

**Standard pool** — the original 22 categories plus 6 new ones:

*Round 1:* Elimin-8 or Not · Chromosomal Shenanigans · Germline vs Soma · Model Organisms · PDE Mechanisms · Songbirds &amp; the GRC · Nematode Diversity · PDE by the Numbers · Repeats &amp; Satellites · History of PDE · Caenorhabditis Surprise · PDE Across Life · Telomeres, Healed · Why Eliminate? · Parasites &amp; Hosts

*Round 2:* Hi-C &amp; 3D Genome · CBRs &amp; Breaks · Comparative Genomics · Epigenetic Marks · Evolution of PDE · Karyotype Evolution · Cell Biology of PDE · Beyond Nematodes · Sex &amp; Elimination · Techniques &amp; Tools · Small RNAs &amp; Argonautes · Genome Assembly · Two Ways to Eliminate

**Intro tier:** DNA Basics · Meet the Worms · Throwing DNA Away · Birds With a Secret · How Scientists Look · Big Numbers, Tiny Worms

**Journal club tier:** Primary Literature · Methods in Detail · Hard Numbers · Mechanism, Molecular · Comparative, Hard Mode · Open Questions

**Roscoff 2026 tier:** Ciliate Machinery · Chromosomes That Leave · Whose Genome Goes? · Nematode PDE · Ciliates, Harder · Birds &amp; Fish · Selfish Elements · Mechanism &amp; Models

**Final JeoPDE!:** 16 clues, one drawn per game

Covers: *Ascaris*, *Parascaris*, *Toxocara*, *Baylisascaris*, *Strongyloides*, *Oscheius tipulae*, *Mesorhabditis*, *Auanema rhodense*, *Caenorhabditis*, *Paramecium*, *Tetrahymena*, *Euplotes*, *Chilodonella*, sciarid fungus gnats, mealybugs, *Drosophila* B chromosomes, *Aegilops* and sorghum, *Cobitis* and *Hexagrammos* fish, lampreys, hagfish, songbird GRCs, the African pygmy mouse, and more.

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

The correct answer's index is `a`, and choices are shuffled at runtime, so `a: 0` is fine for every clue. Add new categories freely — the game picks 5 per round, so more categories means more variety.

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
