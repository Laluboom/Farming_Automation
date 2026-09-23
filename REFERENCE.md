# Farming_Automation — Reference

## What this is right now

A **research notebook, not yet an automation.** There is no executable code in this
repo: 26 markdown files, one PDF, no `.py`/`.ino`/`.js` of any kind. Reviewed
2026-09-23; verdict **REVIVE** (see `TODO.md`).

An automated daily research agent ran 2026-06-04 → 2026-06-16 and did something
genuinely useful: it took a broad question and converged it, one decision per day,
into a completely specified beginner irrigation prototype. The thinking is done. The
build has not started.

## The two main questions

`main_question.md` holds both:

1. **AI plant intelligence** — diagnose a plant from images + species + soil +
   climate. Explored only at the dataset level (PlantVillage, PlantDoc, IP102; TRY,
   GBIF, SoilGrids, WorldClim, ECOCROP, AquaCrop, DSSAT). Conclusion reached: disease
   *image* datasets are mature, but no single dataset covers water/nutrient/soil
   requirements. **No further work done on this branch.**
2. **Farm automation and decision-making** — this is what all nine wiki pages
   actually pursue, and it is the live thread.

`light_pest_control/` is a third, unrelated question (blue-light insect control) added
2026-09-21. It has a main question and a source PDF but **zero wiki pages** — an empty
scaffold. See `TODO.md` item 4.

## The prototype the research settled on

One outdoor tomato bed, drip-irrigated, with a single yes/no watering decision:

- 30 in raised bed, one trellised row, plants 18–24 in apart, beds on 4 ft centers
- 5/8 in drip tape, 12 in emitter spacing, ~0.45 gpm per 100 ft, 10 mil wall,
  laid ~2 in off the plant line
- One soil-water-tension sensor at 6 in depth, read once daily at a fixed time
- Irrigate when tension reaches 25–30 cb; run for 110 minutes
- Skip and recheck if ≥0.25 in of rain is forecast within 24 h
- Recheck the next day, never off the immediate post-run reading
- Log: daily reading, each runtime event, rainfall, rain-delay flag

Soil context is loam / silt loam, bare ground or permeable mulch. Sources are US
extension services (Penn State, Oregon State, Utah State, Missouri, UF IFAS) plus Toro
drip-tape literature; every page separates confirmed facts from inference.

## Layout

| Path | Contents |
|---|---|
| `main_question.md` | The two driving questions and sub-questions |
| `wiki/pages/` | 9 sourced decision pages — the real substance |
| `wiki/INDEX.md` | Page index. **Line 14 links to a file that does not exist.** |
| `research_reports/latest_report.md` | Last research run (2026-06-16) |
| `research_reports/run_logs/` | Dated logs, 2026-06-04 → 2026-06-16 |
| `light_pest_control/` | Separate question, empty wiki |
| `TODO.md` | Ranked next steps |

## How to run it

You can't — there is nothing to run. `TODO.md` item 1 defines the smallest change
that makes this false.

## Known defects

- `wiki/pages/first-runtime-rule-for-outdoor-tomato-drip-irrigation.md` was never
  committed but is cited by six files; the 110-minute runtime has no surviving
  derivation, and that day's run log is missing too.
- `first-drip-tape-specification-...:44` still calls wall thickness unfixed; a later
  page fixed it at 10 mil.
- `light_pest_control/wiki/INDEX.md` has an empty bullet and the folder's old name.
- Two different `last_run.json` files exist (repo root = review record;
  `research_reports/` = research-agent record). Different schemas, same name.
