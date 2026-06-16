# First Logging Boundary For A Beginner Tomato Irrigation Prototype

## Sub-question

What should version one log for the beginner tomato irrigation prototype: only daily sensor readings, or also irrigation runtime and rainfall adjustment?

## Short Answer

Version one should log more than the daily sensor reading. A practical first logging boundary is: one daily root-zone sensor reading at the normal check time, each irrigation runtime event, and the rainfall amount or rain-based adjustment used in the watering decision. It does not need full evapotranspiration modeling, pressure data, or advanced flow analytics in version one.

## Confirmed Facts From Local Course Material

- The local prototype already depends on three core inputs: root-zone soil moisture, recent water added, and a short rain forecast.
- The local threshold page already turns forecast rain into a concrete delay rule for the tomato prototype.
- The local runtime page already uses a concrete irrigation runtime and says rainfall should be subtracted from the weekly target.
- The local recheck page already assumes one normal daily check after an irrigation event rather than a complex continuous control loop.

## Focused External Evidence

- Oregon State University Extension says soil moisture monitoring helps determine how much plant-available water remains, how quickly water is being depleted, when irrigation is needed, and whether irrigation is reaching the intended root depth.
- Oregon State's irrigation water management plan guide says irrigation planning should organize irrigation scheduling, monitoring, action planning, and recordkeeping together rather than treat them as separate concerns.
- Oregon State's irrigation measurement guide says measuring flow rate and application volume helps verify that the proper amount of water is delivered at each irrigation event.

## First Version Logging Boundary

- Log one daily soil-moisture reading from the 6-inch sensor at the normal decision time.
- Log each irrigation event with date and runtime minutes.
- Log rainfall that affected the decision, either as measured recent rainfall or the adjustment value used after rain.
- Log whether watering was delayed because of the rain rule when that rule is used.
- Do not require ET estimates, pressure measurements, or continuous high-frequency sensor streams in version one.

## Why This Is A Reasonable First Boundary

- It preserves every input already used by the local decision rule instead of logging only part of the logic.
- It keeps the prototype beginner-friendly because the records are still small and understandable.
- It creates enough history to explain why the system watered, waited, or skipped a run.
- It supports later debugging if the runtime rule or rain-delay rule needs to change.

## Assumptions And Inferences

- This page infers a minimum record set from the existing local decision logic plus extension guidance on monitoring and recordkeeping; the sources support the need for monitoring and application records more directly than they prescribe this exact starter schema.
- The page treats rainfall adjustment as important even if the first build stores it in a simple manual form rather than a fully automated weather integration.
- This page does not claim that version one needs precise flow-volume instrumentation if runtime and known drip specification are already available.

## What Still Needs To Be Chosen

- One exact field list and file format for the daily log
- Whether the rain entry should store measured rainfall, forecast rainfall, or both
- Whether irrigation runtime should be stored only in minutes or also translated into estimated applied water
- Whether the first interface should be a simple text log, spreadsheet-style table, or tiny local app screen

## Evidence Used

- [main_question.md](../../main_question.md)
- [Minimum Inputs For A Beginner Irrigation Prototype](./minimum-inputs-irrigation-prototype.md)
- [First Threshold For An Outdoor Tomato Irrigation Prototype](./first-threshold-for-outdoor-tomato-irrigation.md)
- [First Runtime Rule For An Outdoor Tomato Drip-Irrigation Prototype](./first-runtime-rule-for-outdoor-tomato-drip-irrigation.md)
- [First Recheck Rule After A Tomato Drip-Irrigation Event](./first-recheck-rule-after-a-tomato-drip-irrigation-event.md)
- Oregon State University Extension, "Soil moisture monitoring to support irrigation scheduling": https://extension.oregonstate.edu/catalog/pub/em-9868-soil-moisture-monitoring-support-irrigation-scheduling
- Oregon State University Extension, "Developing an irrigation water management plan": https://extension.oregonstate.edu/catalog/pub/em-9873-developing-irrigation-water-management-plan
- Oregon State University Extension, "Irrigation water: How it's delivered, how it's measured": https://extension.oregonstate.edu/catalog/pub/em-9612-irrigation-water-how-its-delivered-how-its-measured
