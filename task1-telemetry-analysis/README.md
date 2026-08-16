# Task 1: Daikibo Telemetry Data Analysis & Tableau Dashboard

## Business Problem
Daikibo collected one month of telemetry data (May 2021) from four global factories to answer two core operational questions:
1. **In which location did machines break down the most?**
2. **Which specific machine types broke down most frequently in that location?**

---

## Data Overview
* **Source:** Single JSON file containing telemetry data across 4 factories:
  * Tokyo, Japan (Factory Meiyo)
  * Osaka, Japan (Factory Seiko)
  * Berlin, Germany (Daikibo Berlin)
  * Shenzhen, China (Daikibo Shenzhen)
* **Frequency:** 9 machine types sending telemetry signals every 10 minutes over 31 days.
* **Calculated Metric:** Created an `Unhealthy` calculated field assigned a value of `10` (representing 10 minutes of potential downtime per unhealthy status log).

---

## Technical Execution (Tableau)
1. **Data Ingestion:** Unzipped and imported `daikibo-telemetry-data.json`, ensuring all schema levels were selected during parsing.
2. **Calculated Field Creation:** 
   ```tableau
   IF [Status] = "unhealthy" THEN 10 ELSE 0 END

Visualization 1: Bar chart displaying Total Down Time per Factory.
<img width="1446" height="939" alt="Downtime Per Factory - Dharini" src="https://github.com/user-attachments/assets/4363555f-bec0-4502-a9b9-952ccde05e38" />

Visualization 2: Bar chart displaying Down Time per Device Type.
<img width="1446" height="939" alt="Downtime Per Device Type - Dharini" src="https://github.com/user-attachments/assets/909db7f1-9d49-4497-988b-0cb0fd2998ba" />

Interactive Dashboard: Combined both charts and enabled Visualization 1 as an interactive cross-filter.
<img width="1446" height="939" alt="Dashboard Image- Dharini" src="https://github.com/user-attachments/assets/c0893296-cd32-4e49-ab78-bc24ed19b679" />

## Executive Findings & Business Insights
* **Factory with Highest Downtime:** **Daikibo Shenzhen** (Total calculated downtime: ~420 minutes).
* **Top Failing Device Type:** **LaserCutter** (Responsible for nearly all downtime at the Shenzhen location with ~390 minutes of unhealthy status logs).
* **Key Finding:** Machine failure is heavily concentrated in a single equipment type (`LaserCutter`) at the Shenzhen facility, indicating an urgent need for targeted maintenance, calibration, or operational review on those specific units rather than systemic facility-wide issues.
