# Canonical Bed Layout For A Beginner Outdoor Tomato Irrigation Prototype

## Sub-question

What single physical tomato bed layout should the course assume first so the existing beginner drip-irrigation rules refer to one clear setup?

## Short Answer

For the current beginner prototype, assume one trellised tomato row on one 30-inch raised bed, with plants spaced 18 to 24 inches apart, one 5/8-inch drip tape line running down the row, and the tape placed near the row center but about 2 inches off the plant line. Treat the bed layout as a simple raised-bed garden or small farm bed, not a sprawling unstaked field layout.

## Confirmed Facts From Local Course Material

- The main course question asks how a farm automation system can make practical irrigation decisions with minimal human effort.
- The local wiki already narrowed the first automation target to irrigation timing for an outdoor tomato drip prototype.
- The local wiki already chose a 25 to 30 centibar trigger, a 6-inch starter sensor depth, a roughly 110-minute runtime rule, a next-day recheck rule, a 5/8-inch drip tape direction, and a 10 mil wall-thickness choice.
- The current runtime page already assumes a 30-inch tomato bed when translating drip flow into weekly irrigation hours.

## Focused External Evidence

- Oregon State University Extension says raised beds often improve drainage, warm more quickly in spring, and reduce some soil-borne disease problems in vegetable gardens.
- Utah State University Extension says tomatoes should be spaced 18 to 24 inches apart in the row and rows should be 36 to 48 inches apart, with more room for indeterminate types.
- Missouri Extension says tomatoes need a single drip line per row, offset about 2 inches from the plant, with emitter spacing typically in the 4- to 12-inch range.
- University of Florida IFAS explains drip calculations using 30-inch-wide beds on 4-foot centers and notes that a single drip tape in the middle of the bed can wet the whole bed width in heavier soil.

## First Prototype Layout

- Bed type: raised bed
- Bed width: about 30 inches
- Row pattern: one tomato row per bed
- Plant spacing in row: 18 to 24 inches
- Bed spacing reference: about 4-foot centers if multiple beds are used
- Irrigation line: one 5/8-inch drip tape line per bed
- Tape placement: near the bed center and about 2 inches off the plant line
- Plant support assumption: trellised, staked, or caged plants rather than unsupported sprawling plants

## Why This Is A Reasonable First Layout

- It matches the existing local runtime page instead of forcing the course to abandon the 30-inch-bed assumption already built into earlier irrigation math.
- It keeps the hardware simple: one bed, one row, one tape line, one shallow sensor, and one repeatable watering rule.
- A raised bed is a better beginner default than a flat unmanaged row because the external guidance supports raised beds for drainage and early soil warming.
- Trellised or supported plants fit the course's irrigation focus better than sprawling plants because spacing and tape placement stay easier to define.

## Assumptions And Inferences

- This page treats a raised 30-inch bed as the canonical first layout because earlier local pages already depend on a 30-inch bed assumption; the sources support the pieces of this layout more directly than they prescribe this exact combined prototype.
- The 4-foot-center reference is included so a multi-bed version stays compatible with common drip-layout calculations, but the first prototype can still be tested with only one bed.
- The tape is described as near center and about 2 inches off the plant line because the course is combining a centered-bed drip assumption with tomato-row placement guidance.
- This page does not claim that the same layout is best for every tomato variety, soil texture, mulch system, or production scale.

## What Still Needs To Be Chosen

- Whether the first software version should store only daily sensor readings or also keep each irrigation runtime and rainfall adjustment
- Whether a second deeper sensor should remain a later upgrade or become part of version one
- Whether the prototype should assume bare ground, water-permeable mulch, or plastic mulch on the raised bed
- Whether the rain-delay rule should stay at the current 0.25-inch forecast cutoff once a mulch choice is fixed

## Evidence Used

- [main_question.md](../../main_question.md)
- [First Runtime Rule For An Outdoor Tomato Drip-Irrigation Prototype](./first-runtime-rule-for-outdoor-tomato-drip-irrigation.md)
- [First Drip Tape Specification For An Outdoor Tomato Irrigation Prototype](./first-drip-tape-specification-for-outdoor-tomato-irrigation-prototype.md)
- [First Wall Thickness For An Outdoor Tomato Drip Tape Prototype](./first-wall-thickness-for-outdoor-tomato-drip-tape-prototype.md)
- Oregon State University Extension, "Vegetable Gardening in Oregon": https://extension.oregonstate.edu/catalog/pub/ec-871-vegetable-gardening-oregon
- Utah State University Extension, "Planting and Spacing": https://extension.usu.edu/vegetableguide/tomato-pepper-eggplant/planting-spacing
- Missouri Extension, "Watering and Fertilizing Tomatoes in a High Tunnel": https://extension.missouri.edu/publications/g6462
- University of Florida IFAS, "Drip-Irrigation Systems for Small Conventional Vegetable Farms and Organic Vegetable Farms": https://ask.ifas.ufl.edu/publication/HS388
