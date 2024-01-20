# DBSCAN
DBSCAN is employed for customer segmentation in the retail sector, enhancing targeted promotions. It's a density-based clustering algorithm, ideal when cluster count is uncertain.

**Workflow:**
**1. Data Import** 
CSV Reader imports sampled household_demographic data.

**2. Data Transformation** 
Category to Number node converts categorical columns to numerical.

**3. Normalization**  
Normalizer scales data between 0 and 1 using min-max normalization.

**4. Dimensionality Reduction**  
PCA reduces data to 3 dimensions for computational efficiency.

**5. Distance Calculation**  
Numeric Distances node uses Euclidean distances (PCA dimensions).

**6. DBSCAN Configuration**  
DBSCAN node set with Epsilon (0.4) and minimum points (5).

**7. Visualization**  
Color Manager node assigns colors to resulting clusters.
Scatter Plots visualize clusters in 3D with PCA dimensions.
Additional plots explore clusters based on demographic factors.

**Customer Segmentation** 
Clusters identified based on age, homeownership, marital status, income:
Cluster 0: Age 35-54, homeowner, middle income.
Cluster 1: Age 25-54, married, lower income, probable homeowner/renter, with kids.
Cluster 2: Age 35-54, single, homeowner, higher income.

**Marketing Strategies** 
Cluster 1: Target with lower-priced products, family packages.
Cluster 2: Focus on high-end products, tailor offerings for single individuals.

Heatmap nodes validate clusters using correlation between demographics and clusters.

# Refer to Report for Details and Visualization
https://365umedumy-my.sharepoint.com/:b:/g/personal/u2102822_siswa365_um_edu_my/ERT3kxFhScBHlP3ZHIqeSEsBgcBMQnVyras3BJrhVoWR7Q?e=oiCQNf
