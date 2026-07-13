# Scene-Explained Maritime Anomalies — Hampton Roads (cold-start)

**Live page:** https://pless.github.io/maritime-anomalies/

A prototype for database-free maritime pattern-of-life anomaly detection:
behavioral normalcy conditioned on *place*, where place is encoded from static,
chart-like geography (bathymetry-derived place vocabulary + USACE charted
channels) instead of accumulated traffic history — so it works cold-start in a
port the model never trained on (Hampton Roads; trained on Puget Sound + SF Bay).

The visualization shows the surviving anomalies after three named
false-positive classes were removed (211 → 107), each alert carrying its own
machine reasoning: observed motion, the model's contextual expectation, and a
counterfactual "this would be normal in ⟨place⟩" attribution with conformal
confidence. Click any card to watch the maneuver animate over the tokenized
scene. The full project story and the model description are embedded at the
bottom of the page.

All data public: MarineCadastre AIS (June 2024), GMRT bathymetry, USACE
National Channel Framework. Everything runs CPU-only; the page is a single
self-contained HTML file with data embedded.
