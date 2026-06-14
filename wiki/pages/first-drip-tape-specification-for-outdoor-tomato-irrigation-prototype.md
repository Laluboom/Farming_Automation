# First Drip Tape Specification For An Outdoor Tomato Irrigation Prototype

## Sub-question

What exact drip tape specification should a beginner use first for the current outdoor tomato irrigation prototype?

## Short Answer

For the current beginner prototype, use one concrete starter tape specification: a 5/8-inch drip tape with 12-inch emitter spacing and about 0.45 gpm per 100 ft flow rate. A practical example is Toro Aqua-Traxx tape in a 12-inch spacing option with a listed 0.45 to 0.50 gpm per 100 ft range, because that matches the local runtime page's existing Penn State watering example closely enough to turn the prototype from an assumed flow rate into one real hardware direction.

## Confirmed Facts From Local Course Material

- The main course question asks how a farm automation system can make practical irrigation decisions with minimal human effort.
- The local wiki already narrowed the first automation target to irrigation timing for an outdoor tomato drip prototype.
- The local wiki already chose a first trigger of about 25 to 30 centibars, a 6-inch starter sensor depth, a 110-minute first runtime rule, and a next-day recheck rule.
- The current runtime page assumes drip tape near 0.45 gpm per 100 ft on a 30-inch bed and treats that as about 5.8 total drip hours per week to apply 1 inch of water.

## Focused External Evidence

- Penn State Extension says that for a 30-inch bed with drip tape flowing at about 0.45 gpm per 100 ft, it takes about 5.8 hours to apply 1 inch of water.
- Toro's Aqua-Traxx drip tape literature shows a 12-inch spacing option with about 0.45 gpm per 100 ft at 8 psi for a 0.27 gph emitter configuration, which is a close match to the local runtime assumption.
- The same Toro literature says Aqua-Traxx is available in 5/8-inch diameter and in multiple wall thicknesses including 12 mil, giving a concrete product family that fits a small vegetable-bed prototype.
- Toro's design manual says Aqua-Traxx PC uses emitter spacing options from 6 inches to 24 inches and lists a minimum filtration requirement of 200 mesh for that pressure-compensating line; the Aqua-Traxx product sheet lists 140-mesh filtration for many standard tape options.

## First Prototype Specification

- Tape family: Toro Aqua-Traxx or an equivalent drip tape with matching hydraulic specs
- Internal diameter: 5/8 inch
- Emitter spacing: 12 inches
- Flow rate target: about 0.45 gpm per 100 ft
- Working interpretation for the course: keep using the existing 110-minute runtime page as the first software rule, because this tape choice was selected to stay close to that same flow-rate assumption

## Why This Is A Reasonable First Choice

- It replaces the course's previously generic flow-rate assumption with one real tape pattern that is commercially documented.
- It stays close to the existing Penn State runtime example instead of forcing the course to redo its first watering rule immediately.
- Twelve-inch emitter spacing is simple for a beginner to reason about in a tomato bed because the outlets repeat at a regular, easy-to-measure interval.
- A 5/8-inch tape keeps the prototype in a common small-bed scale rather than pushing the first design toward a larger field layout.

## Assumptions And Inferences

- This page treats Toro Aqua-Traxx as an example of a real tape family whose published specs are close enough to the local 0.45 gpm per 100 ft runtime assumption; the course is not claiming that only this brand will work.
- The choice of 12-inch spacing is a beginner-friendly inference because it offers a concrete, common spacing while staying aligned with the current single-bed prototype scope.
- The wall-thickness choice is not yet fixed by the course. If the first build needs a single placeholder, 12 mil is a reasonable middle option within the manufacturer's available sizes, but that thickness is not established here as a confirmed requirement.
- This page does not yet prove that the chosen tape is the best option for every soil texture, mulch setup, row length, or tomato growth stage.

## What Still Needs To Be Chosen

- One exact wall thickness instead of leaving that part of the tape spec open
- One canonical tomato bed layout such as raised bed or flat field row
- Whether the first hardware build should store only daily sensor readings or also each irrigation runtime and rainfall adjustment
- Whether a second deeper sensor should remain a later upgrade or become part of version one

## Evidence Used

- [main_question.md](../../main_question.md)
- [First Runtime Rule For An Outdoor Tomato Drip-Irrigation Prototype](./first-runtime-rule-for-outdoor-tomato-drip-irrigation.md)
- [First Recheck Rule After A Tomato Drip-Irrigation Event](./first-recheck-rule-after-a-tomato-drip-irrigation-event.md)
- Penn State Extension, "Determining How Long to Run Drip Irrigation Systems for Vegetables": https://extension.psu.edu/determining-how-long-to-run-drip-irrigation-systems-for-vegetables/
- Toro, "Aqua-Traxx Superior Drip Tape" product sheet: https://cdn2.toro.com/en/-/media/Files/Toro/Agriculture/drip-tape-and-dripline/ALT046_1_Aqua-Traxx_Eng_WEB.ashx
- Toro, "Design, Installation & Maintenance Guide" for Aqua-Traxx: https://media.toro.com/Documents/Agriculture/ALT073-0008_AT_Design_Manual.pdf
