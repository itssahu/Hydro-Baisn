# Probabilistic Flood Catastrophe Risk Modeling of Urban Wastewater Infrastructure Integrating Deep Generative Tail Amplification and Systemic Climate Vulnerability

Musi River Sub-Basin, Hyderabad, India


<img width="1451" height="1183" alt="image" src="https://github.com/user-attachments/assets/1049f97e-b0ca-42a9-9c2e-c00225c679d7" />

Figure . Basin-scale hydro-terrain, exposure, and wastewater infrastructure context for the Musi sub-basin.
Elevation and slope maps show a low-relief floodplain aligned with the Musi River, indicating areas prone to flood accumulation and slow drainage. The river network highlights strong drainage convergence through the Hyderabad urban corridor. Population exposure is highly concentrated in this zone. Wastewater facilities, including treatment plants, landfills, and transfer stations (shown with different symbols) are located along these flood-prone and high-exposure areas. This static basin-scale context defines the physical and socio-economic setting used to condition all subsequent flood hazard, loss, and tail-risk modeling.

## Systemic Climate Vulnerability Assessment

<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/40f0a3e3-cb6e-45cb-8047-b753aece109f" />

Figure. Bio-physical flood susceptibility (total wetness) of wastewater facilities in the Musi sub-basin, derived from a weighted combination of drainage proximity, elevation percentile, and slope percentile. High susceptibility clusters along the Musi river and low-lying floodplain zones, highlighting terrain-controlled flood accumulation potential independent of event magnitude. Symbol size denotes population exposure, shown separately to preserve a clear distinction between physical hazard propensity and downstream impact.

<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/55537070-b2ce-4393-bfce-1c3e9e5d690b" />

Figure. Socio-economic exposure of wastewater facilities in the Musi sub-basin, combining population exposure and facility service criticality. High exposure values are spatially concentrated around a limited set of system-critical assets serving dense populations, while peripheral facilities exhibit low exposure despite physical presence. Symbol size represents normalized population exposure, shown separately to distinguish societal dependency from infrastructure importance.

<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/d24fb621-8933-4bab-9b19-c445ef078214" />

Figure. Adaptive capacity of wastewater facilities in the Musi sub-basin, representing relative coping and recovery potential derived from institutional strength, physical robustness, accessibility, and population pressure. While some facilities exhibit high adaptive capacity, several high-exposure assets along the Musi corridor show limited coping potential, highlighting spatial mismatches between societal dependence and resilience. Symbol size denotes population exposure.

<img width="1500" height="995" alt="image" src="https://github.com/user-attachments/assets/70a57cd6-2c7e-43d8-97a2-240dd73504c1" />

Figure. Composite Climate Risk Index of wastewater infrastructure in the Musi sub-basin. Point color represents the integrated risk metric defined as Hazard × Exposure × (1 − Adaptive Capacity), while symbol size denotes population exposure. High-risk facilities cluster along the Musi River flood corridor, where terrain-driven flood susceptibility coincides with dense population exposure and limited adaptive capacity, highlighting priority assets for resilience and risk mitigation.

### Key Insights

#### Risk concentrates along the Musi River corridor
Facilities located directly on or immediately adjacent to the Musi River exhibit the highest composite climate risk, reflecting the compounding effect of flood susceptibility and exposure despite varying adaptive capacities.

#### High risk is not driven by hazard alone
Several facilities with moderate flood susceptibility still emerge as high-risk because population exposure and service criticality amplify consequences, confirming that composite risk is a socio-physical construct, not purely hydrological.

#### Adaptive capacity meaningfully differentiates assets
Facilities in similar hydro-terrain settings show markedly different risk levels, indicating that adaptive capacity acts as a dampening factor, preventing some high-hazard locations from becoming critical-risk assets.

#### Large-population assets dominate risk prioritization
Larger symbols (high population exposure) that also show elevated composite risk identify systemically important infrastructure, where failure would propagate impacts well beyond the facility footprint.

## Probabilistic Flood Catastrophe Risk Modeling and Deep Generative Tail Amplification
<img width="890" height="590" alt="image" src="https://github.com/user-attachments/assets/748890cc-261e-4296-93b5-5d6db82b3d32" />

