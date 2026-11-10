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
- **Cover first, then one level at a time** — a title screen with an undersea scene, then levels unlocked in order; each level ends with 上一关 / 下一关 instead of a jump menu. Progress is saved in `localStorage`, and 重置 clears it.
- **Five hidden easter eggs** — 🐚 🦀 🐙 🐠 ⭐ tucked into the scenes of levels 1, 2, 3, 4 and 8. Clicking one fires a small confetti burst and opens a centred card explaining the fact behind it; the 🥚 counter in the top bar opens a collection list. All five unlock a closing message.
- **Keyboard control** — every slider accepts arrow keys, with on-screen key hints. Level 3 moves the coral, level 7 rotates the globe.
- **Reset anywhere** — levels 4, 5 and 8 have a restart button, so you can re-run a scenario without reloading.
- **Observation room (观察室)** — a collapsible panel with 3-D flip cards, one per relevant level:
  - level 1: eight temperature bands (`<16.5 / 16.5–18 / 18–23 / 23–29 / 29–30.5 / 30.5–32 / 32–34.5 / >34.5 ℃`), each labelled with its growth rate;
  - level 2: four salinity bands (`33–36‰` isotonic / `30–32‰` fresher / `36–38‰` saltier / `<30‰` lethal), with the open-sea ≈ 35‰ reference under the cards;
  - level 3: three light budgets (≥20 % surplus / 8–20 % break-even / <8 % sustained deficit);
  - level 4: four nutrient stages (`0–14 / 15–39 / 40–71 / ≥72`);
  - level 8: the eight indicators as a green/yellow table, plus seven disasters that each move exactly one dial (warming +2–3 ℃, storm −3.5–5.5‰, sewage +16–26, typhoon current surge, acidification −0.06 pH, coastal works → mud, trawling +14 nutrients).

  The front shows the phenomenon, the back explains the mechanism; a summary line above the cards ties the stages into one chain.
- **Chinese / English toggle** — the `EN` button in the top bar (and on the cover) switches the whole page, including everything drawn inside the SVG scenes. The choice is remembered, and can be linked directly: `?lang=en`, `?lv=5&lang=en`.
- **"Why did that fail?" cards** — pushing a dial into the lethal band opens a centred modal that explains the mechanism, not just the result. Thirteen triggers cover all eight levels: temperature (lethal / dying / too cold), salinity (too fresh at a river mouth, and too salty in the final round), light, nutrients, current (too still / too fast), aragonite saturation, site choice (river mouth / high latitude), and a summary when the final reef collapses — which lists the indicators that actually dragged it down. Each reason fires once per attempt, resets with that level's restart button, and the level clock pauses while the card is open.
- **Hand-drawn SVG reef** — corals, algae, fish and the globe are drawn with inline SVG, so the whole thing scales cleanly on any screen.
- **Visual pass (2026-11)** — the cover's light shafts are blurred and layered over a soft ambient glow (no hard edges), the page is vignetted so the title sits in a pool of light, and the shell got a quieter texture. Inside the app: a wider 1160 px measure, a glassy fixed top bar, a lit "window" around each scene (inner glass edge + outer glow), filled slider tracks, glowing flip cards, and a compact footer progress bar. Short laptop screens (≤ 850 px tall) automatically use a narrower measure so scene + controls + feedback still fit on one screen.
- **Written for a middle-school science audience.**
- **Deep links** — `?lv=3` opens level 3 directly, `?lang=en` opens in English.

## Run locally

```bash
# just open the file
open index.html

# or serve it
python3 -m http.server 8000
```

## License

MIT — use it, remix it, teach with it.
