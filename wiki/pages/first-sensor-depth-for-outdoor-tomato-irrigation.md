# First Sensor Depth For An Outdoor Tomato Irrigation Prototype

## Sub-question

What first sensor depth should a beginner use for an outdoor tomato drip-irrigation prototype in loam soil?

## Short Answer

If a beginner prototype uses only one soil-moisture sensor for outdoor tomatoes in loam soil, a practical first placement is about 6 inches deep in the active root zone. If a second sensor is added later, place it deeper, around 18 to 24 inches, to check whether irrigation is reaching the lower root zone or moving too deep.

## Confirmed Facts From Local Course Material

- The main course question asks what sensors or inputs are needed for a farm automation system.
- The local wiki already narrowed the first automation target to irrigation timing.
- The local wiki also already chose an outdoor tomato drip-irrigation prototype in loam or silt loam soil with a starter trigger of about 25 to 30 centibars.

## Focused External Evidence

- Utah State University Extension lists tomato under vegetables with a moderate effective root depth of about 18 to 24 inches.
- Oregon State University Extension says most vegetables have an effective rooting depth of about 12 to 20 inches and that about 70 percent of soil moisture uptake comes from the upper 50 percent of that effective rooting depth.
- Oregon State University Extension also says sensors should be installed within the effective rooting depth and that shallow-rooted crops are often monitored with two depths.
- Utah State University Extension's high-tunnel irrigation guidance gives an explicit tomato example: install sensors at 6 inches deep as a minimum soil depth and at 18 to 24 inches near the bottom of the average rooting depth.

## First Prototype Setting

- Crop and context: outdoor tomato bed
- Soil context: loam or silt loam
- Irrigation method: drip
- Starter monitoring setup: one soil-moisture sensor at about 6 inches deep
- Expansion path: add a second sensor at about 18 to 24 inches once the single-sensor prototype works

## Why This Is A Reasonable First Setting

- It matches the local goal of keeping the first prototype low-cost and beginner-friendly.
- It puts the first sensor in the upper active root zone, where a large share of vegetable water uptake occurs.
- It stays compatible with the earlier local threshold page, which already assumed tomato drip irrigation and now needs one operational sensor placement.
- It leaves room for a second deeper sensor later to detect under-watering or deep percolation without making the first build more complex than necessary.

## Assumptions And Inferences

- The 6-inch starter depth is directly supported by Utah State's tomato example for sensor placement, though that example is framed for high-tunnel tomatoes rather than an outdoor bed.
- Using one 6-inch sensor as the first build is a beginner-friendly inference from the local course goal and the broader extension guidance that most vegetable water uptake happens in the upper part of the root zone.
- The 18 to 24 inch follow-up depth is supported as a second monitoring depth near the lower tomato root zone, not as the recommended single first sensor.
- This page does not claim that one depth works equally well for all tomato stages, soils, or mulching setups.

## What Still Needs To Be Chosen

- One exact tomato production setting such as a raised bed or small field bed
- One simple runtime rule for how long the drip system should run after the threshold is reached
- Whether the prototype assumes bare soil, straw mulch, or plastic mulch
- Whether the first build should log only current readings or also keep a daily history

## Evidence Used

- [main_question.md](../../main_question.md)
- [First Threshold For An Outdoor Tomato Irrigation Prototype](./first-threshold-for-outdoor-tomato-irrigation.md)
- Utah State University Extension, general vegetable irrigation guide: https://extension.usu.edu/vegetableguide/management/irrigation.php
- Oregon State University Extension, "Irrigation management basics": https://extension.oregonstate.edu/water/irrigation/irrigation-management-basics
- Oregon State University Extension, "Soil moisture monitoring to support irrigation scheduling": https://extension.oregonstate.edu/catalog/em-9868-soil-moisture-monitoring-support-irrigation-scheduling
- Utah State University Extension, "Irrigation Management in High Tunnels": https://extension.usu.edu/agriculture-and-natural-resources/irrigation-high-tunnels.php