Figure. Annual Exceedance Probability (EP) curves for flood-induced losses in the Musi Basin derived from EVT-only return levels (black), Monte Carlo catastrophe simulation (red), and EVT with VAE-based tail amplification (blue).
The EVT-only curve is defined by a small number of return levels and spans a limited loss range, representing single-event severity without annual loss aggregation; it lies above the simulated curves and does not resolve the extreme low-probability tail. Monte Carlo simulation extends EVT into a full annual loss distribution by sampling event frequency over 10,000 synthetic years, producing a smoother EP curve and substantially higher loss estimates at low exceedance probabilities. However, the Monte Carlo tail remains constrained by the parametric EVT structure used to generate extreme rainfall. The VAE-amplified curve departs from the Monte Carlo curve only in the lowest EP region (EP < 10⁻³), where losses increase further, indicating heavier and more variable tail behavior. This separation shows that deep generative tail sampling does not alter typical or moderate risk but materially affects rare, high-consequence losses that dominate capital adequacy, stress testing, and reinsurance attachment decisions.

Monte Carlo improves convergence of EVT-based loss aggregation but remains confined to the parametric tail learned from limited extremes. VAE-based tail amplification introduces a learned latent representation of extreme loss structure, enabling controlled exploration of rare, compound tail realizations beyond EVT support. This results in divergence only at the lowest exceedance probabilities, where tail uncertainty, not mean behavior, dominates risk, making the VAE essential for credible extreme tail risk estimation.

<img width="1017" height="675" alt="image" src="https://github.com/user-attachments/assets/2e7b69db-50f9-4a67-8835-d533c730f0fe" />

Figure. Facility-level incremental flood tail loss uplift introduced by VAE-based tail enrichment relative to Monte Carlo simulation. VAE amplification is spatially concentrated along the Musi river corridor, indicating that deep generative modeling captures rare, spatially correlated extreme flood configurations that are not fully represented by stochastic Monte Carlo aggregation.

## Climate stress testing 

<img width="890" height="590" alt="image" src="https://github.com/user-attachments/assets/8433b1e3-e331-4a2a-9934-3d26363c346c" />

Figure. Climate-conditioned flood loss exceedance probability (EP) curves derived from a VAE-amplified baseline climate and two tail stress scenarios: S1 (+10% tail amplification) and S2 (+25% tail amplification). The curves coincide across moderate exceedance probabilities, indicating unchanged loss behavior under typical conditions. Divergence appears only in the lowest exceedance probability range (EP < 10⁻³), where progressively stronger tail amplification leads to higher extreme losses. This pattern reflects non-stationary tail thickening under climate stress, affecting only rare, high-consequence events without altering event frequency or mid-range risk.

These results show that climate stress manifests primarily through amplification of extreme loss tails rather than shifts in typical risk, implying that conventional metrics (AAL, mid-range EPs) understate climate-driven vulnerability. Capital adequacy, reinsurance attachment, and solvency assessments are therefore governed by tail-sensitive modeling, where VAE-based stress testing becomes important to capture non-stationary, high-impact flood losses. Here, S1 and S2 represent moderate and severe climate stress states, implemented as controlled increases in the generative tail severity of the rainfall–loss distribution, mimicking progressively intensified future extreme rainfall conditions rather than changes in event frequency.

<img width="1033" height="675" alt="image" src="https://github.com/user-attachments/assets/0dd87593-e65f-4fb4-903e-22b179d3a749" />
<img width="1042" height="675" alt="image" src="https://github.com/user-attachments/assets/dfc4e270-06a7-4897-acaa-65d104dabb0b" />

Figure. Facility-level climate-conditioned flood tail loss uplift under moderate (S1, +10%) and severe (S2, +25%) loss stress scenarios for a 100-year flood event. While the spatial pattern of tail-sensitive facilities remains consistent, S2 produces non-linear amplification in a subset of assets, indicating that climate stress primarily intensifies extreme loss severity rather than uniformly increasing risk. This highlights that climate-driven vulnerability is concentrated in structurally tail-sensitive facilities, which dominate portfolio losses under severe stress.

Together, these climate-conditioned EP curves and facility-level tail uplift results demonstrate that flood-related climate stress operates primarily through selective amplification of extreme loss tails rather than broad shifts in risk across the portfolio. At the portfolio scale, moderate losses and mid-range exceedance probabilities remain stable across the baseline, S1, and S2 scenarios, while divergence emerges only at very low exceedance probabilities, confirming that climate stress thickens the loss tail without altering event frequency or typical outcomes. At the facility level, this tail amplification is highly heterogeneous, with a small subset of structurally sensitive assets exhibiting disproportionate loss escalation under severe stress (S2), thereby dominating portfolio tail risk. From a stress-testing perspective, these results imply that climate vulnerability is not revealed through average losses or standard return periods, but through tail-focused scenarios that expose nonlinear loss escalation in critical assets, underscoring the importance of VAE-based tail stress testing to inform capital adequacy, reinsurance attachment, and resilience planning under future climate extremes.

