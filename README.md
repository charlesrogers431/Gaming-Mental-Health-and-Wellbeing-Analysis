# Gaming, Mental Health, and Wellbeing Analysis

A data mining project applying four analytical techniques to explore how gaming behavior relates to sleep, mental health, and overall wellbeing.

## Overview

This project analyzes a 1,000-record dataset of gamers to answer a central question: **how does gaming behavior relate to mental health and wellbeing outcomes?** Using Python, I applied four distinct data mining techniques — association rule mining, clustering, classification, and regression — each answering a different analytical question about the same population.

![Daily Gaming Hours vs Sleep Hours](images/daily%20gaming%20hours%20vs%20daily%20sleep%20hours.png)

## Key Findings

**Gaming intensity is the central driver of wellbeing outcomes.** Across every technique, daily gaming hours emerged as the dominant variable affecting sleep, social isolation, and addiction risk.

![Correlation Heatmap](images/correlation%20heatmap%20of%20numeric%20features.png)

**Each additional hour of daily gaming is associated with ~24 fewer minutes of sleep** (linear regression, R² = 0.59).

**Three distinct gamer profiles exist along a clear wellbeing spectrum:**
- *Balanced Gamers* (~3 hrs/day): healthy sleep, low isolation, zero addiction risk
- *Moderate / At-Risk Gamers* (~6 hrs/day): declining sleep, mild risk
- *Heavy / High-Risk Gamers* (~10 hrs/day): severe sleep loss, high isolation, 4x spending

![Cluster Profiles](images/3%20distinct%20clusters.png)

**Two techniques independently identified the same warning signs.** Association rule mining found that withdrawal symptoms, loss of interest, and continued play despite problems strongly co-occur (lift 2.34). The classification model confirmed these same behaviors were the top predictors of addiction risk.

![Top Features Predicting Addiction Risk](images/top%2010%20features%20predicting%20gaming%20addiction%20risk.png)

## Techniques Used

| Technique | Question Answered | Key Result |
|-----------|------------------|------------|
| Association Rule Mining | Which symptoms co-occur? | Withdrawal + loss of interest cluster (lift 2.34) |
| Clustering (K-Means) | What natural gamer types exist? | 3 profiles, validated at K=3 |
| Classification (Decision Tree) | Can we predict addiction risk? | 98% accuracy |
| Regression (Linear) | Can we predict sleep from behavior? | R² = 0.59, ~24 min sleep lost per gaming hour |

## Methodology Notes

- The high classification accuracy (98%) and clean cluster separation suggest this is synthetic data with clear underlying patterns. The regression result (R² = 0.59) is more representative of real-world behavioral data.
- Data leakage was carefully avoided: sleep-derived features were excluded from the sleep regression, and addiction risk was excluded from clustering to allow independent validation.

## Tools

Python · pandas · scikit-learn · mlxtend · matplotlib · seaborn

## How to Run

1. Open `gaming_mental_health_analysis.ipynb` in Google Colab or Jupyter
2. Run all cells (the dataset loads automatically from this repo)

## Data Source

[Gaming and Mental Health dataset](https://www.kaggle.com/datasets/shaistashahid/gaming-and-mental-health) by Shaista Shahid, via Kaggle.
