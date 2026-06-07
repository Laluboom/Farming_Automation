# First Threshold For An Outdoor Tomato Irrigation Prototype

## Sub-question

What first soil-moisture threshold and rain-delay cutoff can a beginner use for an outdoor tomato drip-irrigation prototype in loam soil?

## Short Answer

For a first outdoor tomato prototype in loam or silt loam soil, a reasonable starter rule is to trigger drip irrigation at about 25 to 30 centibars (kPa) of soil water tension and to delay watering if about 0.25 inch (6 mm) of rain is forecast within the next day, then recheck the sensor after the rain window.

## Confirmed Facts From Local Course Material

- The main course question asks how a farm automation system can make practical irrigation decisions with minimal human effort.
- The local wiki already narrowed the simplest first automation target to irrigation timing.
- The local irrigation prototype page already concluded that a beginner system should use soil moisture, recent water input, and a short rain forecast.

## Focused External Evidence

- Utah State University Extension says tomato drip irrigation can be scheduled with soil moisture tension and that for loam or silt loam soil, drip irrigation should start at 20 to 25 percent depletion, corresponding to about 25 to 30 centibars.
- Oregon State University Extension gives a broader typical irrigation threshold of 30 to 50 centibars for loam or silt loam and notes that high-value or shallow-rooted crops are often irrigated at lower tension values.
- Penn State Extension says that for vegetables on bare ground or under water-permeable mulch, irrigation should be reduced by the amount of rainfall received, giving 0.25 inch of rain as a concrete example.
- Penn State Extension also notes that when plastic mulch is used, weekly irrigation often still needs to be applied regardless of rain because much of the rainfall does not reach the root zone.

## First Prototype Setting

- Crop and context: outdoor tomato bed
- Soil context: loam or silt loam
- Irrigation method: drip
- Surface condition: bare ground or water-permeable mulch, so rainfall still matters
- Sensor trigger: irrigate when soil water tension reaches about 25 to 30 centibars
- Rain delay rule: if at least 0.25 inch of rain is forecast within the next 24 hours, wait and recheck before irrigating

## Why This Is A Reasonable First Setting

- It keeps the prototype aligned with the earlier local decision to automate irrigation before harder tasks like disease diagnosis.
- It uses a crop-specific threshold instead of a generic moisture rule.
- It stays near the lower end of the loam-soil threshold range, which fits the extension guidance that higher-value crops are often irrigated before soils become much drier.
- It turns the vague idea of "meaningful rain" into one explicit starter cutoff that a beginner can test.

## Assumptions And Inferences

- The 25 to 30 centibar trigger is directly supported for tomato drip irrigation in loam or silt loam soil.
- The 0.25 inch rain-delay cutoff is a beginner-friendly inference from extension guidance that 0.25 inch of rainfall should reduce irrigation by the same amount for vegetable beds where rainfall reaches the soil.
- The 24-hour forecast window is a prototype assumption added to make the rule operational; the sources support using rainfall and short-term weather, but they do not prescribe this exact window.
- This page does not claim that one threshold works for all tomato stages, climates, or soil profiles.

## What Still Needs To Be Chosen

- One exact tomato production setting: home garden, raised bed, or small field bed
- One sensor placement depth in the root zone
- One follow-up rule for how long to run irrigation after the trigger is reached
- Whether the prototype assumes bare soil, straw mulch, or plastic mulch

## Evidence Used

- [main_question.md](../../main_question.md)
- [Minimum Inputs For A Beginner Irrigation Prototype](./minimum-inputs-irrigation-prototype.md)
- Utah State University Extension, "Irrigation" for tomato, pepper, and eggplant: https://extension.usu.edu/vegetableguide/tomato-pepper-eggplant/irrigation
- Oregon State University Extension, "Soil moisture monitoring to support irrigation scheduling": https://extension.oregonstate.edu/catalog/em-9868-soil-moisture-monitoring-support-irrigation-scheduling
- Penn State Extension, "Determining How Long to Run Drip Irrigation Systems for Vegetables": https://extension.psu.edu/determining-how-long-to-run-drip-irrigation-systems-for-vegetables/
