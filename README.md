# Social Acceptance, Biodiversity, and the Modelling of Residential and Ground-Mounted Photovoltaic Potential in Austria

**Seminar:** Information and Communications Engineering — Research Project  
**Topic:** Electricity Demand Forecasting and Renewable Energy Systems  
**Credit Load:** 6 ECTS (150 hours)  


## Background and Motivation
Austria has committed to generating 100% of its electricity from domestic renewable sources by 2030, requiring an additional 11 TWh/a from photovoltaics (PV) alone — a roughly sixfold increase compared to 2019 production levels. Meeting this target involves not only assessing the physical and technical potential of available surfaces and land, but understanding *who decides* whether a PV system gets installed and *why*. Residential rooftop PV, which could theoretically satisfy the entire 2030 target on its own, is fundamentally constrained by individual and community-level decisions — willingness to pay, trust in institutions, perceived fairness, and attitudes toward the landscape. At the same time, ground-mounted PV systems face increasing scrutiny regarding land-use competition and biodiversity impacts, with evidence showing that social acceptance is heavily driven by where a system is sited and how it is designed.[^1][^2]

This research project sits at the intersection of these challenges. You will carry out a structured literature review on the social, economic, and attitudinal drivers of PV adoption, integrate insights from recent transdisciplinary Austrian research (including the BioPV project), and build upon existing spatial PV potential modelling methodologies to develop an **enhanced, socially and ecologically weighted PV potential model for Austria**. The goal is a unified analytical framework that goes beyond purely technical potential and incorporates social acceptance, biodiversity sensitivity, and policy effectiveness into a scenario-based simulation tool.


## Key Research Papers
Two foundational papers are provided and must be thoroughly studied before work begins:

1. **Mikovits et al. (2021)** — *"A Spatially Highly Resolved Ground Mounted and Rooftop Potential Analysis for Photovoltaics in Austria"* (ISPRS Int. J. Geo-Inf.). This paper introduces the open-source spatial PV potential modelling framework for Austria using PVGIS solar radiation data, IACS agricultural land-use data, and building footprint cadastre data. It presents results across five land-use scenarios and quantifies the gap between technical potential and policy goals for 2030 and 2050.[^1]
2. **BioPV Final Report (2026)** — *"Photovoltaics, Humans and the Biosphere: A transdisciplinary approach fostering Alpine resilience"*. This report, produced from a major Austrian research project spanning five biosphere reserves, provides: (a) a multi-criteria techno-economic siting framework for ground-mounted PV integrating GIS, grid topology, and LCOE modelling; (b) empirical biodiversity data from field surveys at existing PV installations; (c) a large-scale conjoint survey experiment identifying the relative importance of land use type, biodiversity measures, visibility, and energy justice features for public acceptance; and (d) results from participatory BioPV laboratories using immersive 3D simulation games.[^2]



## Research Questions  
Your work should address the following questions:

1. What social, economic, and attitudinal factors most strongly predict residential PV adoption, and how do these vary across Austrian regions and household types?
2. How does modelled social acceptance — when incorporated as a spatial weighting factor — affect projected PV penetration rates and the geographic distribution of feasible installations in energy system scenarios?
3. What is the combined socially- and ecologically-weighted PV potential of Austria, and how does it differ from the purely technical potential computed by Mikovits et al. (2021)?
4. How do biodiversity sensitivity indicators (e.g., High Nature Value farmland, ecological conflict potential) interact spatially with areas of high technical PV potential and high social acceptance?
5. What policy instruments most effectively close the gap between demonstrated public interest and actual deployment, particularly for residential and agri-PV systems?
6. What is the marginal contribution of adding social acceptance indices and biodiversity conflict layers to the existing Mikovits et al. (2021) potential calculation, and how sensitive are the results to the weighting choices made?



## Your Task
The work is structured in four connected phases:

**Phase 1 — Literature Review on Social Acceptance of PV Adoption**  
Conduct a systematic literature review covering the key determinants of residential and community-level PV adoption. The review must cover at minimum the following dimensions:
- **Attitudinal and psychological factors:** environmental concern, climate attitudes, trust in institutions, perceived risk and benefit, social norms, activism intentions
- **Economic factors:** willingness to pay, feed-in tariff design, upfront cost barriers, energy community models, benefit-sharing mechanisms
- **Policy and regulatory factors:** planning law, spatial zoning, grid connection requirements, subsidy design, information provision
- **Social justice dimensions:** distributional justice (who benefits), procedural justice (who decides), recognition justice (whose landscape)
- **Contextual and spatial factors:** urban vs. rural differences, Alpine vs. lowland settings, tourism pressure, place attachment and landscape identity

You should consult the BioPV conjoint survey findings as an empirical anchor  and extend the review with peer-reviewed literature from journals such as *Energy Research \& Social Science*, *Applied Energy*, *Renewable and Sustainable Energy Reviews*, and *Energy Policy*. The output of Phase 1 is a structured review section (~1,500 words) that synthesises findings and identifies which factors are most evidenced for the Austrian context.[^2]

**Phase 2 — Development of a Social Acceptance Index (SAI) and Biodiversity Conflict Index (BCI)**  
Building on the literature review and the BioPV empirical results, you will develop two quantitative spatial indices:

**Social Acceptance Index (SAI):** A composite score, assignable at the municipal or grid-cell level, reflecting the likelihood of PV adoption given local social, economic, and attitudinal conditions. You should draw on:  
- The BioPV conjoint attribute weights (land use type: 35.86%, biodiversity measures: 21.65%, visibility: 19.42%, procedural justice: 12.57%, distributional justice: 10.51%) as a starting point for weighting[^2]
- Publicly available sociodemographic proxies at the municipality level (income, building age, household size, political leaning, existing PV installations)
- Willingness-to-pay estimates and adoption rate data from the literature
- Regional differentiation (Alpine biosphere reserve areas vs. Eastern Austrian plains)

