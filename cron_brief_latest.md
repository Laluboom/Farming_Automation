# Review Brief — Farming_Automation — 2026-09-23

**Verdict: REVIVE.** Not a close call, and not the usual early-stage verdict.

## What I looked at

All 26 markdown files: both main questions, all nine wiki decision pages in full, the
conventions files, `latest_report.md`, the research agent's own `last_run.json`, eight
dated run logs, and the `light_pest_control/` folder. No browser check — there is no
frontend, and no code at all.

## What's actually here

Zero executable files. 26 `.md`, one PDF, one JSON, 2.3 MB. By the tier's own test — a
repo called `Farming_Automation` containing only markdown is a note, not an automation
— this should be a RETIRE or a PARK.

It isn't, and the reason is worth being precise about. An automated research agent ran
daily from 2026-06-04 to 2026-06-16 and did the thing these stub repos almost never
do: it converged. Each day it answered one narrow sub-question and fixed one more
variable. By day nine it had reduced "how can AI understand plants" down to a
completely specified physical object — a 30-inch raised bed with one trellised tomato
row, 5/8-inch drip tape at 12-inch emitter spacing and 10 mil wall, a tension sensor
at 6 inches, irrigate at 25–30 centibars for 110 minutes, skip if a quarter inch of
rain is forecast inside 24 hours, recheck the next day. Every number is sourced to a
US extension service, and every page carefully separates confirmed facts from
inference.

That is a buildable spec. There is no research left to do before version one, and the
research agent knew it: the final report's "exact next baby step"
(`research_reports/latest_report.md:9`) is to define the log schema — a coding task,
not a research task. The project stalled precisely at the point where it had to stop
writing markdown and start writing code, and then nothing happened for three months.

## What I found wrong

One real defect, and it is worse than a broken link.
`wiki/pages/first-runtime-rule-for-outdoor-tomato-drip-irrigation.md` does not exist —
and it never did. It is absent from the repo's entire history of added files. But
`wiki/INDEX.md:14` links to it and five separate wiki pages cite it as evidence. The
110-minute runtime, which is the single most load-bearing number in the whole
prototype, came from that page and now has no surviving derivation. The run logs
confirm the shape of the loss: they jump from `2026-06-09.md` straight to
`2026-06-11.md`, so that day's page *and* its log both failed to get committed, while
every later day happily cited the ghost. It is recoverable — the Penn State figure it
was built on survives as a quotation at
`first-drip-tape-specification-...:20` — but until someone redoes that arithmetic, the
central constant is folklore.

Smaller: `first-drip-tape-specification-...:44` still says wall thickness is unfixed
and suggests 12 mil, though a later page settled on 10 mil. `light_pest_control/` was
bolted on 2026-09-21 with an empty wiki — a bare `-` bullet and the folder's old name
— which is a second, unrelated front opening on the one repo that was finally ready to
ship. And the old `REFERENCE.md` was a chat cold-start summary about plant-disease
image datasets: a topic no wiki page ever pursued. I rewrote it to describe the repo
as it actually is.

## What I'm proposing

The top task is the only one that matters: write `irrigation_rule.py`, a pure decision
function plus a CLI, using constants that are already chosen and cited. Working means
`python irrigation_rule.py --tension 28 --rain 0.0 --last-run 2026-09-21` prints a
decision and appends a row to a CSV. One session. No hardware, no network, no model.

Second is rebuilding the lost runtime page, so task one isn't hard-coding an unsourced
number. The quick win is the broken index link plus the stale 12 mil note. Then a
decision on whether `light_pest_control` splits out, and a consolidation of nine pages
into one build sheet.

If the next session produces no `.py` file, that is the signal to re-run this review as
a PARK or RETIRE. The research is done; only the typing is missing, and three months
of not typing is itself information.
