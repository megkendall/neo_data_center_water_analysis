# Findings and interpretation

## Purpose

This document records the validated analytical findings and interpretive
boundaries from the Northeast Ohio data center and water analysis. It is
an analytical record, not polished report copy. It should be used
alongside the frozen datasets, standardized scenario methodology, final
tables, and figures when developing the project narrative and
interactive scenario explorer.

## Overall synthesis

The water implications of data center development in Northeast Ohio
cannot be inferred from megawatts or regional water abundance alone.
Modeled demand varies substantially with facility water intensity, while
the significance of that demand varies even more with local water-system
context. At the same time, the facility-specific information needed to
evaluate actual projects --- particularly quantitative water use,
water-use effectiveness (WUE), and in some cases the relevant
water-provider relationship --- is often not publicly established in the
sources reviewed.

The standardized scenario model is therefore intended to explore how
assumptions about facility scale, water intensity, and water-system
context change the interpretation of potential demand. It is not
intended to estimate actual water consumption at individual Northeast
Ohio facilities.

## Validated findings

### 1. The same modeled demand has dramatically different significance across water systems

The highest-demand standardized scenario --- 750 MW at 1.50 L/kWh ---
produces 7.13 MGD of modeled average water demand.

Relative to documented treatment capacity, this is approximately:

-   Cleveland Water: 1.32% of 540 MGD
-   Akron Water: 10.65% of 67 MGD
-   Mahoning Valley Sanitary District: 11.89% of 60 MGD
-   Canton Water: 16.21% of 44 MGD
-   Lake County, Bacon Road / East Sub-District: 79.25% of 9 MGD
-   Portage County, Shalersville: 178.32% of 4 MGD

Erie County's Perkins District is excluded from this comparison because
a treatment-capacity denominator is not applicable to the
purchased-finished-water distribution system as defined in the dataset.

**Interpretation:** The same hypothetical data center demand can have
very different relative scale depending on the water-system context.
Regional freshwater abundance does not by itself describe the scale of a
potential demand relative to the particular utility system involved.

**Boundary:** These percentages do not establish whether a system can or
cannot serve a project. Treatment capacity is a documented system
characteristic, not available capacity, treatment headroom, sustainable
yield, or a water-stress threshold.

**Skeptical question:** Does 178% mean Shalersville could not support a
750 MW water-intensive facility?

**Response:** No. It shows that the hypothetical modeled demand is large
relative to the documented 4 MGD treatment-capacity metric.
Infrastructure feasibility would require additional information that
this analysis does not model.

### 2. Facility scale in MW is not sufficient to infer water demand

A 750 MW scenario at 0.05 L/kWh produces approximately 0.238 MGD of
modeled demand. A 50 MW scenario at 1.50 L/kWh produces approximately
0.476 MGD.

The 750 MW case therefore has 15 times the standardized IT capacity but
roughly half the modeled water demand.

At any fixed capacity, the 1.50 L/kWh scenario produces 30 times the
modeled demand of the 0.05 L/kWh scenario.

**Interpretation:** Water intensity can substantially alter the
relationship between electrical capacity and modeled water demand. MW
alone is therefore an inadequate proxy for water demand.

**Boundary:** The four water-intensity values are standardized
analytical assumptions informed by the external benchmark evidence. They
are not predictions of the water intensity of any individual Northeast
Ohio facility.

**Skeptical question:** Are the low and high water-intensity scenarios
realistic enough for this comparison to be meaningful?

**Response:** The frozen benchmark evidence supports a wide range of
observed water-intensity values and cooling contexts. The standardized
values deliberately represent contrasting analytical cases rather than
forecasts for particular facilities.

### 3. Cleveland's system-scale context differs substantially from the smaller analytical cases

The highest-demand standardized scenario, 7.13 MGD, is approximately
1.32% of Cleveland Water's documented 540 MGD treatment capacity.

A 750 MW scenario at 0.40 L/kWh produces approximately 1.90 MGD,
equivalent to about 0.35% of documented Cleveland treatment capacity.

**Interpretation:** Cleveland's interconnected Great Lakes water system
provides a substantially different system-scale context from the smaller
water systems included in the analysis. This cautions against treating
Northeast Ohio as a single uniform water context.

**Boundary:** Cleveland's large treatment capacity does not demonstrate
that data center water use is inconsequential. The analysis does not
model local distribution constraints, peak demand, environmental
effects, infrastructure costs, project-specific demand, or available
system headroom.

**Skeptical question:** Does Cleveland's large treatment capacity mean
water impacts from data centers are not a meaningful concern there?

