# Video Games Sales Analysis

This repository contains a data analysis and modeling project on video game sales, based on the report in `Final-Project.pdf` and dataset `video_games_sales.csv`.

## Project Overview

The project analyzes how game attributes such as platform, genre, region, and user feedback relate to sales performance. It moves from exploratory analysis to predictive modeling for both:

- Regression (predicting continuous sales values)
- Classification (predicting high-sales vs low-sales games)

## Repository Contents

- `video_games_sales.csv`: raw game-level sales and metadata dataset
- `Final-Project.pdf`: full written report with methodology, code snippets, plots, and conclusions

## Dataset Snapshot

From the report and dataset inspection:

- Raw rows: 7,501
- Raw columns: 13
- Core fields: `Name`, `Platform`, `Year`, `Genre`, `Publisher`, regional sales, `Global_Sales`, `User_Score`, `User_Count`, `Rating`

The analysis pipeline aggregates game entries across platforms to create a cleaned dataset of unique titles used for modeling.

## Analysis Workflow (from report)

1. Data cleaning and transformation
- Aggregated duplicate game titles released across multiple platforms.
- Created platform indicator columns (`DS`, `PC`, `PS2`, `PS3`, `XB`, `PSP`, `X360`).
- Fixed variable types and removed missing values.
- Applied log transforms to skewed variables (notably global sales and user count).

2. Exploratory analysis
- Univariate analysis (distribution checks before/after transformations).
- Bivariate and trivariate analysis across sales, genres, ratings, and platforms.

3. Predictive modeling
- Linear regression and multiple regression for sales prediction.
- Random forest for high/low sales classification.
- Logistic regression with calibration analysis.
- Classification tree and KNN comparison.

## Reported Model Results

Random forest classification:
- Accuracy: `0.7959`
- Balanced accuracy: `0.7976`
- ROC AUC: `0.8694`

Classification tree vs KNN:
- Classification tree accuracy: `0.688`
- KNN accuracy: `0.686`
- Report conclusion: classification tree performed slightly better overall.

## Key Takeaways

- Sales-related variables are highly right-skewed and benefit from log transformation.
- Genre, platform, and regional sales patterns are meaningful predictors of global performance.
- Among compared classification approaches, the classification tree is highlighted as the most reliable tradeoff between performance and interpretability in this project.

## Notes on Reproducibility

The PDF includes R code snippets and outputs, but this repository currently does not include a standalone `.R` script or notebook. To fully reproduce the report end-to-end, an analysis script would need to be added.

## Author

- Aniket Rattan
- Report date: 2024-11-08