## Integrated Climate–Catastrophe Risk Interpretation

<img width="1552" height="841" alt="image" src="https://github.com/user-attachments/assets/1f27b3b7-74c6-4856-b807-0fbff23bf82a" />
Figure X. VAE-Amplified Extreme Flood Tail Risk versus Composite Climate Risk for Urban Wastewater Infrastructure in the Musi Sub-Basin (Hyderabad, India).

The left panel shows facility-level extreme flood tail losses (EP < 2%) derived from an EVT-conditioned Monte Carlo catastrophe model with VAE-based tail amplification, highlighting spatial concentration of rare but catastrophic financial risk. The right panel depicts a Composite Climate Risk Index integrating static flood hazard susceptibility, socio-economic exposure, and adaptive capacity, representing long-term systemic vulnerability. Symbol size indicates normalized population exposure.

Results reveal a systematic spatial divergence between assets dominating probabilistic financial tail risk and those driving composite climate vulnerability, underscoring the necessity of jointly modeling extreme loss behavior and socio-environmental resilience when assessing climate risk to urban infrastructure.

## Implications for Infrastructure Risk Assessment
The comparison between extreme flood tail risk and composite climate risk highlights the necessity of multi-objective prioritization. 

Facilities can be broadly categorized into four functional risk classes:

#### Financially critical assets
which dominate tail losses and drive capital stress.

#### Systemically critical assets
which pose high societal and service disruption risk despite moderate financial losses.

#### Dual-risk assets
which score highly on both dimensions and represent “do-not-fail” infrastructure.

#### Low-priority assets 
which are relatively stable under current hazard and exposure conditions.

Crucially, these categories imply different intervention strategies. Capital-intensive flood mitigation investments and risk transfer mechanisms (e.g., insurance or reinsurance) are most suitable for assets dominated by extreme tail losses, whereas systemically vulnerable facilities benefit more from governance improvements, redundancy planning, and targeted enhancement of adaptive capacity. The framework therefore moves beyond generic “high-risk” labels and supports actionable, asset-specific decision pathways.

## Applications

#### Climate stress testing and capital adequacy
Tail-sensitive loss modeling for regulatory stress tests, solvency assessment, and infrastructure financing.

####  Reinsurance and risk transfer design
Inform attachment points, tail layers, and parametric triggers using VAE-amplified extreme loss distributions.

#### Urban resilience and adaptation planning
Identify assets where governance reform, redundancy, or adaptive capacity investments outperform structural mitigation.

#### Portfolio prioritization under climate uncertainty
Support asset-level decision-making by separating financial tail risk from systemic climate vulnerability

## Limitations 

#### Latent tail learning is univariate
The VAE models basin-mean rainfall tail behavior; spatial rainfall structure and storm morphology are not explicitly learned in latent space.

#### Implicit climate conditioning
Climate stress is represented via tail amplification rather than explicitly conditioning the generative model on physical climate drivers (e.g., SSTs, circulation indices).

#### Limited epistemic uncertainty separation
Parameter uncertainty (EVT, damage functions) and generative uncertainty (VAE latent sampling) are not fully disentangled.

#### Climate stress representation
Climate change is represented through controlled tail amplification rather than fully transient climate model projections, prioritizing stress-testing realism over long-term scenario forecasting.

## Future Scope — Climate AI & Advanced Modeling

#### Conditioned generative models for climate drivers
Extend the VAE to a conditional VAE or diffusion model conditioned on large-scale climate variables (e.g., ENSO, monsoon indices, SST anomalies).

#### Spatio-temporal generative rainfall modeling
Replace basin-mean rainfall with spatio-temporal generative models (ConvVAE, latent diffusion) to capture storm structure and spatial dependence.

#### Graph-based infrastructure risk propagation
Incorporate graph neural networks to model cascading failures across interconnected wastewater and urban infrastructure networks.

#### Joint hazard–loss generative modeling
Develop end-to-end generative models that directly learn the distribution of annual losses, integrating hazard generation, exposure interaction, and damage response.
