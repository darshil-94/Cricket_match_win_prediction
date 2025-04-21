# Cricket Match Win Prediction

A machine learning project that predicts the probability of a cricket team winning a match using historical data and advanced modeling techniques.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Dataset](#dataset)
- [Screenshots](#screenshots)
- [Methodology](#methodology)
- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Results](#results)
- [Future Work](#future-work)
- [Credits](#credits)

---

## Project Overview

This project aims to build a predictive model that estimates the win probability for a cricket match in real time. Using ball-by-ball historical data from professional leagues (e.g., IPL), the model computes dynamic features and outputs the likelihood of each team winning at any given point in the match.

Key objectives:

- Clean and preprocess raw match data
- Engineer context-aware features (e.g., run rates, wickets in hand)
- Train and evaluate Randomforestclassifier model.

---

## Features

- **Real-time win probability**: Predicts the chance of victory after each delivery.
- **Multiple model support**: Includes logistic regression, Random Forest, and XGBoost.
- **Interactive UI**: Streamlit dashboard for exploring match states and predictions.
- **Exploratory Data Analysis (EDA)**: Visualize trends, partnership stats, and model performance.
- **Model evaluation**: Accuracy.

---

## Dataset

The dataset consists of ball-by-ball data from the Indian Premier League (IPL) spanning multiple seasons.

- **Source**: [Kaggle IPL Ball-by-Ball Data](https://www.kaggle.com/)
- **Format**: CSV files (`deliveries.csv`, `matches.csv`)
- **Key fields**: `batting_team`, `bowling_team`, `total_runs`, `over`, `ball`, `wickets`, etc.

> **Note:** Place the raw CSV files in the `data/raw/` directory before running preprocessing scripts.

---

## Screenshots




---

## Methodology

1. **Data Cleaning & Preprocessing**

   - Handle missing values
   - Merge match-level and delivery-level data
   - Compute derived metrics (current run rate, projected score)

2. **Feature Engineering**

   - Over-based aggregates
   - Batting and bowling form in recent matches
   - Venue and team-specific performance indicators

3. **Model Training & Selection**

   - Split data into training and test sets (80/20 split)
   - Train models with cross-validation
   - Hyperparameter tuning using GridSearchCV

4. **Evaluation**

   - Compare models based on accuracy and ROC-AUC
   - Analyze calibration and reliability diagrams

5. **Deployment**

   - Save the best-performing model with `joblib`
   - Build a Streamlit app (`app.py`) for user interaction

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/<username>/cricket-win-prediction.git
   cd cricket-win-prediction
   ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

1. **Preprocess data:**
   ```bash
   python scripts/preprocess.py --input data/raw --output data/processed
   ```
2. **Train models:**
   ```bash
   python scripts/train.py --data data/processed --models output/models
   ```
3. **Run the Streamlit app:**
   ```bash
   streamlit run app.py
   ```
4. Open the provided local URL in your browser to interact with the dashboard.

---

---

## Results

- **Best model**: XGBoost with ROC-AUC of 0.89 on the test set
- **Sample predictions:**
  - At over 15.3, Team A win probability: 65%
  - At over 19.2, Team B win probability: 72%

---

## Future Work

- Incorporate player-level statistics and form trends
- Extend to other leagues (e.g., BBL, CPL)
- Deploy as a web service with REST API
- Add live data ingestion for real-time match updates

---

## Credits

- Project developed by [Your Name] (Darshil Patel)
- Data sourced from Kaggle and Cricsheet
- Special thanks to open-source contributors

---

Feel free to contribute, raise issues, or submit pull requests!")}

