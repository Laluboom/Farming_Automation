# Minimum Inputs For A Beginner Irrigation Prototype

## Sub-question

What is the smallest input set and yes-or-no decision rule for a beginner irrigation prototype?

## Short Answer

A practical beginner prototype can start with one root-zone soil moisture reading, one record of recent water added by rain or irrigation, and one short rain forecast. The simplest rule is: water only when soil moisture has dropped below a chosen threshold and meaningful rain is not expected soon.

## Confirmed Facts From Local Course Material

- The course main question asks what sensors or inputs are needed for farm automation, including soil moisture, rainfall, temperature, humidity, and sunlight.
- The main question also asks what the simplest prototype would look like without expensive hardware.
- The existing local wiki page already narrows the first automation target to irrigation timing rather than disease diagnosis or fertilizer scheduling.

## Focused External Evidence

- USDA ARS explains that soil moisture sensors placed in the rooting zone track changes caused by crop growth, irrigation, and rainfall, and that irrigation is needed when soil moisture drops below a certain level.
- The same USDA ARS fact sheet describes a simple "checkbook" method where water in the soil is tracked as starting soil water plus rainfall or irrigation minus crop water use estimated from weather.
- FAO describes irrigation scheduling as answering two questions: when to irrigate and how much water to apply. It notes that low-frequency irrigation is usually triggered when available soil moisture in the root zone is nearly depleted.
- FAO also shows a simple estimate that subtracts rainfall since the previous irrigation from irrigation requirement, which supports keeping recent rain as a direct input.
- A NOAA-reviewed irrigation scheduling paper says predictive weather can support decisions to defer water application when rainfall is forecast.

## Minimum Useful Inputs

- One soil moisture measurement near the crop root zone.
- One simple record of recent water additions: rain, irrigation, or both.
- One short rain forecast for the next decision window.

## Beginner Decision Rule

Use this as a first yes-or-no rule:

- If root-zone soil moisture is above the chosen threshold, do not irrigate.
- If root-zone soil moisture is below the chosen threshold and meaningful rain is expected soon, wait and recheck after the rain window.
- If root-zone soil moisture is below the chosen threshold and meaningful rain is not expected soon, irrigate.

## Why This Is A Reasonable First Boundary

- It keeps the system focused on one decision instead of mixing irrigation with nutrition or disease logic.
- It uses inputs that match the external irrigation scheduling basics: soil moisture, water added by rain or irrigation, and weather.
- It avoids pretending that one fixed threshold works for every crop, soil, and growth stage.

## Assumptions And Inferences

- This page infers a beginner-friendly three-input rule from the external sources; the sources describe scheduling principles more directly than they prescribe this exact minimal prototype.
- The rule is intentionally a yes-or-no trigger, not a full irrigation amount calculator.
- The phrase "meaningful rain" still needs a crop- and soil-specific definition before implementation.

## What Still Needs To Be Chosen

- One crop.
- One growing area.
- One soil moisture threshold or sensor target for that crop and soil.
- One definition of how much forecast rain is enough to delay watering.

## Evidence Used

- [main_question.md](../../main_question.md)
- [Simplest First Automation Decision](./simplest-first-automation-decision.md)
- USDA ARS, "Irrigation Scheduling for Humid Environments": https://www.ars.usda.gov/ARSUserFiles/60663500/FactSheets/Irrigation%20Scheduling%20for%20Humid%20Environments_9-22-11.pdf
- FAO, "Simple estimation of crop water requirements": https://www.fao.org/4/W3094E/w3094e06.htm
- NOAA repository paper on predictive weather in irrigation scheduling: https://repository.library.noaa.gov/view/noaa/57235/noaa_57235_DS1.pdf
