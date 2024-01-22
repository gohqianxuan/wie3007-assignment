# Data Preprocessing using Talend Data Preparation & Talend Data Integration
Data cleaning and transformation were done using two platforms, Talend Data Preparation; a software that provides a graphical interface, allowing users to interact with the data visually and perform suggested transformations through a point-and-click approach, and Talend Data Integration; a software that enables users to design data integration jobs using a drag-and-drop approach, making it accessible to users without an extensive technical expertise.

## Workflow

1. **Data Cleaning**
* Loaded the merged dataset into Talend Data Preparation for processing.
* Removed rows with null values in the department column to maintain data integrity.
* Deleted the curr_size_of_product column as it was unnecessary for further analysis and it contained over 6000 null values. 
* Removed entries with a zero value in the quantity column, indicating invalid transactions.
* Imputed zero values in the sales_value column with the mean of the column to handle missing data without losing records.

2. **Data Transformation**
* Created a new discount column by aggregating retail_disc, coupon_disc, and coupon_match_disc columns to get the total discount.
* Modified the day column format to conform to the ISO 8601 standards for date representation.
* Merged day and trans_time into a single timestamp column in "yyyy-MM-dd HHmm" format for a consistent and precise temporal analysis using Talend Data Integration as it has date formatting functionalities.

## Refer to Report for Details and Visualization
https://365umedumy-my.sharepoint.com/:b:/g/personal/u2102822_siswa365_um_edu_my/ERT3kxFhScBHlP3ZHIqeSEsBgcBMQnVyras3BJrhVoWR7Q?e=oiCQNf
