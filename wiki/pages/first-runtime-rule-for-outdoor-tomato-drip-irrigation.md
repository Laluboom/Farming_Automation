# First Runtime Rule For An Outdoor Tomato Drip-Irrigation Prototype

## Sub-question

Once the 25 to 30 centibar trigger is reached, how long should a single drip-irrigation event run for a beginner outdoor tomato prototype?

## Short Answer

For the current beginner prototype, run each triggered irrigation event for about 110 minutes. This comes from treating 1 inch of water per week as the tomato bed's target, using Penn State Extension's figure of about 5.8 hours of drip time to apply that 1 inch on a 30-inch bed at 0.45 gpm per 100 ft, and splitting that weekly total across about three irrigation events instead of one long weekly run or daily light watering.

## Confirmed Facts From Local Course Material

- The main course question asks how a farm automation system can make practical irrigation decisions with minimal human effort.
- The local wiki already narrowed the first automation target to irrigation timing for an outdoor tomato drip prototype in loam or silt loam soil.
- The local wiki already chose a first trigger of about 25 to 30 centibars and a 6-inch starter sensor depth.

## Focused External Evidence

- Penn State Extension says that for a 30-inch bed with drip tape flowing at about 0.45 gpm per 100 ft, it takes about 5.8 hours to apply 1 inch of water.
- Utah State University Extension's general vegetable irrigation guidance favors a small number of deeper waterings per week over daily light watering, which fits scheduling drip time in a handful of events rather than one continuous run.

## First Prototype Rule

- Weekly water target: about 1 inch of applied water per week for the tomato bed.
- Application-rate assumption: 0.45 gpm per 100 ft on a 30-inch bed, which Penn State's figure translates to about 5.8 hours (about 348 minutes) of total drip time per week to apply that 1 inch.
- Event-frequency assumption: split the weekly total across about 3 irrigation events per week, spaced roughly every 2 to 3 days, rather than one long weekly run or daily light watering.
- Resulting runtime: 348 minutes divided by 3 events is about 116 minutes per event, rounded down to a simpler starter timer value of about 110 minutes per irrigation event.

## Why This Is A Reasonable First Rule

- It ties the runtime directly to a documented extension figure instead of picking an arbitrary duration.
- It keeps the prototype's total weekly water close to the commonly cited 1-inch-per-week vegetable guideline while still running the system in a trigger-based, non-continuous way.
- A small, round number of minutes is easier for a beginner irrigation controller or timer to encode than a raw fractional figure.
- It stays compatible with the already-chosen 25 to 30 centibar trigger and 6-inch sensor depth, and leaves the recheck timing after the event as a separate, later decision.

## Assumptions And Inferences

- The 110-minute figure is a rounded-down version of the raw calculation (348 minutes divided by 3 events, which is about 116 minutes); treat 110 as an approximate starter value, not an exact derivation.
- Splitting the weekly 1-inch target across about 3 events per week is a beginner-friendly inference from general watering-frequency guidance; Penn State's 5.8-hour figure only fixes the weekly total, not how many events it should be split into.
- The 0.45 gpm per 100 ft flow rate and 30-inch bed width are treated here as a working example drawn from Penn State's own illustration, not yet a confirmed hardware choice.
- This page does not claim that every tomato stage, soil condition, or weather pattern should use exactly this runtime; it only fixes one first, testable value.

## What Still Needs To Be Chosen

- One rule for when to recheck the sensor after this irrigation event
- One exact drip tape specification instead of the assumed example flow rate
- One canonical tomato bed layout such as raised bed or flat field row
- Whether the first build should log only daily sensor readings or also each irrigation runtime and rainfall adjustment

## Evidence Used

- [main_question.md](../../main_question.md)
- [First Threshold For An Outdoor Tomato Irrigation Prototype](./first-threshold-for-outdoor-tomato-irrigation.md)
- [First Sensor Depth For An Outdoor Tomato Irrigation Prototype](./first-sensor-depth-for-outdoor-tomato-irrigation.md)
- Penn State Extension, "Determining How Long to Run Drip Irrigation Systems for Vegetables": https://extension.psu.edu/determining-how-long-to-run-drip-irrigation-systems-for-vegetables/
- Utah State University Extension, general vegetable irrigation guide: https://extension.usu.edu/vegetableguide/management/irrigation.php
