# Coral Reef Quest · 珊瑚礁生存挑战

An eight-level interactive science game about coral reefs — built as a **single HTML file** with inline SVG and vanilla JavaScript. No build step, no dependencies, no server. Open it and play.

All eight levels are about one question: **what does a coral need to survive?** You keep a reef alive through temperature swings, salt shocks, light limits, nutrient pollution, grazing pressure, and the chemistry of building a skeleton — then face a final round that combines everything.

## Play

<https://kgl0707.github.io/coral-reef-quest/>

## The eight levels

| # | Level | What you do |
|---|-------|-------------|
| 1 | 温度危机 / Heat Crisis | Drag the temperature from 15 °C to 35 °C: bleaching from 30.5 °C, mass mortality above 32 °C, everything dead at 34.5 °C and 15 °C |
| 2 | 盐度逃生 / Salinity Escape | Survive a salinity swing — too fresh or too salty and the polyps shut down |
| 3 | 阳光猜猜看 / Guess the Light | Drag the coral down the slope until it lands where the light is just right |
| 4 | 施肥陷阱 / The Fertilizer Trap | Add nutrients and watch algae take the reef over |
| 5 | 安家大作战 / Home Hunt | Find a settlement spot with the right substrate, light and current |
| 6 | 造骨头实验室 / Build a Skeleton | Balance calcium and carbonate so the coral can calcify |
| 7 | 地球仪大冒险 / Globe Adventure | Spin the globe to the latitudes where reef-building corals actually live |
| 8 | 终极生存挑战 / Final Challenge | Everything at once — keep the reef alive as the stressors stack |

## The thresholds behind the numbers

The model is simplified, but every cut-off follows the ranges used in textbooks and the reef literature. The ones worth checking:

| Variable | Value used | Why |
|---|---|---|
| Temperature, optimal | 23–29 °C | Standard range for reef-building corals |
| Temperature, stress onset | > 29 °C | ~1 °C above the usual summer maximum |
| Temperature, bleaching | 30.5–32 °C | Symbionts expelled; **reversible** if the water cools |
| Temperature, mass mortality | 32–34.5 °C | Tissue necrosis begins; mortality climbs steeply |
| Temperature, lethal | ≥ 34.5 °C / ≤ 15 °C | Whole reef dies — this is **not** bleaching |
| Salinity, optimal | 34–36‰ | Normal seawater |
| Salinity, marginal | 30‰ | Survives, but spends energy on osmoregulation |
| Salinity, lethal | 18‰ | Cells take on water; estuaries have no reefs |
| Light for reef growth | ≥ 20% of surface | Below ~8% the coral starves |
| Aragonite saturation | Ω < 2.4 | Net dissolution overtakes calcification |

Two ideas the game tries hard to keep separate: **bleaching is reversible, death is not**, and the lethal limit exists at *both* ends of the thermometer — a cold snap kills corals just as a heatwave does.

## Features

- **Single file** — `index.html` is the whole game (about 100 KB). Copy it anywhere and it still works offline.
- **Keyboard control** — every slider accepts arrow keys, with on-screen key hints. Level 3 moves the coral, level 7 rotates the globe.
- **Reset anywhere** — levels 4, 5 and 8 have a restart button, so you can re-run a scenario without reloading.
- **Observation room (观察室)** — inside level 4, a collapsible panel holds four flip cards (0–14 / 15–39 / 40–71 / ≥72). The front shows the phenomenon, the back explains the mechanism; a summary line above the cards ties the four stages into one chain of feedback.
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