**Response:** No. It means that standardized modeled demand is
relatively small compared with this particular documented system metric.
Other water, infrastructure, governance, and transparency questions
remain outside that comparison.

### 4. Public facility-level water-use evidence is sparse

Across the seven analytical facility cases:

-   capacity evidence is available for six of seven cases;
-   cooling evidence is available for all seven cases, although some
    evidence is qualified;
-   no complete facility-level average or annual water-use value was
    publicly established for any of the seven cases;
-   no facility-specific WUE value was publicly established for any of
    the seven cases;
-   Bitdeer Shalersville has a reported 350 gpd average-use figure, but
    it is scope-limited and does not represent the full proposed campus;
-   Perry Technology Park / Champion Farm has a reported 273,000 gpd
    maximum allocation for all facility water uses, which is not
    equivalent to observed consumption.

**Interpretation:** The public evidence does not support defensible
estimates of actual water consumption for the seven analytical
facilities. This is a central reason for maintaining a separate
standardized scenario model rather than imputing facility-specific water
use.

**Boundary:** "Not publicly found" means the information was not
established in the public sources reviewed. It does not mean that the
information does not exist or that a facility or utility has necessarily
withheld it.

**Skeptical question:** Why not apply an industry-average WUE to each
facility's reported MW?

**Response:** Doing so would create facility-specific estimates that are
not supported by the observational evidence. It would also combine
benchmark uncertainty with heterogeneous facility capacity definitions,
creating greater apparent precision than the data justify.

### 5. The relevant water-provider relationship is often not clearly established in public sources

Among the seven analytical facility cases:

-   one has a reported site-provider relationship;
-   two have proposed, uncertain, or system-context relationships;
-   four have no water provider publicly established in the sources
    reviewed.

The facility-to-system relationships used for contextual analysis
therefore vary in evidentiary strength and should not be inferred from
geography alone.

**Interpretation:** Evaluating a data center in local water-system
context requires knowing which system would actually supply the site.
Publicly establishing that relationship can itself be difficult, adding
a second transparency limitation beyond the absence of quantitative
facility water-use data.

**Boundary:** This finding should be framed as a limitation of publicly
available evidence, not proof of deliberate nondisclosure.

**Skeptical question:** Is this a transparency problem, or simply a
limitation of the research?

**Response:** The analysis can establish only that the relationship was
not publicly established in the sources reviewed. It cannot determine
why the information was unavailable.

## Interpretive rules to preserve

The following rules should carry into the report, README, figures, and
interactive explorer:

-   Use **modeled water demand** for standardized scenario outputs.
-   Do not describe standardized scenarios as estimates of actual
    facility consumption.
-   Do not use external benchmarks to fill missing facility water-use or
    WUE values.
-   Do not sum or directly compare facility MW values without preserving
    their heterogeneous capacity definitions and scopes.
-   Do not interpret treatment capacity as available capacity, spare
    capacity, headroom, sustainable yield, or a stress threshold.
-   Do not infer a facility's water provider solely from geography.
-   Preserve missing and not-applicable values rather than converting
    them to zero.
-   Preserve distinctions between reported, qualified,
    proposed/uncertain, missing, and not-applicable evidence.
-   Do not introduce drought-safe yield, population normalization,
    synthetic stress scores, or arbitrary thresholds into the frozen
    standardized model.
-   Keep observational facility evidence, water-system context, and
    hypothetical scenario modeling analytically separate.

## Implications for the interactive explorer

The explorer should help users understand how standardized assumptions
change modeled water demand and its relative scale across documented
water-system contexts.

Appropriate user inputs include:

-   standardized IT capacity: 50, 150, 300, or 750 MW;
-   standardized water intensity: 0.05, 0.20, 0.40, or 1.50 L/kWh;
-   selected analytical water-system case.

Appropriate outputs include:

-   modeled average water demand in MGD;
-   modeled annual water demand in MG or BG;
-   comparison with documented average daily water use where valid;
-   comparison with documented treatment capacity where valid;
-   system-specific qualifications and explicit N/A treatment.

The explorer should not function as an "actual facility water-use
calculator." Actual Northeast Ohio facilities may be presented as
contextual evidence, but their reported MW values should not
automatically be converted into modeled facility water demand.

## Analytical status

The core analytical outputs have passed a final internal sanity check
for scenario arithmetic, denominator use, missing-value handling,
facility evidence classification, and separation between observational
and hypothetical data.

The next phase is to develop the public-facing narrative and interactive
explorer from this frozen analytical interpretation.
