# Project Discussion

A place for notes/conversations about the project - a sort of long form, work-in-progress Readme.

##### Early Note

There's a huge "bias" in this data in that it only captures "positive" data. For example, if there's a super safe street out there somewhere that never has any accidents, we don't know about it.

For local municipalities, traffic accidents tend to cluster in certain "hot spots", and the goal is to identify those (heat map visualization) and implement measures to make them safer. Because we're looking at national level data for the DOT, this type of approach is likely not as useful.

Our focus is on identifying actionable insights that can be turned into safety measures, so "more accidents happen when it rains" would not be helpful. However, if we found a particularly strong correlation with weather/reduced visibility, we could recommend a "turn on your head lights!" awareness campaign, or similar.

## Hypotheses for Actionable, Non-Obvious Insights 
(Summary by Gemini)

To move beyond obvious correlations (e.g., "rain causes accidents"), our analysis aims to uncover insights that are non-obvious, actionable, and directly derivable from the data.

### General Framework for "Non-Obvious" Hypotheses:

Instead of simply looking for `X` causes `Y`, we will explore:
* **Disproportionate Impact:** Does `X` cause `Y` *disproportionately* compared to general traffic volume or other similar conditions?
* **Interaction Effects:** Does `X` cause `Y` *especially when Z condition is also met*?
* **Unexpected Relationships:** Does `X` have an *unexpected effect* on `Y` or `Severity`?

### Specific Hypotheses for Exploration:

We'll begin by focusing on **Weather Info** and **Road Features**, keeping the "Severity" definition (impact on traffic) central to our interpretation.

#### 1. Weather Info (Beyond Raw Counts)

* **Hypothesis:** Certain severe weather conditions (e.g., **Fog, Heavy Snow, Freezing Rain, High Winds**) are disproportionately associated with **Severity 4 accidents**, even when compared to the much more common "Rain" or "Sleet" conditions.
    * **Why it's non-obvious:** While rain causes more *total* accidents, we hypothesize that specific, less frequent severe weather conditions lead to incidents that cause *exceptionally long delays (Severity 4)* per occurrence, perhaps due to reduced visibility leading to higher-speed collisions, or unique clearance challenges.
    * **Actionable Insight:** If confirmed, this points to a need for highly targeted public safety advisories (e.g., specific warnings for "black ice" or "dense fog" zones), or investment in infrastructure (e.g., enhanced warning systems, rapid response teams) for these specific, high-impact weather phenomena, beyond general "drive carefully in bad weather" messages.

#### 2. Road Features & Their Interaction with Time/Severity

* **Hypothesis:** Accidents occurring at **Junctions** or involving **Traffic Signals** during **off-peak hours (e.g., late night/early morning)** are disproportionately likely to be **Severity 3 or 4**, relative to the overall accident count at those times.
    * **Why it's non-obvious:** During peak hours, these locations are busy and prone to minor accidents. However, if severe accidents *still* cluster at these points when traffic volume is low, it suggests contributing factors like speeding, red-light running, or impaired driving, rather than just congestion.
    * **Actionable Insight:** Targeted enforcement (e.g., automated red-light cameras, increased police presence) at specific high-risk intersections during low-traffic periods, or re-evaluation of signal timing/visibility during low-light conditions.

#### The "Description" Wildcard (Future Work):

If the above structured analyses don't yield sufficiently non-obvious insights, a deeper dive into the `Description` field using Natural Language Processing (NLP) could uncover patterns related to specific vehicle types, cargo, or unique incident characteristics that drive extreme severity, regardless of external factors.
