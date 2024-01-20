# SAS Enterprise Miner
## Sample
We use SAS Enterprise Miner's Sample node to randomly select 4% (32 households) from the hh_demographics dataset. The chosen subset ensures a comprehensive analysis while managing computational resources effectively. A Random Seed (420) is set for reproducibility, and the process is documented for transparency and future reference.

## Explore
**Line Graph for Sales Trend**
- Represents sales trends over time.
- Identifies recurring patterns, seasonality, and emerging trends in customer behavior.
- Provides a foundation for informed decision-making and aligning strategies with consumer demand.

**Surface Plots**
- Illustrate interactions between sales values, transaction times, coupon discounts, and product-week numbers.
- Offer insights into customer behavior patterns related to discounts and product trends.
- Inform discount planning, marketing initiatives, and product-related strategies.

**Bar Charts for Demographic Composition**
- Provide insights into the demographic composition of households based on income levels.
- Optimize targeting strategies to align promotional efforts with specific demographic preferences.
- Enhance customer engagement and satisfaction.

**Scatterplot for Demographic Diversity**
- Depicts the distribution of households across income levels, age ranges, and household composition.
- Identifies potential target segments based on income and age demographics.
- Guides product and service tailoring to specific customer groups.

**Brand-Department-Commodity Plot**
- Visualizes relationships between categorical variables, helping identify market preferences or product groupings.
- Aids in effective product placement and business strategy within the manufacturing domain.

**Association Rule Mining**
- Establishes relationships between items through conditional statements.
- Utilizes the SAS Enterprise Miner's Association node for rule discovery.
- Lift values indicate the likelihood of purchasing one item when another is bought.
- Link Graph visually represents associations, aiding strategic decision-making.

**Sequence Analysis**
- Considers the ordering of relationships among items to understand purchasing behavior.
- Uses the SAS Enterprise Miner's Association node for sequential rule discovery.
- Provides insights into popular product sequences and supports strategic decision-making.

**Time Series Clustering**
- Groups similar sequences of data based on temporal patterns.
- Utilizes TS Data Preparation and TS Similarity nodes in SAS Enterprise Miner.
- Cluster analysis reveals segments of similar trends in sales across different households.
- Enables targeted business strategies based on identified clusters.


## Modify
<p>All features from association rule mining, sequential rule mining, time series clustering, and DBSCAN clustering are consolidated 
into the main dataset through SAS Enterprise Miner Merge node. Key configurations include matching by basket_id for association and sequential rule mining, 
incorporating time series clustering output after an initial merge with the TSIF Map Table, and merging DBSCAN cluster output based on household_key.</p>

## Model
The dataset is split into 80% for training and 20% for validation to evaluate model performance.

**Decision Tree (with Association Rule)**
- Target: basket_sales_value
- Underfit Tree: 2 branches, 5 depth, 500 category size, 500 leaf size, 500 split size.
- Best Fit Tree: 15 branches, 50 depth, 5 category size, 5 leaf size, 5 split size.
- Overfit Tree: 35 branches, 50 depth, 1 category size, 1 leaf size, 2 split size.

**Random Forest (with Sequential Rules)**
- Target: basket_sales_value
- Underfit Random Forest: 5 trees, 5 depth, 10 categories, 5 min category size.
- Best Fit Random Forest: 100 trees, 40 depth, 35 categories, 2 min category size.
- Overfit Random Forest: 150 trees, 50 depth, 50 categories, 2 min category size.

**Gradient Boosting (with DBSCAN Cluster)**
- Target: basket_sales_value
- Underfit Gradient Boosting: 10 iterations, 2 branches, 5 depth, 500 category size.
- Best Fit Gradient Boosting: 35 iterations, 15 branches, 50 depth, 5 category size, 100 categorical bins, 80 interval bins.
- Overfit Gradient Boosting: 60 iterations, 35 branches, 50 depth, 1 category size, 120 categorical bins, 120 interval bins.

**Forecasting Model (with Time Series Cluster)**
- Target: basket_sales_value
- Forecasting Method: TS Exponential Smoothing with best model from various models tried.
- Configuration: Interval set to Month, Forecast Lead of 6 months, Smooth Outliers enabled, and Best model selection based on Root Mean Square Error.

## Access
**Evaluation of Decision Tree**
- Best-fit Decision Tree outperformed underfit and overfit models.
- Best-fit model achieved ASE of 20.66 on the validation set, significantly better than underfit (1101.64) and overfit (29.04) models.

Score Rankings Overlay:
- Max Predicted basket_sales_value compared for different depths of decision trees.
- Best-fit and overfit models exhibit similar performance patterns.

Score Distribution:
- Mean Predicted vs. Mean Target values plotted against model score.
- Best-fit and overfit Decision Tree models show close alignment, accurately predicting basket sales values.
- Underfit model reveals a significant gap, indicating poor performance.

**Evaluation of Random Forest**
- Best-fit Random Forest outperformed underfit and overfit models.
- Best-fit model achieved ASE of 398.20, superior to underfit (2394.06) and overfit (400.28) models.

Score Rankings Overlay:
- Max Predicted basket_sales_value compared for different depths of random forests.
- Best-fit model demonstrates superior performance.

Score Distribution:
- Mean Predicted vs. Mean Target values plotted against model score.
- Underfit Random Forest displays poor performance, while best-fit and overfit models show similar trends.
- Best-fit model exhibits smaller gap, indicating better accuracy.

**Evaluation of Gradient Boosting**
- Best-fit Gradient Boosting outperformed underfit and overfit models.
- Best-fit model achieved ASE of 118.75, surpassing underfit (1531.46) and overfit (245.52) models.

Score Rankings Overlay:
- Mean Predicted basket_sales_value compared for different depth values.
- Best-fit and overfit models exhibit similar patterns.

Score Distribution:
- Mean Predicted vs. Mean Target values plotted against model score.
- Underfit model shows less accurate predictions, while best-fit model excels in accuracy.

**Evaluation of Forecasting**
- Mean Square Error: 134.13, Root Mean Square Error: 11.58145.
- Lower Mean Square Error indicates better model performance in capturing and predicting time series patterns.

Trend Analysis:
- Line graph illustrates the forecasted trend of basket_sales_value over a 6-month period.
- Consistent and regular pattern observed in the trend.
- Minimum sales in April, increasing thereafter, reaching maximum in March.


## Please Refer To Report For Details
https://365umedumy-my.sharepoint.com/:b:/g/personal/u2102822_siswa365_um_edu_my/ERT3kxFhScBHlP3ZHIqeSEsBgcBMQnVyras3BJrhVoWR7Q?e=dbgqy3
