# Scene-Conditioned Maritime Pattern-of-Life — Demos

**Live site:** https://pless.github.io/maritime-anomalies/

Prototypes for database-free, cold-start, explainable maritime pattern-of-life
analysis: behavioral normalcy conditioned on *place*, where place is encoded from
static chart-like geography (bathymetry-derived place vocabulary + USACE charted
channels) instead of accumulated traffic history. Models are trained on Puget
Sound + SF Bay and **frozen**; every result is evaluated on Hampton Roads /
Chesapeake — a port the models never saw.

Three demos, three timescales:

1. **[Retrospective anomalies, scene-explained](https://pless.github.io/maritime-anomalies/enc_before_after.html)** —
   211 raw alerts → 107 genuine after three *named, mechanistically explained*
   false-positive classes are removed. Each alert card: observed motion, the
   model's contextual expectation, counterfactual "would be normal in ⟨place⟩",
   conformal confidence, click-to-animate trajectory. Full project story and the
   model description are embedded at the bottom of the page.

2. **[Live threat assessment (causal)](https://pless.github.io/maritime-anomalies/live_threat.html)** —
   the same frozen model run causally (trailing-span, past-only), replaying the
   busiest 6-hour watch: 15 alerts across 360 tracks at a track-level watch FAR
   calibrated against the live decision rule (per-window calibration would flood
   44% of benign tracks — the key methodological finding).

3. **[Multi-hour behaviors (long-timescale arm)](https://pless.github.io/maritime-anomalies/long_behaviors.html)** —
   a 256-step, 2-minute-token transformer (~8.5 h context) discovers nameable
   long-horizon behaviors (pot/trap tending, slow area-working, shoreline
   passage, directed transit) on the training ports and re-finds them, signatures
   matching, in the never-seen Chesapeake. Generic motion saturates at ~1.6 h of
   context; rhythmic work keeps improving to 6.7 h. Includes a look-ahead /
   directional scene-cue ablation for feature-following turns.

All data public: MarineCadastre AIS (June 2024), GMRT bathymetry, USACE National
Channel Framework. CPU-only. Each page is one self-contained HTML file with data
embedded.
