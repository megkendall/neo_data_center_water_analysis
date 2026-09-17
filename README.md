# Northeast Ohio Data Centers and Water

An analysis of how data center development in Northeast Ohio relates to the
water systems that would serve it — built from publicly available facility
records, utility documents, and operator sustainability disclosures.

## The question

Data center projects are almost always described in megawatts. The water
implications are much harder to see: public sources rarely report a
facility's actual water consumption or water-use efficiency (WUE), and it's
often unclear which water utility would even serve a given site.

This project asks: **what does the same hypothetical data-center water-demand
scenario look like across different Northeast Ohio water-system contexts?**

Rather than estimate actual consumption for real facilities — which the
public evidence doesn't support — it builds a **standardized scenario
model**: four IT-capacity levels (50 / 150 / 300 / 750 MW) crossed with four
water-intensity assumptions (0.05 / 0.20 / 0.40 / 1.50 L/kWh, grounded in
operator-reported WUE benchmarks), compared against seven Northeast Ohio
water systems with documented capacity and use data.

## Key findings

1. **The same modeled demand means very different things in different water
   systems.** The highest scenario (750 MW, 1.50 L/kWh → 7.13 MGD) is ~1.3%
   of Cleveland Water's 540 MGD treatment capacity, but ~178% of the
   Shalersville system's 4 MGD peak treatment capacity.
2. **Megawatts alone don't predict water demand.** A 750 MW facility at the
   lowest intensity assumption uses *less* modeled water than a 50 MW
   facility at the highest intensity assumption.
3. **Cleveland's system-scale context differs substantially** from the
   smaller systems in the analysis, cautioning against treating Northeast
   Ohio as one uniform water story.
4. **Public facility-level water-use evidence is sparse.** Across seven
   analytical facility cases, none had a complete, publicly established
   average/annual water-use figure or facility-specific WUE.
5. **The relevant water-provider relationship is often unclear.** Four of
   seven facility cases had no water provider publicly established in the
   sources reviewed.

None of this establishes how much water any real facility will use, or
whether any system has spare capacity for more demand — see
[Interpretive guardrails](#interpretive-guardrails) below. Full reasoning,
boundaries, and the "skeptical question" treatment of each finding are in
[`outputs/narrative/findings_and_interpretation.md`](outputs/narrative/findings_and_interpretation.md).

## Repo structure

```
data/                   Cleaned, source-linked datasets (see below)
notebooks/
  scenario_analysis.ipynb   Scenario modeling, system comparison, validation
outputs/
  figures/               Final charts (see below)
  tables/                 Analysis-ready CSV exports of the results
  narrative/              Working analytical writeups and story framing
```

### Data (`data/`)

Three linked datasets, each with a `*_master` file, a `*_data_dictionary`
file defining every column, and a sources file tracing each claim back to a
publisher and URL:

| Dataset | Master file | What it covers |
|---|---|---|
| Facilities | [`facilities_master_v1_FINAL.csv`](data/facilities_master_v1_FINAL.csv) | 21 Northeast Ohio data-center projects — status, capacity, cooling, and (where available) water use/provider evidence |
| Water-intensity benchmarks | [`water_intensity_benchmarks_master_v1_FINAL.csv`](data/water_intensity_benchmarks_master_v1_FINAL.csv) | 17 operator-reported WUE/PUE observations (AWS, Equinix, etc.) used to ground the scenario water-intensity assumptions |
| Water systems | [`water_systems_master.csv`](data/water_systems_master.csv) | 7 Northeast Ohio water utilities/districts used as analytical cases — source, treatment capacity, existing use, population served |

[`data/water_systems_research.md`](data/water_systems_research.md) is the
underlying per-system research record (source excerpts, figures, and
caveats) that `water_systems_master.csv` was distilled from.

Every "reported" value in these datasets traces to a specific source in
[`data/sources.csv`](data/sources.csv) or
[`data/facilities_sources_v1_FINAL.csv`](data/facilities_sources_v1_FINAL.csv) /
[`data/water_intensity_benchmark_sources_v1_FINAL.csv`](data/water_intensity_benchmark_sources_v1_FINAL.csv).
Missing values are preserved as missing (`not publicly found`,
`not_applicable`, etc.) rather than filled in or estimated — see the
relevant `*_data_dictionary` file for the full set of status categories
before joining or filtering.

### Notebook (`notebooks/scenario_analysis.ipynb`)

Builds the 16 standardized scenarios (4 capacities × 4 intensities), joins
each against all 7 water systems (112 scenario-system rows), calculates
modeled water demand and its share of documented treatment capacity, and
runs validation checks against the frozen methodology assumptions.

### Outputs (`outputs/`)

- **`figures/`** — final charts: water-system contexts (`fig01`), scenario
  water demand (`fig02`), scenario demand vs. treatment capacity as a
  heatmap and as small multiples (`fig03`), and the facility disclosure
  matrix (`fig04`).
- **`tables/`** — analysis-ready CSVs: the full 112-row scenario × system
  comparison, plus three summary tables (water systems, standardized
  scenarios, analytical facilities) that back the figures and findings.
- **`narrative/`** — the analytical record behind the findings above:
  [`findings_and_interpretation.md`](outputs/narrative/findings_and_interpretation.md)
  (validated findings with boundaries),
  [`findings_section_spine.md`](outputs/narrative/findings_section_spine.md)
  (the argument structure), and
  [`project_narrative.md`](outputs/narrative/project_narrative.md) (the
  project story). These are working documents, not final report copy.

## Interpretive guardrails

This model is easy to misread. A few rules the analysis itself insists on:

- **Modeled demand ≠ actual consumption.** The standardized scenarios are
  hypothetical comparison points, not predictions for any real facility.
- **Treatment capacity ≠ available capacity.** A documented treatment-capacity
  figure is a system characteristic, not spare capacity, headroom,
  sustainable yield, or a feasibility threshold. A scenario using >100% of
  a system's treatment capacity does not mean that system "can't" support
  a project — it means the modeled demand is large relative to that one
  documented metric.
- **Don't infer a facility's water provider from geography alone** — several
  facility-provider relationships are proposed, uncertain, or simply not
  publicly established.
- **"Not publicly found" is a statement about available evidence**, not a
  claim that data doesn't exist or was withheld.

See [`outputs/narrative/findings_and_interpretation.md`](outputs/narrative/findings_and_interpretation.md#interpretive-rules-to-preserve)
for the complete list.

## Reproducing the analysis

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab notebooks/scenario_analysis.ipynb
```

`scenario_analysis.ipynb` (pandas/numpy only) reproduces the scenario
construction, the 112-row scenario × water-system comparison, and the
validation checks — i.e. everything in `outputs/tables/`. The charts in
`outputs/figures/` were produced separately; `matplotlib` is included in
`requirements.txt` for that purpose but isn't required just to run the
notebook.

## Status

The datasets and scenario methodology are frozen and have passed an internal
validation pass (see the notebook's final section). The narrative documents
in `outputs/narrative/` are working analytical writeups, not final report
copy — treat the datasets, dictionaries, and notebook as authoritative
where they and the narrative disagree.

## License

This work is licensed under [CC BY 4.0](LICENSE) — you're free to share and
adapt it, including commercially, as long as you give appropriate credit.

## Citation / sources

Every figure in this analysis traces to a specific public source — see the
`*_sources*.csv` files in `data/`. This is an independent analysis and is
not affiliated with any facility operator or water utility named here.

If you reuse this data or analysis, please credit:

> Meg Kendall, *Northeast Ohio Data Centers and Water* (2026).
