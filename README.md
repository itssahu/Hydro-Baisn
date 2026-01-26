# Probabilistic Flood Catastrophe Risk Modeling for Urban Wastewater Infrastructure under Climate Extremes
Musi River Sub-Basin, Hyderabad, India

## Overview

Urban wastewater infrastructure is highly vulnerable to flooding, yet conventional flood assessments and climate risk studies rarely quantify probabilistic tail risk, multi-event losses, or facility-level systemic vulnerability in a unified framework.

This repository implements a research-grade, end-to-end probabilistic flood catastrophe risk model for urban wastewater infrastructure in the Musi River sub-basin (Hyderabad, India). The framework integrates:

    Observed and reanalysis rainfall data

    Bias correction and Extreme Value Theory (EVT)

    Monte Carlo catastrophe loss simulation

    Deep generative tail modeling using Variational Autoencoders (VAE)

    Facility-level hazard, vulnerability, and loss modeling

    Social impact (casualty) estimation

    Composite Climate Risk Index incorporating hazard, exposure, and adaptive capacity

The result is a system that simultaneously quantifies:

    Financial tail risk (insurance / reinsurance perspective)

    Systemic climate vulnerability (resilience and sustainability perspective)
    Study Area & Assets

Region: Musi River Sub-Basin, Telangana, India
Urban Context: Hyderabad metropolitan region
Assets: 16 wastewater-related facilities

Including:

Wastewater treatment plants

Landfills

Transfer stations

Recycling facilities

Facilities are modeled as point assets and enriched with:

Elevation, slope, and drainage proximity

Population exposure and density

Facility typology and service criticality

(Add Figure: Basin map with rivers and facility locations)

Conceptual Framework

This project follows a catastrophe modeling paradigm, not a deterministic flood mapping workflow:

Rainfall extremes → Flood hazard → Infrastructure damage → Losses → Social impacts → Climate vulnerability

The full pipeline is illustrated below.

(Add Figure: End-to-end modeling framework schematic)

Data Sources
Hydro-Meteorological

IMD daily gridded rainfall (0.25°) — observational reference

ERA5 reanalysis daily rainfall — continuous forcing dataset

Geospatial & Physical

HydroBASINS basin boundary

HydroRIVERS drainage network

Digital Elevation Model (DEM) derivatives

Infrastructure & Exposure

OpenStreetMap wastewater facilities

Population density & exposure metrics

Rainfall Bias Correction

ERA5 rainfall is bias-corrected against IMD observations using non-parametric quantile mapping:

R_bc = F_IMD^{-1}( F_ERA5(R) )


This approach preserves:

Mean rainfall

Variability

Extreme quantiles

Negative rainfall values are clipped to zero.

(Add Figure: ERA5 vs IMD vs bias-corrected rainfall distributions)

Extreme Rainfall Modeling (EVT)
Annual Maximum Series (AMS)

Bias-corrected daily rainfall is aggregated to annual maxima:

R_y = max( R_y,1 , … , R_y,365 )

Generalized Extreme Value (GEV) Model

The AMS is modeled using the GEV distribution:

G(x) = exp{ - [1 + ξ (x − μ) / σ] ^ (−1/ξ) }


Parameters estimated via maximum likelihood:

μ : location

σ : scale

ξ : shape

Return levels are computed as:

R_T = G^{-1}(1 − 1/T)


The 100-year rainfall is used as a normalization anchor throughout the model.

(Add Figure: EVT diagnostic plots and return level curve)

Flood Hazard Modeling
Event-Level Hazard

For a rainfall event with intensity R_e:

H_e = min( R_e / R_100 , 1 )

Facility Flood Susceptibility (Bio-Physical)

A static Flood Susceptibility / Total Wetness Index is constructed from:

Distance to drainage

Elevation percentile

Slope percentile

H_i = 0.40(1 − d_i*) + 0.35(1 − p_elev,i) + 0.25(1 − p_slope,i)

Facility Hazard Intensity
H_i,e = H_e × H_i


This ensures extreme rainfall translates to high hazard only where terrain permits flooding.

(Add Figure: Flood susceptibility spatial map)

Damage & Vulnerability Modeling

Infrastructure damage is modeled as a non-linear function of hazard intensity:

D_i,e = min( H_i,e ^ α_i , 1 )


Facility-specific vulnerability exponents α_i represent differing robustness.

(Add Figure: Vulnerability curves by facility type)

Asset Values & Loss Modeling

Synthetic but industry-realistic asset values are assigned by facility type.

Event loss:

L_i,e = V_i × D_i,e


Portfolio loss:

L_e = Σ_i L_i,e

Monte Carlo Catastrophe Simulation
Event Frequency

Annual flood events follow a Poisson process:

N_y ~ Poisson(λ),   λ = 0.4

