# Daily review — Farming_Automation (2026-10-09)

**Verdict: PARK.** Changed from the 2026-09-23 review's REVIVE, deliberately.

## What I looked at

All ten wiki pages end to end (not skimmed — the numbers in them are the whole point),
`main_question.md`, both `last_run.json` files, the research agent's final report and the
run log for 2026-06-10, the `light_pest_control` scaffold, and the full git history. No
browser check: there is no frontend, and no code at all.

## The thing worth knowing

**The specification as written can over-water the bed by 2.2x, and I can show the
arithmetic from the repo's own numbers.**

The 110-minute runtime is not a free-standing value. It was derived by assuming exactly
three irrigation events per week — `first-runtime-rule-...:26` says "about 3 irrigation
events per week, spaced roughly every 2 to 3 days" — and dividing Penn State's weekly
figure by three. The 1-inch-per-week target only holds at that frequency.

But nothing enforces it, and the recheck rule contradicts it outright:
`first-recheck-rule-...:27-29` permits another full 110-minute run **the next day** if the
6-inch sensor has dried back to 25–30 cb. On a 30-inch bed in hot weather that is
plausible daily. Using the runtime page's own figure of 348 minutes of drip time per inch,
each event is 0.316 in, so:

- 3 events/week → 0.95 in (on target)
- 7 events/week → **2.21 in** (2.2x target)

Two pages disagree about whether back-to-back daily runs are legal, and no page anywhere
caps weekly volume. This is also the reason the control function keeps not getting
written: it needs a `TOO_SOON` branch, and **no page defines what interval is too soon.**
Writing the code first would mean inventing that constant in Python and letting the
research inherit it backwards. That is task 1, and it is a one-hour wiki page.

## Why PARK and not REVIVE again

The last review ranked "write `irrigation_rule.py`" first. Sixteen days on it is
untouched — while both 15-minute markdown chores from the same list were done within
hours of the review, in `4c6af52` and `1f2ba6a`. That is a revealed preference worth
reading honestly: the blocker was never a missing function.

What this research specifies is physical. A 30-inch raised bed, Toro tape at 10 mil, a
tension sensor buried at 6 inches. There is no software-only version of this that is more
than a calculator for numbers already written down in markdown. The research agent
stopped on 2026-06-16 having chosen every value — it finished, it didn't stall.

Not RETIRE, though, and I want to be clear about that: ten pages sourced to Penn State,
Utah State, Oregon State, Missouri and UF IFAS, converging on an actionable shopping list
and control rules, is a real artifact. It cost nothing to keep and it doesn't rot —
extension-service agronomy will say the same thing next season. The restart condition is
one sentence: **you own a bed and a tension sensor.** I put that at the top of
`REFERENCE.md` so it is the first thing a future reader sees.

## What I'm proposing

Leave-it-correct work, not a build-out. Task 1 is the frequency fix above — cheap now,
expensive to rediscover from dead tomatoes. The quick win is the two wrong lines in
`light_pest_control/wiki/INDEX.md` (pre-rename folder name, empty bullet), flagged last
review and still there. Then the `PROTOTYPE_SPEC.md` one-pager, which matters *more* under
PARK since re-entry cost is what decides whether a parked repo ever gets picked up. Then
deciding `light_pest_control`'s fate — it's a second unstarted front, 83% of the repo by
bytes, and arguably the more interesting question with a far cheaper bench prototype.

The control function stays on the list as item 5, demoted and explicitly blocked on task
1, reframed as a season-replay harness that reports weekly applied inches — which would
have caught the 2.2x defect mechanically instead of by hand.

Also worth noting: the previous review's three doc defects are genuinely fixed. All ten
index links resolve, the runtime page exists with its derivation rebuilt, and the 12-mil
wall-thickness contradiction is gone. `REFERENCE.md` was still listing all three as open;
I rewrote it.
