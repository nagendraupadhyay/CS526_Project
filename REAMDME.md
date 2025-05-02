# Title: Analyzing Patterns and Predicting Severity of Traffic Accidents in Tennessee: The Impact of Weather and Temporal Factors

## Description
This project analyzes how weather conditions (rain, snow, visibility) and temporal factors (time of day, day of week) influence the frequency and severity of traffic accidents in Tennessee using the US Accidents dataset (2016–2023).

## Installation Instructions
To run this assignment, follow these steps:

1. **Prerequisites**:
   - Install Python 3.x.
   - Install the required libraries: pip install pandas numpy matplotlib seaborn statsmodels scikit-learn xgboost

2. **Download Requirements**:
   - Download the Jupyter Notebook.
   - Obtain the dataset from Kaggle link: https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents?resource=download
   - Uncomment the first code block in the notebook to extract data for the state of Tennessee, which will create a new "TN_accidents.csv" file that is used for everything.

3. **Run the Notebook**:
   - Open the notebook in Jupyter or any compatible environment.
   - Run the cells sequentially or use `Cell -> Run All` to execute the entire notebook.

## Usage
The project is organized into four phases:
1. Data Preprocessing
    - Handles missing values (median/mode imputation).
    - Feature engineering:
        - Time bins (e.g., Morning, Rush Hour).
        - Weather categories (e.g., Light Rain vs. Fair).
2. Exploratory Analysis
    - Visualizations:
        - Hourly accident counts (bar plots).
        - Severity distribution (pie/bar charts).
        - Correlation heatmaps (weather vs. severity).
3. Modeling
    - Accident Frequency:
        ```python 
            # Negative Binomial Regression (statsmodels)
            model = glm(formula="Accident_Count ~ Rush_Hour + Weather_Light_Rain", 
                data=accident_counts, 
                family=sm.families.NegativeBinomial()).fit()
        ```
    - Severity Prediction:
        - Random Forest (binary severity: low/high).
        - Ordinal Logistic Regression (1–4 severity levels).
4. Evaluation
    - Metrics:
        - RMSE (frequency model).
        - ROC-AUC, precision-recall (severity models).

## Key Findings
- Temporal Patterns: 44% more accidents during rush hours (*p* < 0.001).
- Weather Impact: Light rain reduced accidents by 34% (likely due to lower traffic volume).
- Severity Prediction:
    - Best ordinal model: MSE = 0.27 (~0.5 severity point error).
    - Random Forest struggled with high-severity cases (precision = 27%).

## Contact Information
Nagendra Upadhyay
- Reach out via Email: nupadhy3@vols.utk.edu

## Acknowledgments
- Dataset: Sobhan Moosavi (US Accidents, Kaggle).
- Tools: Pandas, Scikit-learn, StatsModels, Matplotlib.