Annual Loss Aggregation
L_y = Σ_e=1..N_y  Σ_i L_i,e


A total of 10,000 simulated years are generated.

Risk Metrics

From simulated losses, standard catastrophe metrics are derived:

OEP — single-event dominance

AEP — annual aggregated loss

PML — tail loss benchmarks

AAL — long-term expected loss

(Add Figure: EP curves and loss distributions)

Social Impact & Casualty Modeling

Casualties are modeled as a function of hazard intensity and population exposure:

f(h) = min( c h^γ , 0.2 )
C_i,e = f(H_i,e) × P_i


Social risk is summarized using Expected Annual Casualties (EAC).

(Add Figure: Social EP curve)

Deep Generative Tail Modeling (VAE)
Motivation

EVT provides parametric tail behavior but may under-represent complex tail structure. A Variational Autoencoder (VAE) is introduced to enrich tail sampling.

Tail Extraction

Rainfall exceedances above the 95th percentile

Log-transformed before training

VAE Training

The VAE maximizes the Evidence Lower Bound (ELBO):

L = E_q(z|x)[ log p(x|z) ] − KL( q(z|x) || N(0,1) )

Tail Injection

During Monte Carlo simulation:

EVT governs most events

VAE-generated rainfall replaces EVT tails with probability:

P_tail = 0.05


This produces heavier, data-driven loss tails.

(Add Figure: EVT vs VAE-injected loss tails)

Socio-Economic Exposure Index
E_i = Normalize( P_i × S_i )


Where:

P_i = population exposure

S_i = service criticality

(Add Figure: Socio-economic exposure map)

Adaptive Capacity Index

Adaptive capacity integrates:

Institutional capacity

Physical robustness

Accessibility

Population pressure

C_i = 0.35 I_i + 0.30 R_i + 0.20 A_i + 0.15 (1 − P_i)


(Add Figure: Adaptive capacity spatial map)

Composite Climate Risk Index (CCRI)
CCRI_i = H_i × E_i × (1 − C_i)


Facilities are classified as:

Low

Moderate

High

Critical

(Add Figure: Composite climate risk map)

Financial Tail Risk vs Composite Climate Risk

This project explicitly distinguishes:

Financial Tail Risk

EVT + Monte Carlo losses

Capital adequacy and insurance relevance

Composite Climate Risk

Systemic vulnerability

Population exposure and coping capacity

These two perspectives do not always align and must be interpreted jointly.

(Add Figure: Side-by-side EVT/MC tail loss vs composite climate risk)

Applications

Catastrophe & reinsurance modeling

Climate risk & ESG disclosure

Urban resilience planning

Infrastructure investment prioritization

Sustainability & sanitation risk assessment

Limitations

No hydrodynamic flood routing

Stylized vulnerability & casualty parameters

Static population exposure

No explicit climate scenario forcing

Future Extensions

Non-stationary climate-conditioned EVT

Dynamic exposure & land-use change

Infrastructure network interdependencies

Compound hazard modeling

Key Contribution

This repository demonstrates how extreme rainfall physics, probabilistic catastrophe modeling, deep generative AI, and climate vulnerability assessment can be unified into a single, transparent, decision-ready framework for urban infrastructure under climate extremes.

Author: Sandeep Sahu
Focus: Climate Risk • Catastrophe Modeling • Infrastructure Resilience

<img width="1451" height="1183" alt="image" src="https://github.com/user-attachments/assets/1049f97e-b0ca-42a9-9c2e-c00225c679d7" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/d12988ce-cef8-407c-a7fb-d586ebe9af6b" />
<img width="890" height="590" alt="image" src="https://github.com/user-attachments/assets/748890cc-261e-4296-93b5-5d6db82b3d32" />
<img width="1017" height="675" alt="image" src="https://github.com/user-attachments/assets/2e7b69db-50f9-4a67-8835-d533c730f0fe" />
<img width="890" height="590" alt="image" src="https://github.com/user-attachments/assets/8433b1e3-e331-4a2a-9934-3d26363c346c" />
<img width="1033" height="675" alt="image" src="https://github.com/user-attachments/assets/0dd87593-e65f-4fb4-903e-22b179d3a749" />
<img width="1042" height="675" alt="image" src="https://github.com/user-attachments/assets/dfc4e270-06a7-4897-acaa-65d104dabb0b" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/40f0a3e3-cb6e-45cb-8047-b753aece109f" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/55537070-b2ce-4393-bfce-1c3e9e5d690b" />
<img width="1020" height="678" alt="image" src="https://github.com/user-attachments/assets/d24fb621-8933-4bab-9b19-c445ef078214" />
<img width="1552" height="841" alt="image" src="https://github.com/user-attachments/assets/1f27b3b7-74c6-4856-b807-0fbff23bf82a" />

