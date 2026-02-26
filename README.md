# Turin Museums — Churn Prediction & Customer Analytics  
**Course:** Big Data in Economics  

## Objective

Apply Big Data and Machine Learning techniques to a real-world dataset in order to:

- Understand the determinants of customer churn  
- Build predictive models to identify at-risk customers  
- Simulate a data-driven marketing campaign  
- Present results in a business-style pitch format  


## Business Context

The **Museum Pass** allows unlimited access to a network of museums in Turin and surrounding areas for one year.

A relevant share of customers does not renew their subscription (churn ≈ 30%).  
The goal of the project is to:

- Identify behavioral and demographic patterns linked to churn  
- Build predictive models  
- Estimate profitability of a retention campaign  

## Dataset Description

The project uses three datasets:

### `data1.csv`
- `Codcliente`: customer ID  
- `Si2014`: churn label (0 = churn)  
- `ultimo_ing.x`: date of last visit  
- `abb13`: starting date of card (2013)  
- `abb14`: renewal date in 2014 (if renewed)  

### `an13.csv`
- `Codcliente`: customer ID  
- `data_inizio`: card activation date  
- `importo`: price paid  
- `sconto`: discount type  
- `Riduzione`: price reduction category (e.g., student, over 60)  
- `Tipo_pag`: payment method  
- `Agenzia_tipo`: purchase channel (online, museum, association, etc.)  
- `Sesso`: gender  
- `Data di nascita`: birth year  
- `Professione`: employment status  
- `Cap`: zip code  
- `Nuovo_abonn`: new subscriber indicator  

### `in13.csv`
- `datai`: visit date  
- `orai`: visit time  
- `importo`: ticket value (not paid due to subscription)  
- `museo`: museum name  
- `prov_museo`: museum province  
- `com_museo`: museum city  
- `Codcliente`: customer ID  

Dataset variable documentation available in:  
`take_home_file_description.pdf`


## Data Processing & Feature Engineering

- Churn variable construction
- Cleaning inconsistent ages and timestamps
- Aggregation of visit-level data into customer-level features
- Creation of behavioral indicators:
  - Number of visits
  - Number of unique museums
  - Month of last visit
  - Estimated savings (subscription value)
- Encoding categorical variables
- Multicollinearity removal

## Methods

### Exploratory Analysis
- Churn rate ≈ 30.6%
- Engagement strongly correlated with retention

### Clustering
- Self-Organizing Map (SOM)
- Two main behavioral clusters:
  - Low engagement → high churn risk
  - High engagement → loyal users

### Network Analysis
- Customer network based on co-visits

### Causal Inference
- Propensity Score Matching (PSM)
- Small but significant gender effect on churn

### Predictive Models
- CART
- Random Forest
- KNN
- AdaBoost
- Under-sampling strategies

**Best predictive performance:** AdaBoost (highest AUC)


## Marketing Campaign Simulation

Profit function:

- +10€ for correctly identified churners who renew  
- −2€ cost for contacting non-churners  

AdaBoost maximized cumulative profit.  
Random Forest under-sampling provided similar profit under budget constraints.

## Tech Stack

- R
- Machine Learning (classification models)
- Clustering (SOM)
- Causal Inference (PSM)
- Network analysis
- Data visualization


## 📎 Repository Structure
