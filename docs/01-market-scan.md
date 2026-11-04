# 01 — Market scan: Roblox incremental games (Nov 2026)

Step 1 of planning. A quick look at what's working in Roblox incrementals right
now, so we can decide where our game fits.

> Caveat: numbers come from web search snippets (many from SEO blogs that
> disagree with each other). Check the live Roblox charts before relying on any
> specific figure.

## 1. The "pure" incremental niche (games with Incremental/Idle/Clicker in the name)

| Game | Signal | Core hook |
|---|---|---|
| Speed Clicker | ~293M visits (most visited in the niche) | Click to gain speed, simple loop |
| Noob Incremental (Ghoulax Games) | ~52M visits, ~4K CCU, ~96% rating | Buy Noobs → earn "Oof" → hundreds of upgrades → rune rolling (luck layer) → ~4 prestige layers |
| Grass Incremental Simulator (Unequal Games) | ~42M visits, low CCU now | Cut grass → currency → upgrades → prestige |
| Immortality Incremental | ~98% rating | Layered prestige |
| Matrix Incremental | ~95% rating | Layered prestige |
| Clicker Simulator, +1 Drain Water Per Click | On top-rated lists | "+1 per click" stat-growth loop |

Takeaways:
- Noob Incremental is the only title that ranks high on **both** visits and
  rating. It's the main game to study.
- The well-rated games share three things: **lots of upgrades**, **several
  prestige layers that each unlock a new mechanic**, and a **luck/RNG layer**
  (runes) on top of the number-go-up.
- Visit counts are modest next to the front page. Pure incrementals are a loyal
  niche, not a mass-market genre on Roblox.

## 2. The mass market: incremental loops wearing a theme

Roblox's biggest hits are incremental games in disguise:

- **Grow a Garden** (record ~21M+ CCU, 2025): plant → wait → sell → buy better
  seeds. It's idle and incremental, with rare mutations (RNG) and limited-time events.
- **Steal a Brainrot** (all-time record ~25M CCU, Oct 2025): collect units that
  generate cash per second, plus a **social/PvP twist** (steal from other bases).
- **Steal An Egg** (reported #1 on live charts, Nov 2026): the same "steal a X"
  formula, and reportedly built mostly with AI tools.

Takeaways:
- The winning recipe = **an incremental core** + **a theme kids instantly get** +
  **collectible rarity (RNG)** + **social interaction** + **frequent updates and
  events**.
- Copies of a hit flood the platform within weeks. Players complain about
  low-effort clones, so we need a twist of our own, not a reskin.

## 3. Platform context (2026)

- Roblox launched **Build** (Jul 2026), a tool that turns a text prompt into a
  game. It has produced 70K+ games in a few months, so the platform is
  **flooded with content**. Standing out needs a strong hook and a clear thumbnail
  and icon.
- Over 80% of top-100 games use AI to speed up development.
- Roblox said in its Q2 2026 results that players are moving toward games with
  **fewer monetization opportunities**, and only ~1.4% of DAU pay. Aggressive
  paywalls are a risk. Prefer generous free progression and cosmetic or
  convenience gamepasses.

## 4. Design lessons to carry forward

1. **The first 30 seconds must show numbers going up** and give the first upgrade.
2. **Each prestige layer should unlock a new *mechanic*,** not just a bigger multiplier.
3. **Add a skill or variety element** (DevForum retention advice cites Bee Swarm
   Simulator: progress depends partly on stats and partly on how well you play).
4. **Give offline/idle progress** so players come back.
5. **Use an RNG collectible layer** (pets, runes, mutations) for "one more roll" sessions.
6. **Add a social layer** (trading, visiting or stealing, leaderboards) to spread
   the game by word of mouth.
7. **Plan the update cadence from day one.** Successful small teams ship content every 1–2 weeks.

## 5. Open questions for the next step

- What is the theme? The repo is named **Build-a-Spiker**. What is a "Spiker"?
  (volleyball? a spiky creature? a spike trap?)
- Solo or social? (Pure incremental vs. a base-building game with player interaction)
- Target session length and audience age?
- Scope for v1: how many weeks, and who is building it?

## Sources
- [List of Roblox games (Wikipedia)](https://en.wikipedia.org/wiki/List_of_Roblox_games)
- [Steal a Brainrot (Wikipedia)](https://en.wikipedia.org/wiki/Steal_a_Brainrot)
- [Grow a Garden (Wikipedia)](https://en.wikipedia.org/wiki/Grow_a_Garden)
- [Best Roblox incremental, idle & clicker games — rbxtcg](https://rbxtcg.com/en/guides/incremental-idle)
- [Best Roblox Idle & Incremental Games (2026) — Top Incremental Games](https://www.topincrementalgames.com/lists/best-roblox-idle-games)
- [Most Played Roblox Games Right Now (Nov 2026) — livecounts](https://livecounts.nl/roblox-charts/)
- [Noob Incremental prestige layers wiki](https://noobincrementals-wiki.pages.dev/wiki/prestige/)
- [Roblox Introduces Build (Roblox IR)](https://ir.roblox.com/news/news-details/2026/Roblox-Introduces-Build-A-New-Way-to-Create-on-the-Platform/default.aspx)
- [PC Gamer — 70,000 games published via Build](https://www.pcgamer.com/software/ai/ai-powered-game-development-is-leading-to-an-explosion-of-content-roblox-says-as-it-brags-about-70-000-games-published-on-its-platform-in-the-last-5-months-alone/)
- [PocketGamer.biz — 80% of top games use AI](https://www.pocketgamer.biz/more-than-80-of-robloxs-top-games-now-use-ai-while-playgama-tracks-the-tools-developers-prefer/)
- [GamingHQ — Roblox players reject microtransactions](https://gaminghq.eu/2026/08/07/roblox-stock-crashes-players-reject-microtransactions/)
- [DevForum — What is the perfect grind? (retention)](https://devforum.roblox.com/t/what-is-the-perfect-grind-a-post-about-retention/409330)
- [DevForum — Guide To Making a Good Roblox Game](https://devforum.roblox.com/t/guide-to-making-a-good-roblox-game/1569149)
- [Machinations — How to design idle games](https://machinations.io/articles/idle-games-and-how-to-design-them)
