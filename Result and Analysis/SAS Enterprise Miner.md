# SA Enterprise Miner
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

## Please Refer To Report For Details
