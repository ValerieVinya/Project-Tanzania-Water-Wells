# TANZANIA-WATER-WELLS-PREDICTION-PROJECT

## Business Understanding

### 1.1 Overview

Tanzania is a developing country that struggles to get clean water to its population of 59 million people. According 
to WHO, 1 in 6 people in Tanzania lack access to safe drinking water and 29 million don’t have access to improved 
sanitation. The focus of this project is to build a classification model to predict the functionality of waterpoints 
in Tanzania given data provided by Taarifa and the Tanzanian Ministry of Water. The model was built from a dataset 
containing information about the source of water and the status of the waterpoint (functional, functional but needs repairs, 
and non-functional) using an iterative approach and can be found here. The dataset contains 60,000 waterpoints in Tanzania 
and the following features will be used in our final model:

amount_tsh — Total static head (amount water available to waterpoint)

gps_height — Altitude of the well

installer — Organization that installed the well

longitude — GPS coordinate

latitude — GPS coordinate

basin — Geographic water basin

region — Geographic location

population — Population around the well

recorded_by — Group entering this row of data

construction_year — Year the waterpoint was constructed

extraction_type_class — The kind of extraction the waterpoint uses

management — How the waterpoint is managed

payment_type — What the water costs

water_quality — The quality of the water

quantity — The quantity of water

source_type — The source of the water

waterpoint_type — The kind of waterpoint

The first sections focus on investigating, cleaning, wrangling, and reducing dimensionality for modeling. The next 
section contains 4 different classification models and an evaluation of each, ultimately leading to us to select our 
best model for predicting waterpoint status based on the precision of the functional wells in the model. Finally, 
we will make recommendations to the Tanzanian Government and provide insight into predicting the status of waterpoints.

### 1.2 Business Problem

The Tanzanian government has a severe water crisis on its hands as a result of the vast number of non-functional 
wells and they have asked for help. They want to be able to predict the statuses of which pumps are functional, 
functional but need repair, and non-functional to improve their maintenance operations and ensure that 
their residents have access to safe drinking water. The data has been collected by and is provided by Taarifa and 
the Tanzanian Ministry of Water with the hope that the information provided by each waterpoint can aid understanding 
in which waterpoints will fail.

In this project, we build a classification model to predict the status of the water points using the dataset provided
by the Tanzanian government. We will use the precision of the functional wells as my main metric for 
model selection, as a non-functional well being predicted as a functional well would be more detrimental to their 
case, but will provide and discuss several metrics for each model.

The dataset used contains a wealth of information about water points in Tanzania and the status of their operation. 
The target variable has 3 different options for it’s status:

functional — the waterpoint is operational and there are no repairs needed

functional needs repair — the waterpoint is operational but needs repairs

non functional — the waterpoint is not operational

### 1.3 Metrics of success

Our model project will be considered a success if;

1. We identify various features that influence the status of the wells' status.

2. We realize the best-performing model for deployment.

## 2 Data Cleaning

This involved several parts including:

- Descriptive statistics
- Completeness
- Consistency
- Validity

## EDA

We used relation plots and count plots as seen in the visuals in the notebook together with the following.

## Correlation matrix

![image](https://github.com/nguro23/Tanazanian-Water-Wells-Project/assets/142256019/a6ff4345-5676-43d2-9010-443c8a58259e)

## Pump status vs payment type at Wells

![image](https://github.com/nguro23/Tanazanian-Water-Wells-Project/assets/142256019/a093459a-a372-491e-b934-0227d1a58981)

## MODELING

We used the following models to evaluate the best-performing one:

- Logistic regression
- K-NearestNeighbour
- Random Forest
- Decision Tree

## Conclusions

- Decision Tree accounts for the highest performance among the trained models.
- Non-functional wells account for 1/3 of all the wells in Tanzania.
- Most of the population is clustered in only areas with functional wells.
- The small management units are the most clustered with the water wells.

## Recommendations

- Deploy a Decision tree as the preferred model.
- Hasten to repair non-functional wells which is a high number.
- Overstretch the distribution of wells to prevent overpopulation in given areas.
- Enhance management by the local communities more than institutions.
