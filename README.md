**Shark Tank Deal Prediction Analysis**

A statistical analysis project using machine learning to predict deal outcomes on the TV show Shark Tank and identify optimal equity offers for entrepreneurs.

**Project Overview**

This project analyzes data from the reality TV show Shark Tank to answer two key questions:

Can we predict whether a pitch will receive a deal? Using Random Forest classification to identify key success factors.
What equity offer maximizes deal probability? Using Generalized Additive Models (GAM) to find the optimal "sweet spot."

**Key Findings**

Optimal Equity Range: Offering 20-25% equity maximizes deal probability (~60-65% success rate)
Team Composition Matters: Multiple female entrepreneurs had the highest success rate (71.2%)
Top Predictors: Deal amount, number of sharks involved, and investment per shark are the strongest indicators
Geographic Trends: Utah (75%), Texas (67.1%), and Georgia (64.3%) had the highest success rates

**Dataset**

Source: Shark Tank US dataset containing detailed pitch and investment information
**Key Variables:**

Categorical: Industry, Gender, State, Royalty Deal, Deal Status
Numerical: Ask Amount, Equity Offered, Valuation, Deal Terms, Number of Sharks

**Methodology**

Random Forest Model

Purpose: Comprehensive prediction of deal outcomes
Performance: Achieved perfect classification on test set (100% accuracy)
Implementation: 500 trees, 80/20 train-test split

Generalized Additive Model (GAM)

Purpose: Model non-linear relationship between equity and deal probability
Key Insight: Reveals optimal equity range using smooth splines
Controls: Ask amount, valuation, industry, gender, team size

**Results Summary**

Success Rates by Demographics

Female pitchers: 63.6%
Male pitchers: 58.1%
Mixed teams: 66.4%
Group pitches: 68.3% vs Solo: 56.1%

Variable Importance (Random Forest)

Total Deal Amount (14.63)
Number of Sharks in Deal (14.04)
Investment Amount Per Shark (13.91)
Total Deal Equity (8.78)
Equity Per Shark (8.32)

**Getting Started**

Prerequisites
rinstall.packages(c("caret", "randomForest", "dplyr", "mgcv", "ggplot2", "tidyverse"))
Running the Analysis

Clone the repository
Place the Shark Tank dataset CSV in your working directory
Run the analysis scripts:

r# Load packages
library(caret)
library(randomForest)
library(mgcv)
library(tidyverse)

# Run data cleaning and EDA
source("data_cleaning.R")

# Run Random Forest model
source("random_forest_model.R")

# Run GAM analysis
source("gam_model.R")

**Visualizations**

The project includes several key visualizations:

Deal success rates by gender and team composition
Geographic distribution of success rates
Variable importance plots
Smooth effect curves for equity offers
Predicted probability plots

**Technical Details**
Data Preprocessing

Missing values imputed as 0 for non-deal cases
Categorical variables properly encoded
Startup names removed as unique identifiers
Train-test split: 80/20

**Model Specifications**

Random Forest: ntree=500, mtry=3, importance=TRUE
GAM: Binomial family with logit link, smooth term for equity

**Limitations**

Cannot capture qualitative factors (presentation skills, negotiation dynamics)
Perfect accuracy suggests potential data leakage from using post-deal variables
Results specific to Shark Tank context

**Future Directions**

Build pre-pitch prediction model using only available information
Incorporate sentiment analysis from pitch transcripts
Cross-validation with other entrepreneurship datasets
Time-series analysis of deal trends across seasons

**Contributors**

Mitchell Darling: Data cleaning and EDA
Shania King: Random Forest implementation
Siyona Behera: GAM development
Sree Penumuchu: Results interpretation and report writing
