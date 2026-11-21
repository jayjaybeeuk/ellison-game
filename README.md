# Ellison Game

A tiny arcade of single-file browser games. [`index.html`](index.html) is the menu:

| Game | File |
| --- | --- |
| 🐦‍⬛ **Chef Pigeon 2** | [`chef-pigeon-2.html`](chef-pigeon-2.html) |
| 🐦 **Pigeon Tube** | [`pigeon-tube.html`](pigeon-tube.html) |
| 🐦 **Dad Attack** | [`dad-attack.html`](dad-attack.html) |

Every game is one self-contained HTML file — no build step, no dependencies and no
backend.

## Play

Open `index.html` in any modern browser and pick a game, or serve the folder:

```bash
npx serve .
```

### 🐦‍⬛ Chef Pigeon 2

Chef Pigeon is baking the biggest bread in the sky when Evil Pigeon curses the food —
catch the good bread, dodge the dark bread and eggs, and save Bread Day.

## Controls

| Action | Keyboard | Touch / mouse |
| --- | --- | --- |
| Move | `←` / `→` | Drag anywhere, tap, or hold the ◀ ▶ buttons |
| Hit the boss | `Space` | `HIT` button, or tap the boss |
| Full screen | — | The `⛶` button in the top-right corner of the board (`✕` to exit) |

## What's in it

- **Stage 1** — reach 500 points, then beat the Evil Pigeon boss (10 HP).
- **Stage 2** — unlocked by catching all 41 original collectibles. Twice as fast, 50%
  elemental food, tougher eggs, and the Dark King Pigeon final boss (25 HP).
- **Collectibles** — 47 in total: 41 original + 6 flavoured breads (Stage 2 only), plus
  16 elemental variants, hidden pages and three secret endings.
- **Power-ups** — shield (blocks eggs for 5s), magnet (5s), hearts, golden hearts,
  rainbow heart. The dark heart is a gamble: +30 health, −100 points.
- **Daily rewards** over 30 days and playtime rewards, including Rainbow Gary at day 30
  and Rainbow Kevin at 60 minutes played.

Progress (collection, best score, daily streak, playtime) is saved in the browser's
`localStorage`, so it stays with that browser and is not synced between devices.

### 🐦 Pigeon Tube

Grow a pigeon YouTube channel: post videos (then watch them), release songs (then listen
to them), visit rival bread shops to buy their stock, copy their recipes and challenge
them on the bread leaderboard, run the tower defense (the Pigeon Boss arrives at wave
750), buy shaders and prestige. Progress is saved in `localStorage`.

### 🐦 Dad Attack

An angry dad is loose in the arena and he is getting faster. Steer the pigeon
with the mouse or a finger, stay out of reach and grab bonuses: ⭐ +25 points,
⚡ a speed burst, 🛡 a shield that survives one catch and ❄ a short freeze for
dad. Score is survival time plus stars, and your best is saved in `localStorage`.

## Deploy to Vercel

The repo is a static site: [`vercel.json`](vercel.json) only turns on clean URLs, and the
HTML files are served from the project root — no framework, build command or output
directory needed. With clean URLs on, the menu is `/`, the games are `/chef-pigeon-2`,
`/pigeon-tube` and `/dad-attack`.

### Automatic deploys

The Vercel project is connected to this GitHub repo, so every push to `main` deploys to
production (and other branches get preview deployments). Nothing needs to be stored in
GitHub — Vercel holds the Git connection itself.

To deploy from a CI pipeline instead, use Vercel's documented flow —
`vercel pull --yes --environment=production`, `vercel build --prod`, then
`vercel deploy --prebuilt --prod` — with `VERCEL_TOKEN`, `VERCEL_ORG_ID` and
`VERCEL_PROJECT_ID` supplied as secrets.

### Manual deploy

One-click import: <https://vercel.com/new/clone?repository-url=https://github.com/jayjaybeeuk/ellison-game>.

Or from the CLI:

```bash
npx vercel        # preview deployment
npx vercel --prod # production deployment
```
