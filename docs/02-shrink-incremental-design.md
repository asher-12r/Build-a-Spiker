# 02 — Shrink Incremental: Game Design (draft v0.1)

> **Pitch:** Buy shrinks. Get smaller. The world towers over you. Go so small
> you find a whole new universe.

Genre: a menu-heavy incremental in the style of Noob Incremental, plus physical
progress through a world like Depth Incremental and Tower Incremental. Instead
of moving up or down, **you move through scale.**

Working title: **Shrink Incremental** (or "+1 Shrink Incremental", following the
naming trend on Roblox).

---

## 1. Core loop

```
Earn Matter  →  Buy Shrinks (get smaller)  →  Reach a new Zone (more Matter/sec)
     ↑                                               ↓
 Upgrades  ←  Roll Particles (luck)  ←  Beat the Zone Boss to go deeper
     ↑                                               ↓
     └────────────  Rebirth for Essence (permanent power)  ←┘
```

- **Matter** is the main currency. It comes in every second, and you can tap
  for bonus Matter.
- **Shrinks** are the "steps." Each one multiplies your size by the Shrink
  Factor (base ×0.9).
- **Size** is the headline number, shown on screen like `0.00042 m` or
  `4.2 × 10⁻⁷ m`. Smaller is better.
- **Zones** are bands of scale. Each new zone multiplies Matter income.
- A **boss** sits at the bottom of every zone, and you must beat it to keep shrinking.

---

## 2. Zones (layers) and bosses

Sizes are loosely real-world. The number `m` = how many powers of ten you are
below 1 meter (`m = −log10(size)`).

| # | Zone | Size range | Look | Boss | Boss unlocks |
|---|---|---|---|---|---|
| 1 | **Bedroom** | 1 m → 1 cm | Giant Lego bricks, socks, toy cars | **House Spider** | Rebirth |
| 2 | **Carpet Jungle** | 1 cm → 100 µm | Carpet fibers as trees, crumbs as boulders | **Tardigrade** | Particle slot +1 |
| 3 | **Skin & Cells** | 100 µm → 1 µm | Pink cell walls, blood cells drifting | **Bacterium Bully** | Auto-Roll |
| 4 | **Molecule Maze** | 1 µm → 1 nm | Proteins like twisted ropes, DNA ladders | **Virus Queen** | Zone 5 |
| 5 | **Atom Field** | 1 nm → 1 pm | Glowing electron clouds orbiting | **The Atom** | **Collapse** (layer 2) |
| 6 | **Nucleus Core** | 1 pm → 1 fm | Dense glowing red/blue spheres | **Proton Titan** | Fusion |
| 7 | **Quark Sea** | 1 fm → 10⁻¹⁸ m | Colorful flickering triplets | **Quark Trio** (3-phase fight) | Zone 8 |
| 8 | **Quantum Foam** | 10⁻¹⁸ → 10⁻³⁵ m | Bubbling, warping space | **The Planck Wall** | **Big Bang** (layer 3) |
| ∞ | **The Void** | below Planck length | Darkness, then a tiny glowing universe | — | Enter a new universe |

**Bosses:** each boss has an HP bar. Your **Power** stat deals damage per
second automatically, and tapping adds burst damage. When a boss falls it drops
a boss-only particle and unlocks the next zone for good (until you rebirth).

---

## 3. Systems

### 3.1 Matter and Shrinks
| Thing | Starting formula | Notes |
|---|---|---|
| Size after *n* shrinks | `1 m × F^n`, F = 0.9 | ~22 shrinks per power of ten |
| Shrink cost | `5 × 1.12^n` Matter | Upgrades lower the 1.12 |
| Matter/sec | `base × zoneMult × upgrades × particles × essence` | `zoneMult = 4^(zone−1)` |
| Boss HP | `100 × 50^(zone−1)` | Tuned so bosses take 30–90 s at the "right" power |

These are first-draft numbers. We'll tune them with a spreadsheet or simulator
before building.

### 3.2 Particles (luck / roll system)
- You earn **Rolls** from shrinking (1 per 10 shrinks at first) and from bosses.
- Each zone has its **own particle pool**, so new zones mean new things to collect.
- Rarities: Common · Uncommon · Rare · Epic · Legendary · Mythic · **Secret**.
- Particles give stat multipliers (Matter, Luck, Power, cheaper shrinks, Shrink Factor).
- You **equip** a limited number (start with 3 slots, up to ~8 later).
- The **Collection Index** gives a permanent bonus for each unique particle
  found, so players keep chasing the full set.
- The **Luck** stat moves the odds toward rarer tiers.

Example pools:

| Zone | Common | Rare | Legendary | Secret |
|---|---|---|---|---|
| Bedroom | Dust Speck, Lint | Glitter | Lost Lego | Golden Crumb |
| Carpet | Fiber, Crumb | Pollen | Mite Egg | Diamond Dust |
| Cells | Water Drop | Ribosome | Stem Cell | Immortal Cell |
| Atoms | Electron | Photon | Neutrino | Antimatter |
| Quarks | Up / Down | Strange | Charm | **Higgs** |

