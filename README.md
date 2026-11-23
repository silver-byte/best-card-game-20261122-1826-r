# Ember & Tide — Arcane Card Duel

[![Ember & Tide on make.fun](https://make.fun/badge/best-card-game-20261122-1826.svg)](https://make.fun/bounty/best-card-game-20261122-1826)
[![rank](https://make.fun/badge/best-card-game-20261122-1826/silver-byte/best-card-game-20261122-1826-r/rank.svg)](https://make.fun/bounty/best-card-game-20261122-1826)
[![reward](https://make.fun/badge/best-card-game-20261122-1826/silver-byte/best-card-game-20261122-1826-r/reward.svg)](https://make.fun/bounty/best-card-game-20261122-1826)

Play as Marin, the Tide Caller, in an offline duel against Pyra, the Ember Witch. Use four schools of magic to break her defenses while keeping your own Life above zero.

## How to play

- Start with 20 Life, 0 Shield, and five cards. Each turn starts with 3 Energy, a draw if you have room, and a Burn tick if you're afflicted. You can hold up to five cards; an empty deck reshuffles its discard pile.
- Click a card or press its **1–5** key to pay its Energy cost and cast it. Click **End Turn** or press **Space** to let Pyra act. Press **Enter** to start or rematch, and click **♪ Sound** to toggle the synthesized effects.
  **Rematch** reuses the same seed, so the duel repeats card-for-card if you make the same moves. Add `?seed=2` to the game URL for a fresh shuffle.
- **Ember** burns and attacks; **Tide** attacks and heals; **Thorn** shields and draws; **Star** mixes offense and support. Damage drains Shield before Life. Healing tops out at 20 Life. Burn deals one damage per stack, then loses one stack. Draw adds cards immediately; some spells apply two effects.
- Pyra takes a lethal hit if she can land one. She also finishes you with two spells if their combined Energy cost fits her remaining Energy and their combined damage covers your Life + Shield. Otherwise, at 8 Life or less she uses her cheapest affordable heal. Next she prefers the highest-cost affordable damage spell, then the highest-cost affordable shield, then the leftmost affordable spell. Ties go to the leftmost card.
- Change the shuffled decks with `?seed=2` or browse all 16 spells with `?shot=atlas`.

## Run it

Use Node.js 22.18 or newer. Run `node serve.ts`, then open <http://localhost:8080> in desktop Chrome. You can also open `game/index.html` directly for offline play.

```sh
MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Deterministic screenshots

- Play cover: `?shot=play&seed=278`
- Victory: `?shot=win&seed=1`
- Defeat: `?shot=loss&seed=1`
- The title screen is static (`?shot=title`).
