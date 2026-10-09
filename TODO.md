# TODO — Farming_Automation

Verdict from the 2026-10-09 review: **PARK.** Not a retirement — the research here is
real and finished. But it specifies a *physical* prototype (a raised bed, drip tape, a
soil-tension sensor in the ground) and none of that hardware exists. Until it does,
there is no automation to write, only a 40-line `if/else` with hand-typed inputs.

The honest evidence for parking: the 2026-09-23 review ranked "write the first code" as
task 1. Sixteen days later it is untouched, while both 15-minute markdown chores from
that same list were done within hours. The blocker was never a missing function.

**What would have to be true to restart:** you own a tomato bed and a soil-moisture
tension sensor (or a Tensiometer/Watermark + reader) and have planted a row. That is
the only gate. The research does not rot in the meantime — extension-service agronomy
from Penn State and Utah State will say the same thing next season.

So the tasks below are *leave-it-correct* work, not a build-out. Item 1 is the one that
actually matters: the spec as written contains a real defect that would over-water the
bed, and it is much cheaper to fix now than to rediscover from dead tomatoes.

---

## 1. [DESIGN] The spec can over-water the bed by 2.2x — nothing caps irrigation frequency

This is the only substantive defect left in the research, and it is load-bearing.

The 110-minute runtime was derived **assuming exactly 3 events per week**:
`wiki/pages/first-runtime-rule-for-outdoor-tomato-drip-irrigation.md:26` says "split the
weekly total across about 3 irrigation events per week, spaced roughly every 2 to 3
days." The weekly 1-inch target only holds at that frequency.

But no rule enforces it, and the recheck rule actively contradicts it.
`wiki/pages/first-recheck-rule-after-a-tomato-drip-irrigation-event.md:27-29` permits
another full run **the very next day** if the 6-inch sensor has dried back to 25–30 cb.
In hot weather on a 30-inch bed that is plausible daily.

The arithmetic, using the page's own Penn State figure (348 min of drip time = 1 inch):

| Events/week | Water applied | vs. 1 in/week target |
|---|---|---|
| 3 (as derived) | 0.95 in | on target |
| 5 | 1.58 in | 1.6x |
| 7 (what the rules allow) | **2.21 in** | **2.2x** |

Each 110-minute event is 0.316 inch. Nothing in any of the ten pages bounds the total.

The fix is one new wiki page in the house format, deciding **one** of:
- a minimum interval between events (e.g. 48 h), which caps the week at ~3.5 events, or
- a rolling 7-day applied-water cap (~1 inch), which self-regulates regardless of trigger
  frequency, or
- a shorter runtime sized for the true observed trigger rate

Then reconcile `first-recheck-rule-...:27-29` so the two pages stop disagreeing about
whether back-to-back daily runs are legal.

**Why it matters:** this is also why task 5 is blocked. The `decide()` function everyone
keeps proposing needs a `TOO_SOON` branch, and **no page in the repo defines what
interval is too soon.** Writing the code first would mean inventing that constant in
Python and letting the research inherit it backwards.

---

## 2. `[DONE 2026-10-09]` Fix the two wrong lines in `light_pest_control/wiki/INDEX.md`

The only remaining factual wrongness in the repo, and it is two lines:

- `light_pest_control/wiki/INDEX.md:3` still says the wiki is for
  `light_effects_on_insects` — the folder was renamed to `light_pest_control` on
  2026-09-21 and the index never caught up.
- `light_pest_control/wiki/INDEX.md:7` is a bare `-` bullet: an empty list item under a
  `## Pages` heading, which renders as a stray dash.

Either correct the name and delete the empty bullet, or — better, and consistent with
task 4 — replace the whole file with one line stating this question has no pages yet.

**Why it matters:** flagged in the 2026-09-23 review, never fixed. It is 15 minutes and
it stops the folder from looking half-abandoned to the next reader.

---

## 3. [DOCS] Write `PROTOTYPE_SPEC.md` — the one page that makes a future pickup cheap

Carried from the last review and still the right call, *more* so under PARK: if this sits
for a season, the thing that decides whether it gets picked up is whether you can
re-enter it in five minutes instead of re-reading 640 lines across ten files.

Every number is settled; it is just smeared out. Pull onto one page:

bed 30 in raised, one trellised tomato row, plants 18–24 in apart, beds on 4-ft centers
(`canonical-bed-layout-...:27-34`); 5/8 in drip tape, 12 in emitter spacing, ~0.45
gpm/100 ft, 10 mil wall, laid ~2 in off the plant line (`first-drip-tape-specification-...:27-31`);
one tension sensor at 6 in (`first-sensor-depth-...:29`); irrigate at 25–30 cb for 110 min
(`first-threshold-...:30`, `first-runtime-rule-...:27`); skip if ≥0.25 in rain forecast
within 24 h (`first-threshold-...:31`); recheck next day at a fixed time
(`first-recheck-rule-...:27`); log daily reading, each runtime event, rainfall, rain-delay
flag (`first-logging-boundary-...:26-30`).

Split it into **"what to buy"** and **"the control rules"** — the buy list is the actual
gate on this project, so make it a shopping list you could act on in one trip. Fold in
whatever task 1 decides about frequency.

Keep the ten pages as the sourced derivations; this is an index, not a replacement.

---

## 4. [DESIGN] Resolve `light_pest_control/` — it is a second open front on a parked repo

Also carried, also never done. It is 59 lines of genuinely good sub-questions, a 996 KB
source PDF (Hori et al. on lethal blue-light wavelengths), and a wiki with **zero pages**.
That PDF is 83% of the repo's 1.2 MB.

Blue-light insect mortality has no overlap with tomato drip scheduling beyond the word
"farming" — different physics, different hardware, different literature. Keeping it here
means the repo has two unstarted fronts instead of one parked one, which is how both end
up looking dead.

Pick one and write it down in `REFERENCE.md`:
- split it into its own `04_early_stage_and_ideas` repo, where it can be triaged on its
  own merits (it is arguably the more interesting question, and unlike irrigation it has
  a cheap bench prototype — an LED, a jar, and some flour beetles), or
- delete the empty wiki scaffold and keep only the PDF plus `main_question.md` as a
  reading note

Do not leave it as-is.

---

## 5. [IMPROVEMENT] Only if you want to validate without hardware: `decide()` plus a replay harness

**Blocked on task 1 — do not start before it.** This was task 1 on the last two lists and
went untouched both times; it is demoted deliberately, not forgotten.

The case for doing it anyway, without owning a sensor: a pure function plus a replay
harness would *prove* the rules are self-consistent before you spend money on tape and a
tensiometer. Feed it a synthetic season (a daily tension curve plus rainfall) and have it
report total applied inches per week. That would have caught the task-1 defect
mechanically instead of by hand.

```
decide(tension_cb, forecast_rain_in_24h, hours_since_last_irrigation) -> Decision
```
returning one of `IRRIGATE_110_MIN`, `RAIN_DELAY`, `HOLD_WET`, `TOO_SOON`.

Constants are all decided — cite the page in a comment, do not re-derive. The branch
order is already prose at `wiki/pages/minimum-inputs-irrigation-prototype.md:35-37`;
transcribe it. `TOO_SOON` uses whatever interval task 1 settles.

"Working" means: `python irrigation_rule.py --replay season.csv` prints weekly applied
inches and flags any week over the cap. A CLI that just prints one decision for one
hand-typed reading is not worth the file — that is a calculator, and the repo already
has the numbers written down.
