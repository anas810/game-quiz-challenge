# Maze of Gains — 15-Question Quiz Site

## What we're building

A single-page quiz website about **Maze of Gains (MoG)**, the crypto maze/dungeon roguelike by Onchain Heroes on Abstract. Players:

1. Land on a start screen ("Enter the maze" button)
2. Answer 15 multiple-choice questions one at a time (4 options each), easy → hard
3. Go straight to the next question after choosing — no right/wrong feedback during play
4. See a fun score card at the end: score out of 15, an in-game rank title, and a "Post on X" button that opens X's tweet composer with a prefilled brag
5. Refreshing the page serves a fresh question set — the pool has ~24 questions, 15 are drawn at random each load, so at least 5 are different every replay

Design direction chosen by the user: **Neon arcade dungeon** — dark purple background, cream text, volt-green/cyan/gold/magenta neon accents, chunky black borders with hard drop shadows, Bungee display font, game-feel animations (rise, pop, pulse-glow).

## Behavior details

- **No instant feedback**: after tapping an option it just highlights as selected; the "Descend" button advances. Correct answers are never revealed during play.
- **No play-again button** on the results screen.
- **Results card**: big score (e.g. 12/15) + rank title + "Post on X" button. The tweet opens via X's web intent URL with text like "I scored 12/15 on the Maze of Gains quiz — rank: Silo Stocker".
- **Difficulty curve**: questions 1–5 easy (game basics), 6–10 medium (keys, passes, fees), 11–15 hard (exact numbers and event details).
- **Question rotation**: quiz data holds a larger pool (~24 questions); each page load shuffles and picks 15 in difficulty order, guaranteeing at least 5 new questions on a refresh.

## Rank titles (from real MoG/Onchain Heroes vocabulary)

- 0–4: **Fresh Spawn**
- 5–8: **Corn Farmer**
- 9–11: **Expeditioner**
- 12–14: **Silo Stocker**
- 15/15: **Certified Mogger** (the actual in-game badge is the "Mogger" Abstract badge)

## Questions (based on real game facts from official/news sources)

Topics: game genre, developer (Onchain Heroes), chain (Abstract), Golden Corn from Corn Stalks, modes that drop corn (Arcade/Expedition, not World's Eve), Arcade Key price ($1, max 100/run), weekly free Expedition Keys (3 free / 5 Basic / 8 VIP), corn rate (10 Corn × keys), free-run loot retention (nothing without a Pass), ~90% of entry fees returned, Deed Season (850 whitelist spots, Silo 575 / Raffle 275, 11 days), MoG 2.0 (persistent upgrades, pattern-based combat), World's Eve items, wallets supported (MetaMask, Rabby, Robinhood).

## Files to change

- `src/styles.css` — replace the default palette with the Neon arcade dungeon tokens (dark purple bg, volt/cyan/gold/magenta accents), register the Bungee / Space Grotesk / Space Mono fonts, add the game-feel animations
- `src/routes/__root.tsx` — add Google Fonts `<link>` tags for the three fonts in the root head
- `src/lib/quiz-data.ts` — new file: the question pool with difficulty tiers, and the rank titles
- `src/routes/index.tsx` — the full quiz: start screen, question flow with progress bar ("Depth") and floor counter, no-feedback advancing, results score card with Post on X; its own page title and social meta

## Notes

- Frontend only — no database or login needed for a quiz
- Fully responsive (big tappable option buttons work on mobile)
- No real crypto, wallets, or transactions — purely a quiz