**Biodiversity Conflict Index (BCI):** A spatial layer encoding ecological sensitivity, to be used as a constraint or penalisation factor in the potential calculation. Draw on:  
- The BioPV High Nature Value (HNV) farmland overlay with IACS land use data[^2]
- Protected area designations (Naturschutzgebiete, Natura-2000, Trockenrasenkatalog, Feuchtgebietsinventar)
- The Ecological Potential for Conflict (EPFC) metric developed in the BioPV project[^2]
- Relevant biodiversity literature on ground-mounted PV impacts (arthropods, bats, birds, pollinators)

Both indices should be clearly documented with a transparent weighting methodology, justified by the literature and the BioPV empirical evidence. Sensitivity to alternative weighting choices should be discussed.


**Phase 3 — Enhanced PV Potential Calculation for Austria**  
Using the spatial framework established by Mikovits et al. (2021) as your methodological baseline, you will compute an **enhanced PV potential estimate** that integrates the SAI and BCI alongside the existing technical parameters. Specifically:[^1]

- **Replicate or adapt the baseline calculation** from Mikovits et al. (2021) for at least one land-use scenario (e.g., *All Open* or *Crops \& Vegetables*), using PVGIS, IACS, and slope/altitude data as described in the paper. The open-source code is available at: https://github.com/inwe-boku/pvaustria2021
- **Apply the SAI as a deployment probability modifier**, scaling the technical potential at each spatial unit by a factor derived from the local acceptance index. This produces a *socially adjusted potential* — the share of technical potential that is realistically deployable given social conditions.
- **Apply the BCI as an exclusion and penalisation layer**, removing or downweighting high-conflict areas from the feasible deployment set. This produces a *socially and ecologically adjusted potential*.
- **Run at least three scenarios:** (a) baseline technical potential (replicating Mikovits et al.), (b) socially adjusted potential, (c) socially and ecologically adjusted potential. For each scenario, report total potential (TWh/a), spatial distribution by federal state and Alpine vs. non-Alpine regions, and the fraction of 2030 and 2050 policy targets that could be met.
- Compare your results against the Mikovits et al. findings and interpret the differences, particularly regarding which regions show the largest reduction in feasible potential once social and ecological factors are applied.

Where full GIS replication is not feasible within the project scope, a scenario-based parametric analysis using the published Mikovits et al. data at the municipal level as input, combined with your computed SAI and BCI layers, is an acceptable approach. This should be clearly justified in the methodology.


**Phase 4 — Policy Analysis and Scenario Simulation**  
Based on the model results, carry out a **policy scenario analysis** addressing the third research question. Define at least three policy scenarios that vary one or more of the following levers:

- Subsidy level or feed-in tariff design (affecting the SAI through economic factors)
- Mandatory biodiversity measures for ground-mounted PV (affecting the BCI through regulatory constraints)
- Participatory planning requirements (affecting acceptance through procedural justice)
- Agri-PV promotion (allowing simultaneous agricultural and PV use, relaxing the BCI on agricultural land)

For each policy scenario, compute the resulting change in socially and ecologically adjusted PV potential and discuss which combination of instruments most effectively closes the gap between current technical potential and realistic deployment. Explicitly link your findings to the BioPV stakeholder preferences (e.g., the strong preference for siting on sealed and pre-impacted land; the positive valuation of biodiversity measures; the preference for citizen participation with benefit sharing).[^2]



## Deliverables  
You are expected to submit the following:
1. **Written Report** — A structured scientific report of approximately 6,000–8,000 words covering:
    - Introduction and motivation, including Austria's 2030 renewable energy context
    - Literature review (Phase 1 output): social, economic, and attitudinal drivers of PV adoption
    - Methodology: construction of the SAI and BCI, adaptation of the Mikovits et al. framework, scenario definitions
    - Results: spatial maps and tables comparing baseline, socially adjusted, and socially-ecologically adjusted potential across scenarios; policy scenario outcomes
    - Discussion: interpretation of results, comparison with BioPV findings and Mikovits et al. baseline, limitations, and sensitivity of the index weightings
    - Conclusion: key findings, policy recommendations, and directions for further research
2. **Model and Code** — Documented scripts or a reproducible analysis pipeline implementing the SAI/BCI construction and the adjusted potential calculations. These should be submitted in a version-controlled repository (GitHub) and designed so the analysis can be reproduced.
3. **Presentation** — A 20-minute oral presentation of your findings, including at minimum: one map showing the spatial distribution of the socially and ecologically adjusted PV potential, one comparison table of scenario results against policy targets, and a concise set of policy recommendations.



## Recommended Starting Points  
- Read both provided papers in full before beginning Phase 1. Pay particular attention to the Mikovits et al. methodology section (Section 2) and the BioPV WP2, WP3, and WP4 results
- Explore the open-source PV potential model code (https://github.com/inwe-boku/pvaustria2021) to understand what inputs and outputs are available for reuse or adaptation
- Access the open Austrian data sources referenced in both papers: PVGIS (https://ec.europa.eu/jrc/en/PVGIS), IACS/INVEKOS land use data (https://data.gv.at), the Austrian digital terrain model, and the Umweltbundesamt protected area datasets
- For the literature review, begin with the references cited in both provided papers — they provide a well-curated entry point into the international literature on PV acceptance, land-use conflict, biodiversity impacts, and energy justice
- For the SAI construction, treat the BioPV conjoint utility weights as an empirically grounded starting point and document clearly how you adapt or extend them
