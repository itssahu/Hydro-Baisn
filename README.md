# Probabilistic Flood Catastrophe Risk Modeling for Urban Wastewater Infrastructure under Climate Extremes
Musi River Sub-Basin, Hyderabad, India


<img width="1451" height="1183" alt="image" src="https://github.com/user-attachments/assets/1049f97e-b0ca-42a9-9c2e-c00225c679d7" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/d12988ce-cef8-407c-a7fb-d586ebe9af6b" />
<img width="890" height="590" alt="image" src="https://github.com/user-attachments/assets/748890cc-261e-4296-93b5-5d6db82b3d32" />
Figure. Annual Exceedance Probability (EP) curves for flood-induced losses in the Musi Basin derived from EVT-only return levels (black), Monte Carlo catastrophe simulation (red), and EVT with VAE-based tail amplification (blue).
The EVT-only curve is defined by a small number of return levels and spans a limited loss range, representing single-event severity without annual loss aggregation; it lies above the simulated curves and does not resolve the extreme low-probability tail. Monte Carlo simulation extends EVT into a full annual loss distribution by sampling event frequency over 10,000 synthetic years, producing a smoother EP curve and substantially higher loss estimates at low exceedance probabilities. However, the Monte Carlo tail remains constrained by the parametric EVT structure used to generate extreme rainfall. The VAE-amplified curve departs from the Monte Carlo curve only in the lowest EP region (EP < 10⁻³), where losses increase further, indicating heavier and more variable tail behavior. This separation shows that deep generative tail sampling does not alter typical or moderate risk but materially affects rare, high-consequence losses that dominate capital adequacy, stress testing, and reinsurance attachment decisions.

Monte Carlo improves convergence of EVT-based loss aggregation but remains confined to the parametric tail learned from limited extremes. VAE-based tail amplification introduces a learned latent representation of extreme loss structure, enabling controlled exploration of rare, compound tail realizations beyond EVT support. This results in divergence only at the lowest exceedance probabilities, where tail uncertainty, not mean behavior, dominates risk, making the VAE essential for credible extreme tail risk estimation.

<img width="1017" height="675" alt="image" src="https://github.com/user-attachments/assets/2e7b69db-50f9-4a67-8835-d533c730f0fe" />

Figure. Facility-level incremental flood tail loss uplift introduced by VAE-based tail enrichment relative to Monte Carlo simulation. VAE amplification is spatially concentrated along the Musi river corridor, indicating that deep generative modeling captures rare, spatially correlated extreme flood configurations that are not fully represented by stochastic Monte Carlo aggregation.

<img width="890" height="590" alt="image" src="https://github.com/user-attachments/assets/8433b1e3-e331-4a2a-9934-3d26363c346c" />

Figure. Climate-conditioned flood loss exceedance probability (EP) curves derived from a VAE-amplified baseline climate and two tail stress scenarios: S1 (+10% tail amplification) and S2 (+25% tail amplification). The curves coincide across moderate exceedance probabilities, indicating unchanged loss behavior under typical conditions. Divergence appears only in the lowest exceedance probability range (EP < 10⁻³), where progressively stronger tail amplification leads to higher extreme losses. This pattern reflects non-stationary tail thickening under climate stress, affecting only rare, high-consequence events without altering event frequency or mid-range risk.

<img width="1033" height="675" alt="image" src="https://github.com/user-attachments/assets/0dd87593-e65f-4fb4-903e-22b179d3a749" />
<img width="1042" height="675" alt="image" src="https://github.com/user-attachments/assets/dfc4e270-06a7-4897-acaa-65d104dabb0b" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/40f0a3e3-cb6e-45cb-8047-b753aece109f" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/55537070-b2ce-4393-bfce-1c3e9e5d690b" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/d24fb621-8933-4bab-9b19-c445ef078214" />
<img width="1552" height="841" alt="image" src="https://github.com/user-attachments/assets/1f27b3b7-74c6-4856-b807-0fbff23bf82a" />
Figure X. VAE-Amplified Extreme Flood Tail Risk versus Composite Climate Risk for Urban Wastewater Infrastructure in the Musi Sub-Basin (Hyderabad, India).

The left panel shows facility-level extreme flood tail losses (EP < 2%) derived from an EVT-conditioned Monte Carlo catastrophe model with VAE-based tail amplification, highlighting spatial concentration of rare but catastrophic financial risk. The right panel depicts a Composite Climate Risk Index integrating static flood hazard susceptibility, socio-economic exposure, and adaptive capacity, representing long-term systemic vulnerability. Symbol size indicates normalized population exposure.

Results reveal a systematic spatial divergence between assets dominating probabilistic financial tail risk and those driving composite climate vulnerability, underscoring the necessity of jointly modeling extreme loss behavior and socio-environmental resilience when assessing climate risk to urban infrastructure.

## Implications for Infrastructure Risk Assessment
The comparison between extreme flood tail risk and composite climate risk highlights the necessity of multi-objective prioritization. 

Facilities can be broadly categorized into four functional risk classes:

Financially critical assets, which dominate tail losses and drive capital stress.

Systemically critical assets, which pose high societal and service disruption risk despite moderate financial losses.

Dual-risk assets, which score highly on both dimensions and represent “do-not-fail” infrastructure.

Low-priority assets, which are relatively stable under current hazard and exposure conditions.

Crucially, these categories imply different intervention strategies. Structural flood defenses and insurance mechanisms may be appropriate for tail-loss-dominant assets, whereas governance reforms, redundancy planning, and adaptive capacity enhancement are more effective for systemically vulnerable facilities. The framework therefore moves beyond generic “high-risk” labels and supports actionable, asset-specific decision pathways.

This framework enables asset-specific prioritization by explicitly separating extreme financial tail risk from long-term systemic climate vulnerability, providing a unified yet decision-targeted view of climate risk.
