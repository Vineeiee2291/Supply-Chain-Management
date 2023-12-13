# Supply-Chain-Management
Optimizing the Supply Chain: A Data-Driven Approach for Enhanced Efficiency and Performance

## Problem Statement
An FMCG company entered into the instant noodles business two years back. Their higher management has noticed that there is a miss match in the demand and supply. Where the demand is high, supply is pretty low and where the demand is low, supply is pretty high. In both ways, it is an inventory cost loss to the company; hence, the higher management wants to optimize the supply quantity in every warehouse in the entire country.

## Dataset Information Overview
- Dataset consists of 25,000 entries 
- RangeIndex from 0 to 24,999.
- A total of 24 columns provide detailed information about different aspects of the supply chain.
- No null values in most columns.
- Some missing values in columns such as workers_num, wh_est_year, and approved_wh_govt_certificate.
- workers_num: 990 missing values.
- wh_est_year: 11,881 missing values.
- approved_wh_govt_certificate: 908 missing values.
- Majority of columns are of type int64.
- A few columns are of type float64 and object.

![Screenshot (51)](https://github.com/Vineeiee2291/Supply-Chain-Management/assets/118652081/58cfb1b6-9942-44f1-8e46-2bcc08996669)

## Descriptive Statistics of the Dataset
![Screenshot (52)](https://github.com/Vineeiee2291/Supply-Chain-Management/assets/118652081/58ae67a6-d876-4a21-ba9a-492fb8b98f20)

## Handling missing values
#### Worker's Number: 3.960% missing values.
- Imputing missing values in 'workers_num' using the KNN imputer.
- Rounding the imputed values and converting them to integers.
#### Warehouse Establishment Year: 47.524% missing values.
- Strong negative correlation between 'Warehouse Establishment Year' and 'Product Weight in Tons.'
- Significant correlation indicates the importance of 'Warehouse Establishment Year' in predicting 'Product Weight in Tons.'
- Imputation Technique: Utilize KNN Imputer from sklearn.impute.
- Imputation Approach: Impute missing values in 'Warehouse Establishment Year' based on the values of its 5 nearest neighbors.
#### Approved WH Govt Certificate: 3.632% missing values.
- Using the mode (most frequent value) to fill missing values in the 'approved_wh_govt_certificate' column.

## Feature Engineering
- Created a new feature 'wh_age' representing warehouse age.
- Calculated by subtracting the establishment year from the current year (2023).
- Mean Age: The average age of warehouses is approximately 13.8 years.
- Age Range: Warehouses have an age range from 0 to 27 years.
- 25% of warehouses have an age of 13 years or less.
- 50% of warehouses have an age of 14 years.
- 75% of warehouses have an age of 14 years or less.
- Variability: The standard deviation is 5.46, indicating some variability in warehouse ages.

## Exploratory Data Analysis
#### Location type
- 91.8% warehouses are located in Rural areas.
- 8.2% warehouses are located in Urban areas.

#### WH_capacity_size
- Approximately 40% categorized as Large warehouses.
- Another 40% classified as Mid-sized warehouses.
- Only 20% fall into the Small warehouse category.

#### zone
- North zone has highest number of warehouses approx 41%
- East has lowest number of warehouses, only 1.7%
- West has 31.7% and South has 25.4% warehouses.

#### Refill Patterns in last 3 months
- 2,846 warehouses (approx. average) needed 4 refills.
- A total of 2,990 warehouses requested only 3 refills in the last 3 months.
- In 2,970 warehouses, the maximum number of refills (8) has been carried out.
- Majority of warehouses (2,941) required 5 refills, indicating demand between 3 and 8.
- 2,912 warehouses did not conduct any refills.
- A notable number of 2,873 warehouses conducted 7 refills, showcasing a high demand pattern.
- 2,856 warehouses had only 1 refill, suggesting lower demand compared to the average.
- 1,808 warehouses recorded with 2 refills, relatively lower compared to the average.

#### Transport Issues in last 1 year
- The majority (15,215) of warehouses reported no transport issues in the last 3 months.
- A significant number (4,644) experienced 1 transport issue.
- 2,198 warehouses reported 2 transport issues, indicating a relatively lower occurrence compared to those with only 1 issue.
- In 1,818 warehouses, 3 transport issues were reported, showing a moderate level of transportation challenges.
- 777 warehouses faced 4 transport issues, suggesting an increase in logistical difficulties.
- A total of 348 warehouses encountered 5 transport issues, reflecting a notable transportation disruption.

#### Competitor in Market
- Majority (8,669) reported 2 competitors, a common scenario.
- 7,094 warehouses indicated 3 competitors, reflecting typical competition.
- 6,708 warehouses faced competition from 4 players.
- 1,265 mentioned dealing with 5 competitors, indicating a more challenging environment.
- 546 warehouses reported 6 competitors, suggesting increased market saturation.
- 432 warehouses had only 1 competitor, indicating a less competitive market.
- 189 faced competition from 7 players, highlighting an intense landscape.
- Few warehouses reported competition with 8 (76), 9 (13), and 10 (6) competitors.
- Unique situations: 1 warehouse each reported 0 and 12 competitors.

#### Number of Distributors
- Dataset: 25,000 observations.
- Mean Distributors: Approximately 42 per warehouse.
- Variability: Standard deviation around 16, indicating some variability.
- Range: Distributors range from 15 to 70.
- Median Distributors: 42.
- Interquartile Range (IQR): 25th to 75th percentile spans from 29 to 56 distributors.
- Distribution Symmetry: Relatively symmetrical with a slight tendency towards higher counts.
- Peak Counts: Warehouses with 31, 41, and 69 distributors have the highest occurrences (each 481 times).

#### Flood impacted 
- Approximately 90.18% (22,546 warehouses) are not located in flood-impacted areas.
- About 9.82% (2,454 warehouses) are situated in flood-impacted areas.

#### Flood Proof
- Approximately 94.54% (23,634 warehouses) are not labeled as flood-proof.
- About 5.46% (1,366 warehouses) are labeled as flood-proof.

#### Distance from hub
- Mean: Approximately 163.54, indicating central tendency.
- Variability: Standard deviation of 62.72 suggests moderate variability.
- Range: From 55 to 271, showcasing varied distances.
- Median: 164, indicating the center point.
- IQR: 25th to 75th percentiles span from 109 to 218, representing the middle 50%.
- Symmetry: The distribution appears approximately symmetrical around the mean.

#### Number of workers
- Mean: Approximately 28.95, indicating central tendency.
- Variability: Standard deviation of 7.72 suggests moderate variability.
- Range: From 10 to 98, showcasing variability in worker counts.
- Median: 28, indicating the center point.
- IQR: 25th to 75th percentiles span from 24 to 33, representing the middle 50%.
- Symmetry: The distribution appears approximately symmetrical around the mean.

#### Storage Issues reported in last 3 months
- Range: Reported issues range from 0 to 39, showcasing a spectrum of potential problems.
- Median: 18, indicating that half of the warehouses reported 18 or fewer storage issues in the last 3 months.
- IQR: 25th to 75th percentiles span from 10 to 24, representing the middle 50% of reported storage issues.

#### Temperature-Regulating Machines
- Warehouses without Machines : 17,418 (approximately 69.67%).
- Warehouses with Machines : 7,582 (approximately 30.33%).
- Majority: A significant 69.67% of warehouses lack a temperature-regulating machine.
- Presence: 30.33% (7,582 warehouses) have a temperature-regulating machine, indicating substantial capability for controlled temperature environments.

#### Government Checks in last 3 months
- Minimum: Recorded value of 1, indicating warehouses with minimal government officer presence for food checks.
- 25th Percentile (Q1): 11, suggesting 25% of warehouses experienced 11 or fewer government checks in the last 3 months.
- Median (50th Percentile or Q2): 21, indicating that half of the warehouses had 21 or fewer government checks.
- 75th Percentile (Q3): 26, implying 75% of warehouses underwent 26 or fewer government checks.
- Maximum: Recorded value of 32, indicating some warehouses experienced the maximum possible number of government checks in the specified time frame.

#### Product Weight in Tons for last 3 months
- Average Weight: Approximately 22,102.63 tons over the last three months.
- Range: From a minimum of 2,065 tons to a maximum of 55,151 tons.
- 25th Percentile (Q1): 13,059 tons, indicating 25% of warehouses have a weight of 13,059 tons or lower.
- Median (50th Percentile or Q2): 22,101 tons, suggesting 50% of warehouses have a weight of 22,101 tons or lower.
- 75th Percentile (Q3): 30,103 tons, showing 75% of warehouses have a weight of 30,103 tons or lower.
- Distribution Symmetry: Mean and median are close, indicating a relatively symmetrical distribution of product weight.
- Variability: Standard deviation of 11,607.76 suggests a moderate amount of variability.
- Maximum Weight: Recorded at 55,151 tons, representing the highest weight among warehouses in the last three months.

#### Flood-Impacted vs Flood-Proof
- Non-flood-Proof Measures - Among flood-impacted warehouses, 87.2% have not implemented flood-proof measures.
- Flood-Proof Measures - Conversely, 12.8% of flood-impacted warehouses have implemented flood-proof measures.
- Vulnerabilities - A significant portion of flood-impacted warehouses lacks flood-proof measures, indicating potential vulnerabilities.
- Protective Measures - The number of warehouses with flood-proof measures is comparatively low, emphasizing the need for additional protective measures in flood-prone areas.

## Feature Correlation
![corr](https://github.com/Vineeiee2291/Supply-Chain-Management/assets/118652081/9e75665d-9ef7-4c3d-86a4-0d7d35f18a3e)

## Correlation with the target column
![corr_with_target](https://github.com/Vineeiee2291/Supply-Chain-Management/assets/118652081/2906c76c-3800-4026-b548-f119edca5528)

#### Negative Correlation:
- Warehouse establishment year (wh_est_year): -0.60, older warehouses tend to have lower product weight.
#### Weak Negative Correlation:
- Transport issues in the last year (transport_issue_l1y): -0.17, fewer transport issues may mean slightly higher product weight.
#### No Significant Correlation:
- Variables (govt_check_l3m, workers_num, retail_shop_num, dist_from_hub, flood_impacted, electric_supply, flood_proof, WH_regional_zone, num_refill_req_l3m, distributor_num, Competitor_in_mkt, WH_regional_zone) show no significant linear relationship with product weight.
#### Positive Correlation:
- Temperature-regulating machine indicator (temp_reg_mach): 0.10, warehouses with these machines may have slightly higher product weight.
#### Moderate Positive Correlation:
- Warehouse breakdowns in the last 3 months (wh_breakdown_l3m): 0.34, breakdowns relate to higher product weight.
#### Strong Positive Correlation:
- Warehouse age (wh_age): 0.60, older warehouses have higher product weight.
#### Very Strong Positive Correlation:
- Storage issues reported in the last 3 months (storage_issue_reported_l3m): 0.99, warehouses reporting issues tend to have significantly higher product weight.

## Impact of Categorical Features on Target Variable
### Highly Relevant Features
#### Location Type:
- ANOVA F-statistic: 139.77
- P-value: 3.64e-32
- Observation: Significant differences in means, highly relevant.
#### Approved Warehouse Govt Certificate:
- ANOVA F-statistic: 365.64
- P-value: 1.55e-306
- Observation: Significant differences in means, highly relevant.
### Potentially Relevant Feature
#### Warehouse Capacity Size:
- ANOVA F-statistic: 1.11
- P-value: 0.33
- Observation: Borderline result (p-value: 0.33), potential relevance, further investigation warranted.
### Less Relevant Features:
#### Zone:
- ANOVA F-statistic: 1.11
- P-value: 0.35
- Observation: No significant differences in means, less relevant.
#### Warehouse Owner Type:
- ANOVA F-statistic: 0.84
- P-value: 0.36
- Observation: No significant differences in means, less relevant.

## Encoding Categorical Features
- Utilized LabelEncoder from sklearn.preprocessing to transform categorical variables in the dataset.
- Encoded 'Location_type', 'WH_capacity_size', 'wh_owner_type', and 'approved_wh_govt_certificate' using LabelEncoder for numerical representation.
- Applied one-hot encoding to 'zone' variable for enhanced model interpretability and performance.
- This preprocessing step ensures compatibility with machine learning algorithms that require numerical input.
- Improved data readiness and paved the way for more robust model development and analysis.

## Variance Inflation Factor
![Screenshot (53)](https://github.com/Vineeiee2291/Supply-Chain-Management/assets/118652081/ab54e2fd-5739-454c-8af7-03468a06ca48)

## Model Building and Evaluation
- Diverse Ensemble: Employed a diverse set of regression models to capture various nuances in the dataset.
- Linear Models: Utilized Linear Regression, Ridge, Lasso, and Support Vector Regression (SVR) to capture linear relationships.
- Tree-Based Models: Incorporated Decision Tree, Random Forest, Extra Trees, Gradient Boosting, AdaBoost, and XGBoost for capturing non-linear patterns and interactions.
- Neural Network: Implemented a Multilayer Perceptron (MLP) for its ability to model complex, non-linear relationships.
- Ensuring Robustness: Ensemble of models provides robust predictions by combining the strengths of different algorithms.
- Hyperparameter Tuning: Fine-tuned model hyperparameters to optimize individual model performance.
- Evaluation Metrics: Assessed models using standard regression evaluation metrics such as R-squared, Mean Squared Error (MSE), and Mean Absolute Error (MAE).
- Insightful Ensemble: Each model contributes uniquely, contributing to a more insightful and accurate prediction.

## Evaluation Results
![Screenshot (54)](https://github.com/Vineeiee2291/Supply-Chain-Management/assets/118652081/e79e8c59-ff16-40f2-8bff-5c51fd6dc559)
- Top Performers: XGBoost, Random Forest, and Gradient Boosting emerged as the top-performing models with R-squared values exceeding 98%.
- Ensemble Effect: Combining diverse models in an ensemble (e.g., XGBoost, Random Forest) contributed to robust and accurate predictions.
- Tree-Based Strength: Decision Tree and its ensemble variants (Random Forest, Extra Trees, Gradient Boosting) excelled in capturing non-linear relationships.
- Neural Network Evaluation: MLP achieved a respectable R-squared score, demonstrating its ability to model complex patterns.
- Linear Models: Ridge and Linear Regression demonstrated good performance, providing a baseline for comparison.

## Grid Search for XGBoost Hyperparameters
- Parameter grid explored includes variations in n_estimators, learning_rate, max_depth, min_child_weight, subsample, and colsample_bytree.
- Utilized negative mean squared error (neg_mean_squared_error) as the scoring metric.
- Employed 5-fold cross-validation to robustly evaluate model performance.
- Execution of Grid Search involved exploration of various combinations across the parameter grid.
- The best hyperparameters identified by Grid Search for optimal model performance are:
- - Learning Rate: 0.1
- - Max Depth: 4
- - Min Child Weight: 2
- - Number of Estimators: 100
- - Subsample: 0.9
- - Colsample_bytree: 1.0
- The identified best model incorporates these hyperparameter values, enhancing predictive accuracy.

## Final Model using XGBRegressor
#### Model Performance:
- R-squared Score: Achieved an impressive 98.87%, indicating strong predictive capability.
- Mean Absolute Error (MAE): Remarkably low at 0.0397, showcasing accurate predictions.
#### Precision Metrics:
- The model demonstrates high accuracy in capturing the variance in the target variable.
- Exceptionally low MAE emphasizes the minimal average prediction error.
#### Optimal Hyperparameters:
- Tuned XGBoost with carefully selected hyperparameters to achieve superior performance.
- Fine-tuned parameters include learning rate, maximum depth, and subsampling.
#### Scalability:
- The model's effectiveness remains consistent across different scales, ensuring robust performance.
