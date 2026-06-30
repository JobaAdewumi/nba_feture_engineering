# NBA Rookie Career Longevity Prediction

## Project Overview
This project aims to predict whether an NBA rookie will have a career lasting at least 5 years based on their performance metrics during their debut season.

## Dataset Source
The dataset (`nba-players.csv`) contains rookie season statistics for various players, including shooting percentages, rebounds, assists, and defensive stats.

## Prediction Goal
*   **Target Variable**: `target_5yrs` (Binary)
    *   `1`: Career duration ≥ 5 years.
    *   `0`: Career duration < 5 years.

## Feature Engineering Workflow
To move beyond basic volume statistics, the following engineering steps were performed:

### 1. Data Cleaning
- **Column Removal**: Dropped non-predictive features such as `name` and index columns to prevent data leakage and noise.
- **Null Handling**: Handled missing values (specifically in 3-point categories) to ensure mathematical consistency.

### 2. Efficiency Metrics
- **Points Per Minute (pts_per_min)**: Normalizes scoring volume against playtime.
- **True Shooting Percentage (TS%)**: A comprehensive shooting metric accounting for 2P, 3P, and FT efficiency.
- **Assist-to-Turnover Ratio**: Measures playmaking intelligence and ball security.

### 3. Defensive & Hustle Metrics
- **Defensive Impact per Minute**: Combines steals and blocks normalized by minutes played.
- **Rebounds per Minute**: Captures glass-cleaning efficiency regardless of total court time.

## Methodology
We utilize correlation analysis to identify which features (both original and engineered) provide the strongest signal for career longevity, helping to select the best inputs for classification models.
