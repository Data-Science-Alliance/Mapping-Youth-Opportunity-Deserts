# Paper: The Opportunity Atlas — Chetty et al. (2018)

Link: [https://opportunityinsights.org/wp-content/uploads/2018/10/atlas_paper.pdf](https://opportunityinsights.org/wp-content/uploads/2018/10/atlas_paper.pdf)

## 3 Key Takeaways (Access/Mobility)

* **Opportunity is hyper-local.** Most variation in kids’ adult outcomes is across **nearby tracts within the same county**; neighborhood conditions **within ~0.5–0.6 miles** matter most.
* **Social environment beats job proximity.** Kids do better where **more adults are employed**, family stability is higher, schools test better, and social capital is stronger—**not** simply where jobs are dense or growing.
* **Signals are strong and durable.** Tract outcomes have high signal vs. noise and change slowly over time; a large share of cross-tract differences reflects **causal effects of place** (validated against MTO and mover designs).

## Figure to Replicate (and how)

* **Figure concept:** “Upward mobility for low-income children by childhood tract” (map).
  **Metric:** Mean adult **household income rank** (or $ income) for children from **p=25** parental income percentile.
  **Data needed:** Opportunity Atlas tract outcomes (p=25), tract geometries; for overlays later, ACS youth counts.
  **Steps:**

  1. Join tract outcome table to Census tract shapefile via **GEOID**.
  2. Filter to target county (e.g., San Diego).
  3. Choropleth by outcome quantiles; annotate high/low examples.
  4. (Optional) Facet by subgroup (gender/race) to show heterogeneity.

## Limitations/Caveats

* **Not one-size-fits-all.** A tract that’s “good for income” might not be for **incarceration** or for every subgroup (men/women, race/ethnicity).
* **Privacy noise & small cells.** Some subgroup cells are suppressed/noisy; don’t over-interpret single-tract ranks without uncertainty context.
* **Observational + causal mix.** Many differences are causal at the tract level, but maps show **associations**; avoid attributing impact to any single site.

## “So what for San Diego?”

* **Hypothesis we can test with our map:**
  Tracts with **few youth-serving sites within a ~0.5–0.6-mile walk-shed** and **lower adult employment / higher single-parent share** will align with **lower Opportunity-Atlas outcomes** for low-income youth.
* **Proxy(s) we can compute now:**

  * **Services per 1,000 youth** (YMCA, libraries, SDYS, parks/rec).
  * **Nearest-k distance** to services (walk & transit).
  * **Transit arrivals within 500 m** of youth-dense blocks.
  * **% zero-vehicle households** (barrier proxy).
* **Data we must collect to avoid bias:**

  * **Hours, eligibility, and capacity** for each site (access ≠ presence).
  * **Safety/lighting and sidewalk continuity** along likely paths.
  * **Awareness/outreach** (whether teens actually know & use sites).
  * **Subgroup views** (when sample sizes allow) to avoid masking gaps.

---

*Why this paper matters for us:* build at **tract/block-group** scale, measure **walk-shed access (~0.5–0.6 mi)**, overlay **services + social environment** (adult employment, family structure, school context), and treat the Atlas outcomes as **stable, high-signal targets** for prioritizing “opportunity deserts.” 
