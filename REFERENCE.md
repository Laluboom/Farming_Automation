# Farming_Automation — Reference

## Status: PARKED (2026-10-09)

A **finished piece of research, not an automation.** 33 tracked files: 30 markdown, 2
JSON, one PDF, and **zero executable files** of any kind. 1.2 MB, 996 KB of it one PDF.

Parked rather than retired because the research completed its job; parked rather than
revived because what it specifies is *physical*. Reasoning in `TODO.md`.

**Restart condition:** you own a tomato bed and a soil-water-tension sensor, and have
planted a row. That is the only gate. Nothing else here needs more thought first.

## What happened

An automated daily research agent ran 2026-06-04 → 2026-06-16 and converged a vague
question into a completely specified beginner irrigation prototype, one decision per day.
It stopped with every number chosen. No new research since.

`main_question.md` holds two original questions. **AI plant intelligence** (diagnose a
plant from images + species + soil + climate) was explored only at the dataset level and
is a dead branch — no wiki page pursues it. **Farm automation** is what all ten pages
build. `light_pest_control/`, added 2026-09-21, is an unrelated third question (lethal
blue-light insect control): a good 59-line question list, one PDF, **zero wiki pages**.
See `TODO.md` item 4.

## The prototype the research settled on

One outdoor tomato bed, drip-irrigated, one yes/no watering decision per day:

- 30 in raised bed, one trellised row, plants 18–24 in apart, beds on 4 ft centers
- 5/8 in drip tape, 12 in emitter spacing, ~0.45 gpm/100 ft, 10 mil wall, ~2 in off the
  plant line
- One soil-water-tension sensor at 6 in depth, read once daily at a fixed time
- Irrigate at 25–30 cb; run 110 minutes
- Skip and recheck if ≥0.25 in rain forecast within 24 h
- Recheck next day, never off the immediate post-run reading
- Log: daily reading, each runtime event, rainfall, rain-delay flag

Soil context is loam / silt loam, bare ground or permeable mulch. Sources are US
extension services (Penn State, Oregon State, Utah State, Missouri, UF IFAS) plus Toro
drip-tape literature; every page separates confirmed facts from inference.

## Layout

| Path | Contents |
|---|---|
| `wiki/pages/` | 10 sourced decision pages — the real substance |
| `wiki/INDEX.md` | Page index; all 10 links resolve |
| `research_reports/` | Last run (2026-06-16) and dated logs from 2026-06-04 |
| `light_pest_control/` | Separate question, empty wiki, 996 KB PDF |
| `TODO.md` | Ranked next steps |

## How to run it

You can't, and under PARK that is the expected state. `TODO.md` item 5 describes the only
software worth writing before hardware exists, and it is blocked on item 1.

## Known defects

- **The spec can over-water 2.2x.** The 110-min runtime assumes 3 events/week
  (`first-runtime-rule-...:26`), but `first-recheck-rule-...:27-29` permits a run every
  24 h — up to 2.21 in/week against a 1 in/week target. No page caps frequency, and none
  defines a minimum inter-event interval, so control code would have to invent that
  constant. `TODO.md` item 1.
- `light_pest_control/wiki/INDEX.md:3` still calls the folder `light_effects_on_insects`,
  its pre-rename name; `:7` is an empty `-` bullet.
- Two different `last_run.json` files exist (repo root = review record;
  `research_reports/` = research-agent record). Different schemas, same name.
