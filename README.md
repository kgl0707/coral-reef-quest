# Coral Reef Quest · 珊瑚礁生存挑战

An eight-level interactive science game about coral reefs — built as a **single HTML file** with inline SVG and vanilla JavaScript. No build step, no dependencies, no server. Open it and play.

All eight levels are about one question: **what does a coral need to survive?** You keep a reef alive through temperature swings, salt shocks, light limits, nutrient pollution, grazing pressure, and the chemistry of building a skeleton — then face a final round that combines everything.

## Play

<https://kgl0707.github.io/coral-reef-quest/>

## The eight levels

| # | Level | What you do |
|---|-------|-------------|
| 1 | 温度危机 / Heat Crisis | Drag the temperature into the coral's comfort band and watch the reef bleach when you overshoot |
| 2 | 盐度逃生 / Salinity Escape | Survive a salinity swing — too fresh or too salty and the polyps shut down |
| 3 | 阳光猜猜看 / Guess the Light | Drag the coral down the slope until it lands where the light is just right |
| 4 | 施肥陷阱 / The Fertilizer Trap | Add nutrients and watch algae take the reef over |
| 5 | 安家大作战 / Home Hunt | Find a settlement spot with the right substrate, light and current |
| 6 | 造骨头实验室 / Build a Skeleton | Balance calcium and carbonate so the coral can calcify |
| 7 | 地球仪大冒险 / Globe Adventure | Spin the globe to the latitudes where reef-building corals actually live |
| 8 | 终极生存挑战 / Final Challenge | Everything at once — keep the reef alive as the stressors stack |

## Features

- **Single file** — `index.html` is the whole game (about 100 KB). Copy it anywhere and it still works offline.
- **Keyboard control** — every slider accepts arrow keys, with on-screen key hints. Level 3 moves the coral, level 7 rotates the globe.
- **Reset anywhere** — levels 4, 5 and 8 have a restart button, so you can re-run a scenario without reloading.
- **Hand-drawn SVG reef** — corals, algae, fish and the globe are drawn with inline SVG, so the whole thing scales cleanly on any screen.
- **Chinese interface** — written for a middle-school science audience.

## Run locally

```bash
# just open the file
open index.html

# or serve it
python3 -m http.server 8000
```

## License

MIT — use it, remix it, teach with it.
