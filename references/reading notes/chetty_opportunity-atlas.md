# The Opportunity Atlas (Chetty, Friedman, Hendren, Jones, Porter)

**Links:** [PDF (Opportunity Insights)][atlas-pdf]

[atlas-pdf]: https://opportunityinsights.org/wp-content/uploads/2018/10/atlas_paper.pdf

> **Main idea:** Kids’ adult outcomes (income, incarceration, etc.) differ a lot across **very small neighborhoods**. The patterns are mostly **local**, stable over time, and are better explained by the **immediate social environment** (nearby adult employment, family structure, school context, social capital) than by proximity to job centers. 

---

## Why this paper matters for our project

* Analyze San Diego at **tract / block-group** scale (not city/county averages) because the biggest differences are **within counties across nearby tracts**. 
* Build access metrics around what kids can realistically reach: about a **10–12 minute walk (~0.5–0.6 miles / ~1 km)**; conditions outside that radius add little. 
* Use **outcome-based targeting** (tract outcomes) to find “opportunity deserts,” not just poverty/job density proxies. 

---

## What the paper finds 

* **Hyper-local differences:** Over half of the variability in upward mobility is **across tracts within the same county** (≈54.5%); 32% is across commuting zones; 13.5% across counties within CZs. Two nearby tracts can diverge sharply. 
* **Schools explain some, not all:** High-school catchments explain ~**28%** of total variance; large differences remain **within the same catchment** → non-school neighborhood effects matter. 
* **Strong signal, not noise:** Only about **9%** of raw tract variance is noise; the **true** SD across tracts is ~**6.2 percentiles** in income rank (precise enough to target). 
* **Not one-size-fits-all:** “Good for income” may not mean “good for incarceration risk”; subgroup patterns (race/gender) differ → provide subgroup views when feasible. 
* **What actually predicts better outcomes (within ~0.6 mi):** more **employed adults nearby**, higher **mean incomes**, higher **two-parent share**, stronger **school/test score context**, and **social capital**. **Job proximity/growth by itself** is not predictive. 
* **Causal credibility:** Experimental (MTO) and quasi-experimental mover designs align with the Atlas patterns (e.g., **corr ≈ 0.60**, slope **≈ 0.71**), implying much of the cross-tract difference reflects **causal neighborhood effects**, not just sorting.
* **Policy framing:** Data on **children’s outcomes** helps target better than traditional proxies (poverty, job growth). 

---

## How reliable are these neighborhood signals?

* **Persistent over time:** Cross-cohort correlations are high; old tract estimates still retain most predictive value (the decay over ~10 years is modest). Useful for **today’s targeting** even with historical outcomes.
* **Disclosure-safe but precise:** Estimates use differential privacy and cell suppression where needed; still, tract-level precision is high overall. 

---

## What this means for our San Diego map

* **Geometry:** Work at **tract/BG** scale. Use BG internally; aggregate to tract for public views if needed. 
* **Access radius:** Compute **0.5–0.6-mile** walk-sheds (and 10–15-min transit isochrones) around YMCA, Libraries, SDYS, City/County Parks & Rec. 
* **Core layers to overlay:**

  * **Services:** YMCA, libraries, SDYS, rec/parks sites.
  * **Social environment:** adult employment rate (or proxy), two-parent share, school/test score proxy, social capital (if available).
  * **Barriers/normalizers:** **youth population** (for per-1k denominators), **% zero-vehicle households**, **income** for context (don’t let it dominate). 
* **Metrics to compute now:**

  * **Services per 1,000 youth** (tract/BG).
  * **Distance to nearest 1/3/5 services** (walk & transit).
  * **Transit arrivals within 500 m** of youth-dense blocks.
  * **Missingness flags**: hours, eligibility, capacity. 
* **Starter “access score” (unweighted; adjust with partners):**

  ```
  score = (+) services_per_1k_youth
        + (+) transit_arrivals_500m
        + (–) nearest3_distance_km
        + (–) pct_zero_vehicle
        + context: income   # use for context; don't overweight
  ```

  Then **sensitivity**: try 0.4–0.8-mile buffers, reweight terms, compare youth cohorts (5–17 vs 10–19); report top/bottom deciles & rank stability. 

---

## Communication & ethics checklist

* **Be explicit:** These are **associations** at small areas; much variation is causal at the tract level, but **no single site** is “the cause.” Reference MTO alignment for credibility, not over-claiming. 
* **Name the gaps:** Hours, eligibility, capacity, safety, and awareness are often missing but important—call them out alongside maps. 
* **Avoid stigmatizing labels:** In public artifacts, prefer “**priority areas**” / “**areas of unmet access**” over “deserts.”

---

## Quick glossary 

* **Census tract / block group:** Standard map areas the Census uses.

  * A **tract** is a larger neighborhood area (roughly a few thousand people).
  * A **block group (BG)** is a smaller piece inside a tract (more detail).

* **Walk-shed:** The area someone can realistically walk from a place.
  For our project, assume about **0.5–0.6 miles** (≈10–12 minutes on foot).