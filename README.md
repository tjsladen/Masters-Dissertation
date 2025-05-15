# Emulating the Joint UK Land Environment Simulator (JULES)

This project explores statistical emulation methods to replicate the output of the JULES land surface model using machine learning. Simulators like JULES are computationally expensive; emulators offer a faster, more efficient alternative to estimate system outputs based on input parameters.

Available to view here: [Better emulators for JULES](https://github.com/tjsladen/Masters-Dissertation/blob/2ed3963600ba7d7401c1e0c7e50d67a28ee89055/Dissertation.pdf)

📌 Project Summary

The study compares three emulator methods:

    Gaussian Processes (GP)

    Random Forests (RF)

    Extreme Gradient Boosting (XGBoost)

The emulators were trained on 499 ensemble members from JULES Wave 0 data, representing outputs for 13 carbon-cycle-related variables over 165 years (1850–2014).
🧠 Objectives

    Model Accuracy: Evaluate how well each method predicts observations.

    Model Precision: Assess uncertainty via confidence intervals.

    Computational Cost: Compare tuning/training time across models.

⚙ Methodology

    Dimensionality Reduction: Principal Component Analysis (PCA) used to reduce 164-year time series into a smaller number of components while retaining ≥99.9% variance.

    Model Tuning:

        GP: Bayesian optimization.

        RF/XGBoost: Grid search (via R's caret package).

    Evaluation Metrics: RMSE, prediction interval width, true value coverage, and computation time.

📊 Key Results

    Best Accuracy (PCA Space): Gaussian Process performed best on most datasets.

    Lowest Uncertainty: Random Forest, but with poorer predictive performance.

    Best Coverage of True Values: Gaussian Process (despite wider intervals).

    Fastest Method: Random Forest; slowest was XGBoost.

    Overall Recommendation: GP or XGBoost depending on time constraints and emulator accuracy needs.

🗂 Data
[Link to paper/data](https://gmd.copernicus.org/articles/17/1059/2024/)

    Source: JULES Wave 0 ensembles from McNeall et al. (2024). 

    Inputs: 32 land surface parameters.

    Outputs: 13 datasets related to carbon cycling (e.g., NPP, CVeg, CSoil).

📈 Visuals

The dissertation includes:

    PCA reconstructions.

    Observed vs. predicted plots.

    Rank histograms.

    Confidence interval widths and coverage metrics.

    Clustered bar plots comparing computational times.
