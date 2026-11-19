# Ellison Game — Chef Pigeon 2

A single-file browser game. Chef Pigeon is baking the biggest bread in the sky when
Evil Pigeon curses the food — catch the good bread, dodge the dark bread and eggs, and
save Bread Day.

Everything (HTML, CSS, JavaScript, sounds) lives in [`index.html`](index.html). There is
no build step, no dependencies and no backend.

## Play

Open `index.html` in any modern browser, or serve the folder:

```bash
npx serve .
```

## Controls

| Action | Keyboard | Touch / mouse |
| --- | --- | --- |
| Move | `←` / `→` | Drag anywhere, tap, or hold the ◀ ▶ buttons |
| Hit the boss | `Space` | `HIT` button, or tap the boss |

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

## Deploy to Vercel

The repo is a static site: [`vercel.json`](vercel.json) only turns on clean URLs, and
`index.html` is served from the project root — no framework, build command or output
directory needed.

### Automatic deploys (GitHub Actions)

[`.github/workflows/deploy-vercel.yml`](.github/workflows/deploy-vercel.yml) deploys to
production on every push to `main` (and can be run manually from the Actions tab). It
needs three repository secrets under **Settings → Secrets and variables → Actions**:

| Secret | Where it comes from |
| --- | --- |
| `VERCEL_TOKEN` | <https://vercel.com/account/tokens> — create a token, scope it to this project if you like |
| `VERCEL_ORG_ID` | The `orgId` in `.vercel/project.json`, or the team/account ID in the Vercel dashboard |
| `VERCEL_PROJECT_ID` | The `projectId` in `.vercel/project.json`, or Project Settings → General |

The Vercel project has to exist before the first run. If the repo is connected through
Vercel's Git integration as well, turn automatic Git deploys off for the project so the
two don't both deploy on every push.

### Manual deploy

One-click import: <https://vercel.com/new/clone?repository-url=https://github.com/jayjaybeeuk/ellison-game>.

Or from the CLI:

```bash
npx vercel        # preview deployment
npx vercel --prod # production deployment
```
