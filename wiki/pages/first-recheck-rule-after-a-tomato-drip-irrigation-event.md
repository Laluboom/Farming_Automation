# First Recheck Rule After A Tomato Drip-Irrigation Event

## Sub-question

When should a beginner recheck the 6-inch soil-moisture sensor after a tomato drip-irrigation event?

## Short Answer

For the current beginner tomato prototype, use the next day as the first decision recheck after a drip event, rather than reading the sensor immediately and making another watering decision right away. A practical starter rule is: after the 110-minute irrigation event, wait about 24 hours, read the 6-inch sensor at the normal daily check time, and only allow another irrigation run if the sensor has dried back to the 25 to 30 centibar trigger and rain is not expected soon.

## Confirmed Facts From Local Course Material

- The main course question asks how a farm automation system can make practical irrigation decisions with minimal human effort.
- The local wiki already narrowed the first automation target to irrigation timing.
- The local wiki already chose an outdoor tomato drip-irrigation prototype in loam or silt loam soil.
- The local wiki already chose a first trigger of about 25 to 30 centibars, a 6-inch starter sensor depth, and a first runtime of about 110 minutes.

## Focused External Evidence

- Utah State University Extension says that when water is added by irrigation or precipitation, soil exceeds field capacity and then reaches field capacity after about 1 to 2 days of gravity drainage.
- The same Utah State guide says growers should keep a daily log of sensor-value changes and use those readings to improve irrigation scheduling.
- Oregon State University Extension explains that after saturation, gravitational water drains from large pores until the soil reaches field capacity, which is the more stable condition used for irrigation management.

## First Prototype Rule

- After the 110-minute irrigation event, do not use the immediate post-run reading as the next irrigation decision point.
- Recheck the 6-inch sensor the next day, at about the same daily time each day.
- If the sensor is still wetter than the 25 to 30 centibar trigger, do not irrigate and continue daily checks.
- If the sensor has dried back to about 25 to 30 centibars and the rain-delay rule does not block watering, allow the next irrigation run.

## Why This Is A Reasonable First Rule

- It avoids treating a just-watered, still-draining soil profile as the stable reading for the next decision.
- It matches the low-cost beginner goal by using one simple daily checkpoint instead of a more complex hourly control loop.
- It fits the local prototype sequence: trigger, runtime, then one repeatable recheck step.
- It keeps the decision logic understandable for a first automation build.

## Assumptions And Inferences

- The "next day" recheck is a beginner-friendly operational inference from the extension guidance that soils may need about 1 to 2 days to drain back toward field capacity after irrigation.
- This page assumes a once-daily decision loop is acceptable for an outdoor tomato prototype; the sources support daily tracking but do not prescribe this exact software schedule.
- This page does not claim that every soil, mulch, or weather condition will stabilize on the same timetable.

## What Still Needs To Be Chosen

- One exact drip tape specification instead of the current assumed example flow rate
- One canonical tomato bed setup such as raised bed or small field row
- Whether the first build should log only daily sensor values or also store each runtime event and rainfall adjustment
- Whether a second deeper sensor should become part of the first hardware version or remain a later upgrade

## Evidence Used

- [main_question.md](../../main_question.md)
- [First Threshold For An Outdoor Tomato Irrigation Prototype](./first-threshold-for-outdoor-tomato-irrigation.md)
- [First Sensor Depth For An Outdoor Tomato Irrigation Prototype](./first-sensor-depth-for-outdoor-tomato-irrigation.md)
- [First Runtime Rule For An Outdoor Tomato Drip-Irrigation Prototype](./first-runtime-rule-for-outdoor-tomato-drip-irrigation.md)
- Utah State University Extension, "Irrigation Management in High Tunnels": https://extension.usu.edu/agriculture-and-natural-resources/irrigation-high-tunnels
- Oregon State University Extension, "Soil moisture monitoring to support irrigation scheduling": https://extension.oregonstate.edu/catalog/em-9868-soil-moisture-monitoring-support-irrigation-scheduling
