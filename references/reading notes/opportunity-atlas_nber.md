# NBER w25147 — “The Opportunity Atlas” (Chetty et al., 2018)

**Links:** [NBER working paper][nber] 

[nber]: https://www.nber.org/papers/w25147

> **Main idea:** Where kids grow up—down to very small neighborhoods—strongly relates to their adult outcomes. Differences are mostly **local**, and what matters most is the **immediate social environment**, not how close jobs are.

---

## Why this paper matters for our project

* We should analyze at **small neighborhood units** (Census **tracts** or **block groups**), not city or county averages.
* For mapping access, use the area kids can actually reach on foot/transit: roughly **a 10–12 minute walk (~0.5–0.6 miles / ~1 km)**.
* To find “opportunity deserts,” look at **youth-serving places + social conditions** (adult employment, family stability, school performance)—not just job centers.

---

## What the paper finds

* **Most differences are hyper-local.** Two nearby neighborhoods can produce very different adult outcomes for kids, even in the same county or school area.
* **The signal is real.** Neighborhood differences aren’t just noise; they’re stable and meaningful.
* **Neighborhoods aren’t one-size-fits-all.** A place that’s good for one group or outcome (e.g., income) might not be for another (e.g., incarceration risk). We should look by **subgroup** and **outcome**.
* **What predicts better outcomes:** more **employed adults nearby**, higher local **incomes**, higher **two-parent share**, stronger **school/test score** environment, and **social capital**—**within about half a mile**.
* **What doesn’t predict by itself:** being close to job centers or in a booming local job market does **not** automatically translate to better outcomes for kids.

---

## How reliable are these neighborhood signals?

* **They’re persistent.** Even if we use estimates that are ~10 years old, they still carry most of their predictive value.
* **They’re not just sorting.** Experimental evidence (Moving to Opportunity) lines up with the observational patterns, suggesting much of the neighborhood effect is **causal**.

---

## What this means for our San Diego map 

* **Geometry:** work at **tract or block-group** level. Keep BG for internal analysis; aggregate to tract for public views if needed.
* **Access radius:** compute access using **~0.5–0.6-mile walk-sheds** (or equivalent 10–15-minute transit isochrones).
* **Core indicators to layer:**

  * **Services:** YMCA, libraries, SDYS, parks/rec.
  * **Social environment:** adult employment rate (or proxy), two-parent share, school performance/test score proxy, social capital where available.
  * **Barriers:** **youth population** (for normalization), **households with zero vehicles**, **income** (context, not as a “deficit” label).
* **Metrics to produce quickly:**

  * **Services per 1,000 youth** by tract/BG.
  * **Distance to nearest 1/3/5 services** (walk/transit).
  * **Transit frequency near youth areas** (arrivals within 500 m).
  * **Missingness flags** (hours, eligibility, capacity).
* **Design choices to document:**

  * Why we chose **5–17** as the primary youth cohort (and test **10–19** as a sensitivity).
  * Why we used **0.5–0.6-mile** buffers/isochrones.
  * Why we **normalize by youth population** (not total population).
  * How we treat **subgroups** (e.g., race/gender) and **different outcomes** (income vs incarceration).

---

## Starter “desert” score (simple, transparent, adjustable)

> Begin unweighted; adjust with partners after interviews.

* **Higher is better access** (flip the sign if you prefer “desert severity” instead):

  * **+** services_per_1k_youth
  * **+** transit_arrivals_within_500m
  * **–** nearest3_distance_km
  * **–** pct_zero_vehicle
  * **Context only:** income (use carefully; don’t let it dominate)

Run **sensitivity checks**: try 0.4–0.8-mile buffers, reweight terms, compare ranks. Report **top/bottom deciles** and how stable they are.

---

## Notes for data intake and communication

* Use **precision-adjusted** estimates and exclude subgroup results with poor reliability.
* School boundaries don’t perfectly match tracts; that’s okay—effects remain within school areas and within neighborhoods.
* Be explicit that these are **associations**; use the MTO result to justify **targeting**, not to claim any one site “causes” outcomes.
* Always include a **“Data Gaps & Caveats”** box: hours, eligibility, capacity, safety, and awareness are often missing but matter a lot.

---

## Quick glossary

* **Tract / Block group:** small Census areas that approximate neighborhoods. BG is smaller (finer detail).
* **Walk-shed:** the area you can reasonably walk from a point (we use ~0.5–0.6 miles).
* **Social capital:** community ties and norms that help people access information/opportunities (we’ll use proxies if direct data is missing).
