# 🦕 Poor Dino — Cope & Run

A richer, funnier take on the classic Chrome dino runner: a dinosaur too stubborn to
stay extinct, jogging through a thunderstorm under a colorful parachute while the game
mocks him the whole way.

![made with vanilla JS + Canvas](https://img.shields.io/badge/stack-vanilla%20JS%20%2B%20Canvas-4ecdc4)

## ✨ Features

- **Signature parachute mechanic** — the canopy pops open the instant the dino's feet leave the ground, visibly billows as it fills with air at the top of the jump, then pinches and squeezes shut as it nears the ground.
- **3 lives + heart pickups** — a hit costs a heart (with brief mercy invincibility) instead of an instant game over; once you're down a life, a glowing heart sometimes floats in that you can grab to earn one back (capped at 3).
- **Opening thunderstorm** — every run starts with heavy, wind-blown rain and lightning flashes + thunderclaps that ease off after a few seconds.
- **Sarcastic quips** — floating taunts start needling you around 15s and keep coming.
- **Air double-jump** — a live-filling power vessel (right side of the sky) charges over ~20s; when full, jump again in mid-air. Spends the meter, then recharges.
- **Meteor event** — a telegraphed "☄️ INCOMING!" warning, a flaming meteor crashes down, and leaves a smoking boulder to hurdle.
- **Shareable ending** — game over gives you a sarcastic rank + epitaph and an auto-generated score card you can copy, share (Web Share API), or download. 100% client-side — no server, no tracking.
- **Rich, hand-drawn graphics** (all procedural — zero image files):
  - Day → dusk → night → dawn sky cycle with a sun/moon that arcs across the sky and twinkling stars.
  - Parallax clouds and rolling hills.
  - A cheery cartoon dino that runs, jumps, ducks, blinks, and kicks up dust.
  - Cactus clusters and flapping pterodactyls.
  - Screen shake, particle puffs, and gentle sound effects.
- **Endless & responsive** — scales to any screen, works with keyboard, mouse, and touch.
- **High score** saved locally.

## 🎮 Controls

| Action | Keys | Touch |
| ------ | ---- | ----- |
| Jump   | `Space` / `↑` / `W` | Tap top ⅔ of screen |
| Duck   | `↓` / `S` | Hold bottom ⅓ of screen |
| Start / Restart | `Space` | Tap |
| Mute   | 🔊 button (top-left) | Tap button |

> The parachute is automatic — just jump and watch it deploy on the way down.

## ▶️ Run locally

It's a static site, so anything that serves files works. For example:

```bash
# Python
python -m http.server 8000
# or Node
npx serve .
```

Then open <http://localhost:8000>. (Opening `index.html` directly in a browser also works.)

## 🚀 Deploy online

### Vercel
1. Push this folder to a GitHub repo (or run `npx vercel`).
2. Import the repo at [vercel.com/new](https://vercel.com/new).
3. Framework preset: **Other** · Build command: *(empty)* · Output dir: `.`
4. Deploy — you get a public `https://your-project.vercel.app` link.

Or from this folder, without a repo:
```bash
npx vercel --prod
```

### Netlify
- **Drag & drop:** zip or drag this folder onto <https://app.netlify.com/drop>.
- **CLI:** `npx netlify deploy --prod --dir .`
- **Git:** connect the repo; `netlify.toml` already sets publish dir to `.` with no build.

## 📁 Project structure

```
poor-dino/
├── index.html    # markup, HUD, overlays
├── style.css     # UI / overlay styling
├── game.js       # game engine + all procedural graphics
├── vercel.json   # static hosting config (Vercel)
├── netlify.toml  # static hosting config (Netlify)
└── README.md
```

Built with plain HTML, CSS, and the Canvas 2D API — no frameworks, no build step.
