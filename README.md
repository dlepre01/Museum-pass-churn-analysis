# Museum-pass-churn-analysis — Big Data in Economics Project

**Course:** Big Data in Economics (A.Y. 2024/2025)  
**Type:** Economics for Data Science — project work  
**Goal:** Apply the course methods to a real dataset and produce a business-style **pitch** supported by data preparation + ML/analytics results. 

## Business Problem
The **Museum Pass** gives access to a large network of museums in Turin and surrounding areas (1-year validity, unlimited visits).  
A significant share of users **does not renew**, generating high churn. The project focuses on:

- Identifying **drivers of churn**
- Building **predictive models** to anticipate churn
- Designing a **targeted marketing campaign** to improve retention and profitability :contentReference[oaicite:1]{index=1}

## Dataset
Three main sources:

- `data1.csv` — general customer information + churn label (`si2014`)
- `an13.csv` — demographics, payment info, discount/reduction types
- `in13.csv` — museum visits (date, time, museum) :contentReference[oaicite:2]{index=2}

## Data Preparation & Feature Engineering (high level)
Key steps performed:

- Cleaning and filtering unrealistic ages, invalid timestamps, and non-useful fields
- Building the churn label: **churn = 1 if customer did not renew**
- Aggregating visit-level data per customer (`numero_visite`, `musei_unici`, `ultimo_ingr_mese`, `quota_risparmiata`, …)
- Encoding categorical variables (binarization / one-hot), and multicollinearity removal :contentReference[oaicite:3]{index=3}

## Analysis & Methods
The workflow includes:

- Exploratory insights on museums and customers
- **Correlation analysis** (low single-feature correlation, but clear signal from engagement variables)
- **Clustering** (Self-Organizing Map + 2 clusters: low vs high engagement)
- **Customer network analysis** (users connected by repeated shared visits)
- **Causal analysis** (Propensity Score Matching to test gender effect on churn)
- **Churn prediction** (CART, Random Forest, KNN, AdaBoost; also under-sampling variants) :contentReference[oaicite:4]{index=4}

## Main Results
- Churn rate around **30.6%**
- Engagement is strongly protective: more visits / more savings → lower churn
- SOM clustering separates **at-risk low engagement** vs **loyal high engagement**
- Small but significant gender effect (women slightly less likely to churn)
- Best predictive performance: **AdaBoost** (top AUC), with **Random Forest (under-sampling)** close behind and often more cost-efficient for campaign constraints :contentReference[oaicite:5]{index=5}

## Marketing Campaign Simulation
A profitability scenario evaluates contacting customers at risk of churn:

- +10€ net profit for each contacted churner who renews
- −2€ cost for each contacted non-churner

AdaBoost yields the highest maximum cumulative profit; Random Forest under-sampling provides similar profit with fewer contacts in budget-tight settings. 

## Repository Contents
- `Big_Data_Eco_code_LEPRE.Rmd` — analysis notebook / report code
- `Big_data_eco_pres_LEPRE.pdf` — final slides (business-style pitch) 

## How to Run
> If you want this section fully accurate (packages + commands), keep it minimal until you confirm your environment.

1. Open `Big_Data_Eco_code_LEPRE.Rmd` in RStudio
2. Install required R packages (as indicated in the file)
3. Knit to HTML/PDF or run chunks interactively

## Credits
Project work developed for the course “Big Data in Economics”.
