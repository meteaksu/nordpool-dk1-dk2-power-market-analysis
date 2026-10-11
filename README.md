# Nord Pool DK1/DK2 Power Market Analysis & Wind Intermittency Modeling

##  Executive Summary
This energy trading analysis project investigates the impact of wind power generation intermittency on Day-Ahead electricity prices and cross-zonal location spreads across Danish bidding zones (**DK1** and **DK2**) for 2025. 

By synchronizing 5-minute real-time wind telemetry with hourly spot market data from Energi Data Service, the study quantifies the **Merit Order Effect** ($r = -0.46$) and evaluates spatial arbitrage opportunities driven by cross-border grid congestion.

---

## Tech Stack & Data Architecture
* **Core Stack:** Python (`pandas`, `numpy`, `matplotlib`)
* **Time Alignment:** UTC-based timestamp normalization (eliminating Daylight Saving Time duplicates)
* **Market Telemetry:** Energi Data Service (Official Danish TSO / Energinet open data portal)
* **Bidding Zones:** Denmark West (DK1 - Continental/Wind Heavy) & Denmark East (DK2 - Zealand/Demand Heavy)

---

## Key Findings & Market Dynamics
* **Merit Order Effect ($r = -0.461$):** Strong inverse correlation between DK1 wind generation infeed and spot prices. High wind output systematically depresses Day-Ahead prices, driving increased negative price frequencies.
* **Spatial Arbitrage & Location Spread:** High wind generation in DK1 triggers capacity constraints on the Great Belt power link (Storebælt), expanding the DK1-DK2 location spread ($\text{Price}_{\text{DK1}} - \text{Price}_{\text{DK2}}$) down to extreme levels (-790.56 EUR/MWh).
* **Demand Premium:** DK2 (Copenhagen region) exhibits an average price premium of +1.95 EUR/MWh over DK1 due to structural demand patterns and transmission limits.

---

## How to Run

1. Clone this repository:
   ```bash
   git clone [https://github.com/meteaksu/nordpool-dk1-dk2-power-market-analysis.git](https://github.com/meteaksu/nordpool-dk1-dk2-power-market-analysis.git)
   cd nordpool-dk1-dk2-power-market-analysis

   Install required dependencies:

pip install pandas numpy matplotlib statsmodels

jupyter notebook DK1_DK2.ipynb
