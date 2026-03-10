## Project Title: Development and validation of a machine learning prediction model for cost-related medication nonadherence in Canada:a cross-sectional analysis of national survey data.

## Description
This repository contains the analytic code and trained prediction model for the study:Tucker DR, Dodani D, De Vera MA. Development and validation of a machine learning prediction model for cost-related medication nonadherence in Canada: a cross-sectional analysis of national survey data.

The goal of the study was to develop and internally validate machine learning models to estimate the probability of cost-related medication nonadherence (CRNA) among Canadians using data from the Canadian Community Health Survey (CCHS).


## Data source

The analyses were conducted using the Canadian Community Health Survey (CCHS) 2015–2016 Public Use Microdata File (PUMF), available from Statistics Canada.

The dataset is publicly available but must be downloaded directly from Statistics Canada and cannot be redistributed through this repository.



## Repository structure
Repository structure

data/
  Example input data structure

scripts/
  Data preparation and modelling scripts

models/
  Saved trained models (.rds)

elastic_model_crna_main.rds
elastic_model_crna_sex_race_province.rds

predict_model.R
  Script demonstrating how to generate predicted probabilities


## Prediction model

The final model selected in the manuscript was an elastic net logistic regression model trained using the tidymodels framework in R.

Predictors included:

- Age

- Insurance status

- Household income

- Number of chronic conditions

- Self-reported mental health conditions

Model performance in the independent test set:
AUROC ≈ 0.72

## Using the model

Load the trained model:

```r
model <- readRDS("models/elastic_model_crna_main.rds")
```
## Generate predicted probabilities
predict(model, new_data = input_data, type = "prob")


## Example code
Code is provided in CRNA_prediction_Canada_script.Rmd

## Citation
If you use this model or code, please cite:

Tucker DR, Thomas M, Dodani D, Law M, De Vera MA. Development and validation of a machine learning prediction model for cost-related medication nonadherence in Canada: a cross-sectional analysis of national survey data.


## Contact
Dwayne Tucker: dwayne.tucker@ubc.ca

Mary De Vera: mdevera@mail.ubc.ca


