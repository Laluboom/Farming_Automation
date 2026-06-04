# Simplest First Automation Decision

## Sub-question

Which farm decision is simplest to automate first in a low-cost beginner prototype?

## Short Answer

Irrigation timing is the simplest first automation target.

## Confirmed Facts From Local Course Material

- The main question asks which farm decisions are worth automating first, including irrigation timing, fertilizer scheduling, disease alerts, pest detection, crop selection, and harvest planning.
- The main question also asks for the simplest prototype that proves the idea without requiring expensive hardware.
- The local reference summary says plant disease image datasets are relatively mature and benchmark-driven.
- The same summary says there is no single clean public dataset covering water, nutrition, soil, and location requirements; those needs usually require combining multiple sources.

## Reasoning

Irrigation timing fits a beginner prototype better than disease diagnosis or nutrient scheduling because it can be framed as a narrower decision:

- decide whether watering should happen now, later, or not at all
- rely on a small set of inputs such as soil moisture, recent weather, and forecast
- avoid the harder multimodal diagnosis problem of telling apart disease, pests, nutrient deficiency, and water stress from similar symptoms

## Assumptions And Inferences

- This page infers a prototype priority from the local materials; the local materials do not explicitly rank irrigation as number one.
- The recommendation depends on the goal being a low-cost proof of concept rather than a full agronomy system.
- A practical beginner system can start with threshold-based or simple predictive rules before adding richer plant-specific models.

## Prototype Boundary

A first prototype could stay inside this boundary:

- one crop or plant type
- one growing area
- one decision: water now or wait
- a small input set: soil moisture, recent rainfall, short weather forecast, and a simple watering history

## Why Not Start Elsewhere

- Disease alerts need image interpretation plus uncertainty handling because similar symptoms can come from different causes.
- Fertilizer scheduling depends on broader agronomic context and usually needs stronger crop- and soil-specific knowledge.
- Harvest planning and crop selection depend on longer time horizons and more external variables.

## Evidence Used

- [main_question.md](../../main_question.md)
- [REFERENCE.md](../../REFERENCE.md)
