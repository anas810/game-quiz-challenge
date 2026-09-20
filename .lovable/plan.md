# Maze of Gains — 15-Question Quiz Site

## What we're building

A single-page quiz website about **Maze of Gains (MoG)**, the crypto maze/dungeon roguelike by Onchain Heroes on Abstract. Players:

1. Land on a start screen ("Enter the maze" button)
2. Answer 15 multiple-choice questions one at a time (4 options each)
3. Get instant right/wrong feedback with a short fact after each answer
4. See the final score out of 15, a fun rank title, and a Play Again button

Design direction chosen by the user: **Neon arcade dungeon** — dark purple background, cream text, volt-green/cyan/gold/magenta neon accents, chunky black borders with hard drop shadows, Bungee display font, game-feel animations (rise, pop, shake, pulse).

## Questions (based on real game facts from official/news sources)

The 15 questions cover: game genre, developer (Onchain Heroes), chain (Abstract), Golden Corn from Corn Stalks, modes that drop corn (Arcade/Expedition, not World's Eve), corn rate (10 Corn × keys), Arcade Key price ($1, max 100/run), weekly free Expedition Keys (3 free / 5 Basic / 8 VIP), free-run loot retention (nothing without a Pass), Deed Season (850 whitelist spots, Silo 575, 11 days), and ~90% of entry fees returned to players.

## Files to change

- `src/styles.css` — replace the default palette with the Neon arcade dungeon tokens (dark purple bg, volt/cyan/gold/magenta/correct/wrong accents), register the Bungee / Space Grotesk / Space Mono fonts, add the game-feel animations (rise, pop, pulse-glow, shake, blink)
- `src/routes/__root.tsx` — add Google Fonts `<link>` tags for the three fonts in the root head
- `src/lib/quiz-data.ts` — new file: the 15 questions, correct answers, explanations, and rank titles (Maze Warlord / Loot Baron / Maze Runner / Corn Farmer / Lost Newbie)
- `src/routes/index.tsx` — the full quiz: start screen, question flow with progress bar ("Depth") and floor counter, instant feedback, results screen with score + rank card + replay; its own page title and social meta

## Notes

- Frontend only — no database or login needed for a quiz
- Fully responsive (big tappable option buttons work on mobile)
- No real crypto, wallets, or transactions — purely a quiz