### 3.3 Prestige layers (each unlocks a new mechanic)

| Layer | Unlocked by | Resets | You gain | New mechanic |
|---|---|---|---|---|
| **1. Rebirth** ("Grow Back") | Beat House Spider | Matter, Shrinks, Zone | **Essence** = `floor(2^(m−1))` | Essence upgrade tree; auto-buy shrinks |
| **2. Collapse** | Beat The Atom | Everything in layer 1 too | **Quanta** | **Fusion**: merge 5 duplicate particles into a higher tier. **Superposition**: earn from a second zone at the same time |
| **3. Big Bang** | Beat The Planck Wall | Everything in layers 1 and 2 | **Stardust** | **Universe Laws** (below) |

**Universe Laws** is the signature endgame idea. Every Big Bang creates a new
universe with **randomly rolled physics laws**, for example:
- *Heavy Gravity:* shrinks cost 2× more, but Matter is ×5
- *Unstable Atoms:* bosses have half HP but regenerate
- *Lucky Cosmos:* Luck ×3, Shrink Factor worse
- *Inverted:* tapping is 10× stronger, idle income is halved

You can keep a universe's laws or re-roll them. Each universe is a new
challenge run, which keeps the late game from becoming the same loop again.

### 3.4 Upgrades (first draft of the Matter tree)
| Upgrade | Effect | Scaling |
|---|---|---|
| Bigger Pockets | +1 base Matter/sec | Repeatable |
| Tap Power | +Matter per tap | Repeatable |
| Smooth Shrinking | Shrink cost growth 1.12 → down to 1.08 | Capped |
| Squeeze | Shrink Factor 0.9 → down to 0.8 | Capped |
| Lucky Eyes | +5% Luck | Repeatable |
| Roll Rush | Fewer shrinks per Roll | Capped |
| Tough Tiny | +Power (boss damage) | Repeatable |
| Zone Mastery | +x% income per zone beaten | Repeatable |
| Bulk Shrink | Buy ×10 / ×Max | One-time |

The Essence, Quanta and Stardust trees each get 15–30 upgrades of their own,
for "hundreds of upgrades" over time.

---

## 4. Signature feature: scale is something you see

Shrinking must feel like shrinking. **We don't actually shrink the character**,
because Roblox physics and cameras get weird at tiny sizes. Instead:

- Each zone is a separate, normal-sized map that *depicts* that scale.
- Inside a zone, the zone's props **smoothly grow** (`Model:ScaleTo`) with every
  shrink you buy. Fibers turn into trees, and crumbs turn into boulders.
- On a zone transition the screen whooshes, the camera zooms, and the next zone
  fades in.
- Zones render **on the client** for each player, so everyone can be at a
  different size on the same server.

**Social layer (light, like Noob Incremental):**
- The shared **Bedroom hub** is where everyone meets. Each player shows a size
  badge (e.g., "10⁻¹² m").
- A global **"Smallest Players"** leaderboard.
- A **Microscope** in the hub: zoom in on another player to see their current zone.

---

## 5. Monetization (fair-first)

Roblox data shows players moving away from heavy monetization, so no gamepass
blocks progress.

- **Gamepasses:** 2× Matter, Auto-Roll from the start, +1 particle slot,
  Fast Roll animation, VIP chat tag.
- **Dev products:** Luck potions (10 min), Matter boost (10 min), skip a boss
  cooldown.
- **Free:** codes at each update, group-join bonus, offline earnings (capped at 8 h).

---

## 6. Release plan

| Release | Content |
|---|---|
| **v1 (launch)** | Zones 1–4, 4 bosses, Rebirth + Essence tree, ~35 particles, ~25 Matter upgrades, saves, leaderboard, hub |
| **UPD1** | Zone 5 (Atoms), **Collapse** layer, Quanta tree, Superposition |
| **UPD2** | Zones 6–7, **Fusion**, Quark Trio boss |
| **UPD3** | Zone 8, **Big Bang**, Universe Laws |
| UPD4+ | Events (e.g., a "Halloween Germ" zone), more laws, more particles |

Ship v1 small and fast, then update every 1–2 weeks. Depth Incremental
reached "UPD4" within weeks of launch.

---

## 7. Technical notes (for the build phase)
- **Big numbers:** costs pass 10³⁰⁰ in later layers, so use a mantissa/exponent
  number type from day one.
- **Server-authoritative** currency and purchases. The client only asks.
- **Saving:** ProfileStore (or similar session-locked DataStore wrapper).
- **Code layout:** Rojo + Luau in this repo, so everything is version-controlled.

---

## 8. Open questions
1. Is the art style cute/cartoony or glowing/sci-fi? (It could change by zone:
   cartoon at first, sci-fi at the atom level.)
2. Should players see each other inside zones, or only in the hub?
3. Is the 3-layer depth right for launch scope, or should we plan a 4th layer early?
4. Final name?
