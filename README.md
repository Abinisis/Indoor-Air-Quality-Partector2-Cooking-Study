# 🔬 UFP-Cooking-Emissions-Analysis

> Measurement and analysis of ultrafine particle (UFP) emissions during indoor cooking activities using the **Partector 2** nanoparticle monitor — comparing gas vs. electric stove emissions under open and closed ventilation conditions.

**University of Cassino and Southern Lazio**  
Department of Civil and Mechanical Engineering  
MSc in Civil and Environmental Engineering (LM-23)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Findings](#key-findings)
- [Experimental Design](#experimental-design)
- [Instrumentation](#instrumentation)
- [Repository Structure](#repository-structure)
- [Data & Analysis](#data--analysis)
- [Results Summary](#results-summary)
- [Authors](#authors)
- [References](#references)

---

## Overview

Indoor air pollution from cooking is one of the most underestimated health risks in residential environments. This study investigates **ultrafine particle (UFP)** emissions generated during potato frying using gas and electric stoves under controlled ventilation conditions.

**Lung-Deposited Surface Area (LDSA)** concentrations were measured in real time using the **Partector 2** nanoparticle monitor — a portable, high-sensitivity instrument designed for continuous aerosol monitoring.

Four experimental scenarios were conducted to evaluate the combined effects of:
- **Stove type** (gas vs. electric)
- **Ventilation condition** (open vs. closed kitchen)

---

## Key Findings

| Finding | Result |
|---|---|
| Gas stove emission factor | ~6.47 × 10¹² particles/h |
| Electric stove emission factor | ~1.98 × 10¹¹ particles/h |
| Gas vs. Electric ratio | **~33× higher emissions from gas** |
| Ventilation impact | Open window significantly reduced peak LDSA and accelerated decay |
| Closed kitchen risk | Sharp LDSA spikes with slow post-cooking decay |

> ⚠️ More than **90% of particles** emitted during frying fall within the ultrafine size range (<100 nm) — small enough to penetrate deep into lung tissue and enter the bloodstream.

---

## Experimental Design

All four experiments used a standardized frying protocol:
- **Food:** 79 g potato strips (15 strips, uniform size)
- **Oil:** Sunflower oil
- **Measurement:** Continuous LDSA recording at 6-second intervals

| ID | Stove | Ventilation | Room Volume |
|---|---|---|---|
| Exp. 1 | Electric | Closed (insufficient) | 78.1 m³ |
| Exp. 2 | Electric | Open (sufficient) | 78.1 m³ |
| Exp. 3 | Gas | Closed (insufficient) | 42.0 m³ |
| Exp. 4 | Gas | Open (sufficient) | 42.0 m³ |

### Emission Factor Calculation

Average indoor particle generation rate was estimated using a **mass balance approach**:

```
dC(t)/dt = Qₛ / V − (AER + k) · C(t)
```

At quasi-steady-state:

```
EF = Qₛ = C_avg × (AER + k) × V
```

**Concentration decay** was modeled as:

```
C(t) = C₀ · exp[−(AER + k) · t]
```

Air Exchange Rate (AER) = **0.5 h⁻¹** (standard reference for naturally ventilated residential kitchen, consistent with Buonanno et al., 2009).

---

## Instrumentation

**Naneos Partector 2** — Aerosol and Nanoparticle Monitor

| Specification | Value |
|---|---|
| Serial Number | 8477 |
| Hardware Revision | 3.2 |
| Firmware Revision | 367 |
| Calibration Factor | 5.75 |
| Last Calibration | April 2, 2025 |
| Detection Range | 10–300 nm |
| Max Concentration | 10⁶ particles/cm³ |
| Flow Rate | 500 ml/min |
| Temporal Resolution | 1 second |
| LDSA Accuracy | ±30% or ±3 µm²/cm³ |

**Primary metric — LDSA (Lung-Deposited Surface Area):**  
Represents the surface area of particles deposited in the alveolar region of the lungs. A more physiologically relevant exposure metric than mass-based measures like PM₂.₅.

---

## Repository Structure

```
UFP-Cooking-Emissions-Analysis/
│
├── data/
│   ├── raw/                    # Raw Partector 2 CSV exports
│   │   ├── exp1_electric_closed.csv
│   │   ├── exp2_electric_open.csv
│   │   ├── exp3_gas_closed.csv
│   │   └── exp4_gas_open.csv
│   └── processed/              # Cleaned and analyzed datasets
│
├── analysis/
│   ├── emission_factor_calc.xlsx   # Emission rate calculations
│   ├── decay_regression.xlsx       # Log-linear decay analysis
│   └── summary_statistics.xlsx     # Cross-experiment comparison
│
├── figures/
│   ├── ldsa_temporal_electric.png  # LDSA trend - electric stove
│   ├── ldsa_decay_electric.png     # Decay curve - electric stove
│   ├── ldsa_temporal_gas.png       # LDSA trend - gas stove
│   └── ldsa_decay_gas.png          # Decay curve - gas stove
│
├── report/
│   └── Report_ST_K.docx            # Full technical report
│
└── README.md
```

---

## Data & Analysis

Raw data was exported from the Partector 2 as CSV files and processed in **Microsoft Excel**. Key parameters derived for each experiment:

- Background concentration (average of first 10 pre-cooking readings)
- Peak LDSA concentration during active frying
- Average concentration during frying period (C_avg)
- Post-cooking decay slope — (AER + k) from linear regression of ln(C/C₀) vs. time
- Particle deposition rate k
- Emission factor (EF)

---

## Results Summary

### Electric Stove
- **Closed kitchen:** Background LDSA ~240 µm²/cm³ → peak >430 µm²/cm³ → stabilized ~365 µm²/cm³ post-cooking
- **Open kitchen:** Background ~75 µm²/cm³ → modest peak ~155 µm²/cm³ → rapid return to baseline

### Gas Stove
- **Closed kitchen:** LDSA peaked at **several thousand µm²/cm³** — more than 10× higher than open condition
- **Open kitchen:** LDSA remained low (<few hundred µm²/cm³) throughout

### Stove Comparison
The gas stove produced **~33× more particles** than the electric stove. This aligns with Buonanno et al. (2009), who reported that gas stoves emit significantly higher UFP concentrations due to direct combustion by-products in addition to thermal cooking aerosols.

---

## Authors

| Name | Institution |
|---|---|
| Abenezer Sisay Dibisa | University of Cassino and Southern Lazio |
| Eleni Woldeselassie Gebretsadik | University of Cassino and Southern Lazio |
| Kalkidan Amare Mulu | University of Cassino and Southern Lazio |
| Siyane Tariku Zewude | University of Cassino and Southern Lazio |

**Supervisor:** Prof. Giorgio Buonanno — Department of Civil and Mechanical Engineering

**Date:** April–May 2026

---

## References

- Buonanno, G., Morawska, L., Stabile, L. (2009). Particle emission factors during cooking activities. *Atmospheric Environment*, 43, 3235–3242.
- Bezantakos, S. et al. (2024). Performance of the Naneos Partector 2 at reduced temperature and pressure conditions. *Aerosol Science and Technology*, 58, 584–593.
- Lachowicz, J.I. et al. (2022). Cooking Particulate Matter: A Systematic Review on Nanoparticle Exposure. *Atmosphere*, 14, 12.
- Todea, A.M. et al. (2017). Inter-comparison of personal monitors for nanoparticle exposure. *Science of The Total Environment*, 605–606, 929–945.
- Xiang, J. et al. (2021). Characterization of cooking-related ultrafine particles in a US residence. *Science of The Total Environment*, 798, 149236.
- Pikmann, J. et al. (2024). Particulate emissions from cooking: emission factors and emission dynamics. *Atmos. Chem. Phys.*, 24, 12295–12321.

---

*This study was conducted as part of an MSc thesis research project on indoor air quality at the University of Cassino and Southern Lazio, Italy.*
