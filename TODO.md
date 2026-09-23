# TODO — Farming_Automation

Verdict from the 2026-09-23 review: **REVIVE.** The research phase actually finished
its job. Nine wiki pages narrowed a vague "AI plant intelligence" question down to a
fully-specified physical prototype with real numbers. Nothing is left to research
before the first build — only to type. Ranked so the top item is the one that turns
this repo from notes into software.

---

## 1. [IMPROVEMENT] Write `irrigation_rule.py` — the first thing here that runs

Every constant this needs has already been decided. Stop researching and encode it.

A pure function plus a `__main__` CLI, no hardware, no network:

```
decide(tension_cb, forecast_rain_in_24h, hours_since_last_irrigation) -> Decision
```

Returns exactly one of `IRRIGATE_110_MIN`, `RAIN_DELAY`, `HOLD_WET`, `TOO_SOON`.

Constants and their sources — do not re-derive these, just cite the page in a comment:

| Value | Source |
|---|---|
| Trigger at 25–30 centibars | `wiki/pages/first-threshold-for-outdoor-tomato-irrigation.md:30` |
| Delay if ≥0.25 in rain forecast in 24 h | same file, `:31` |
| Sensor at 6 in depth | `wiki/pages/first-sensor-depth-for-outdoor-tomato-irrigation.md` |
| Runtime 110 min | `wiki/pages/first-recheck-rule-after-a-tomato-drip-irrigation-event.md:9` |
| Recheck next day, same clock time | same file, `:27` |

The branch order is already written out in prose at
`wiki/pages/minimum-inputs-irrigation-prototype.md:35-37` — transcribe it.

"Working" means: `python irrigation_rule.py --tension 28 --rain 0.0 --last-run
2026-09-21` prints a decision and appends one row to `irrigation_log.csv`. That is
the whole bar. It makes the repo name true for the first time.

**Why it matters:** the repo is 2.3 MB of markdown with zero executable files. Until
one exists this is a note, not a project.

---

## 2. [BUG] Reconstruct the missing runtime-rule page — the 110-minute figure has no source

`wiki/pages/first-runtime-rule-for-outdoor-tomato-drip-irrigation.md` does not exist
and **was never committed** — it is absent from the repo's full history of added
files. Yet six files cite it as evidence:

- `wiki/INDEX.md:14`
- `wiki/pages/first-logging-boundary-...:57`
- `wiki/pages/first-drip-tape-specification-...:57`
- `wiki/pages/first-wall-thickness-...:54`
- `wiki/pages/canonical-bed-layout-...:60`
- `wiki/pages/first-recheck-rule-...:56`

There is also no run log between `research_reports/run_logs/2026-06-09.md` and
`2026-06-11.md`, so that day's page *and* its log were both lost. The 110-minute
runtime is the single most load-bearing number in the prototype and currently rests
on nothing.

It is reconstructible without new research: `first-drip-tape-specification-...:20`
preserves the Penn State figure of ~5.8 hours to apply 1 inch on a 30-inch bed at
0.45 gpm/100 ft. Rebuild the arithmetic from there, confirm it lands near 110 min per
event, and write the page in the house format. If it does not land near 110, that is
a more important finding — every downstream page inherits the error.

Do this before or alongside task 1 so the code is not encoding an unsourced constant.

---

## 3. [QUICK WIN ~15min] Fix the broken index link and the superseded 12 mil note

Two small, verified defects:

- `wiki/INDEX.md:14` links to the missing runtime page. Either stub the file or mark
  the entry as missing, so the index stops lying about what is in `wiki/pages/`.
- `wiki/pages/first-drip-tape-specification-...:44` still says wall thickness "is not
  yet fixed by the course" and floats 12 mil as a placeholder. A later run fixed it at
  **10 mil** (`wiki/pages/first-wall-thickness-...:26`). Update the stale line so the
  two pages do not disagree on a part you would actually buy.

**Why it matters:** cheapest possible removal of real wrongness, and it stops the next
reader from ordering the wrong tape.

---

## 4. [DESIGN] Decide what `light_pest_control/` is doing in this repo

Added 2026-09-21, and it is an empty shell: `main_question.md` (59 lines of good
questions), a research PDF, and a wiki with **zero pages** —
`light_pest_control/wiki/INDEX.md:7` is a bare `-` bullet, and line 3 still calls the
folder `light_effects_on_insects`, which is not its name.

It is also a completely different problem: killing insects with blue-light LEDs has
no overlap with tomato drip scheduling beyond the word "farming". Bolting a second
untouched main question onto the one repo that is finally ready to ship is how the
irrigation prototype ends up never getting built.

Pick one, in a paragraph in `REFERENCE.md`: split it into its own early-stage repo, or
delete the scaffold and keep only the PDF. Do not leave it as a second open front.

---

## 5. [DOCS] Collapse the nine wiki pages into one `PROTOTYPE_SPEC.md` build sheet

The full specification is real but smeared across ~600 lines in nine files, each
repeating "what the local wiki already chose" in prose. Pull every settled number onto
one page you could hand to a hardware store and to task 1:

bed 30 in raised, one trellised tomato row, plants 18–24 in apart, beds on 4-ft
centers; 5/8 in drip tape, 12 in emitter spacing, ~0.45 gpm/100 ft, 10 mil wall, laid
~2 in off the plant line; tension sensor at 6 in; irrigate at 25–30 cb for 110 min;
skip if ≥0.25 in rain forecast within 24 h; recheck next day at a fixed time; log
daily reading, each runtime event, rainfall, and rain-delay flag
(`wiki/pages/first-logging-boundary-...:26-30`).

Keep the nine pages as the sourced derivations — this is the index, not a replacement.

**Why it matters:** right now you cannot act on this research without reading all of
it. One page makes the next build session start in minutes instead of an hour.
