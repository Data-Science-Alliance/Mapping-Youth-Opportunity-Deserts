# Paper: The Opportunity Atlas — Chetty et al. (2018)

Link: [https://www.nber.org/papers/w25147](https://www.nber.org/papers/w25147)

## 3 Key Takeaways (Access/Mobility)

* **Opportunity is hyper-local.** The biggest differences in kids’ adult outcomes are **across nearby tracts within the same county**; what’s just outside the immediate neighborhood adds little once the local context is known. 
* **Social environment > job proximity.** Better outcomes track places with **higher adult employment, higher local incomes, more two-parent households, stronger school/test context, and social capital**, not simply proximity to job centers or local job growth. 
* **Signals are strong, persistent, and partly causal.** Tract differences are mostly **real (not noise)**, **stable over time**, and align with **experimental/quasi-experimental evidence** (MTO; movers), implying sizable **causal effects of place**. 

## Figure to Replicate (and how)

* **Figure concept:** Choropleth of **upward mobility for low-income children by childhood tract** (e.g., mean adult income rank for kids from the **25th parental percentile**). 
  **Needed data:** Opportunity Atlas tract outcomes (p=25), tract geometries (TIGER/ACS), San Diego subset.
  **Steps:**

  1. Join Atlas tract outcomes ↔ Census tract shapefile via **GEOID**.
  2. Filter to **San Diego County**; compute quantiles/deciles.
  3. Style a **quantile choropleth**; label extreme tracts (hi/low).
  4. Optional facets by **gender/race** to show subgroup heterogeneity. 

## Limitations/Caveats

* **Not one size fits all.** A tract that’s “good for income” may be **bad for incarceration** (esp. for men) or differ by subgroup; always check **outcome × subgroup** views. 
* **Privacy/reliability.** Some small cells are suppressed/noisy; subgroup estimates can be less precise—treat single-tract outliers with caution. 
* **Associational maps.** Many patterns are causal at the tract level, but any single map is still **associational**; don’t attribute effects to a single site. 

## “So what for San Diego?”

* **Hypothesis we can test with our map:**
  Tracts with **few youth-serving sites** within a **~0.5–0.6-mile walkshed** and **weaker social environment proxies** (lower adult employment, higher single-parent share, lower school/test context) will align with **worse Atlas outcomes** for low-income youth. 
* **Proxy(s) we can compute now:**

  * **Services per 1,000 youth** (YMCA, libraries, SDYS, parks/rec) by tract/BG.
  * **Nearest-k distance** to services (walk & transit).
  * **Transit arrivals within 500 m** of youth-dense blocks.
  * **% zero-vehicle households** (barrier), **youth population** (denominator). 
* **Data we must collect to avoid bias:**

  * **Hours, eligibility, capacity** for each site (access ≠ presence).
  * **Safety/lighting & sidewalk continuity** along likely paths.
  * **Awareness/usage** (do teens know/use sites?).
  * **Subgroup cuts** (when reliable) so we don’t mask disparities. 

*Why this paper matters for us:* build and analyze at **tract/BG scale**, measure **walk-shed access (~0.5–0.6 mi)**, overlay **services + social environment**, and use Atlas outcomes as **stable, high-signal targets** to locate San Diego’s “opportunity deserts.” 
