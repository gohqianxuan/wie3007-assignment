# Data Integration and Feature Engineering
Data integration was done using *Talend Data Integration*; a software that enables users to design data integration jobs using a drag-and-drop approach, making it accessible to users without extensive technical expertise.

Feature engineering was done manually using *Talend Data Integration* and automatically using the *Featuretools library*; a library that aided in generating new features based on aggregation and transformation primitives. 

## Workflow

### Data Integration

1. **Schema Definition**
* Defined schemas for product, household, and transaction tables.

2. **Data Merging**
* Merged transaction and household tables using tMap.
* Enriched transaction data with household attributes.
* Combined enriched data with product table using product_id.

3. **Output Creation**
* Utilized tFileOutputDelimited to create a consolidated dataset file.

### Manual Feature Engineering

1. **Data Importation**
* Imported transactional data using tFileInputDelimited.
* Selected necessary columns with tFilterColumns.

2. **Aggregation**
* Performed aggregation by basket_id using tAggregateRow.
* Calculated sum of sales_value and discount.

3. **Deduplication and Transition**
* Ensured unique records with tUniqRow.
* Transitioned data using tHashOutput.

4. **Data Transformation**
* Mapped transactional and aggregated data in tMap.
* Created basket_sales_value and basket_discount fields.
* Outputted enhanced dataset with FileOutputDelimited.

### Automatic Feature Engineering

1. **Entities Definition**
* Defined the product, household and transaction entities from the merged dataset.
* Each entity represent one table.

2. **EntitySet Definition**
* Previous entities were included in the definition of entityset. 
* Defined the entityset, the primary keys of the entities and the relationships between them.

3. **Feature Matrix Creation**
* Generated new features using the Deep Feature Synthesis (DFS) function.
* Outputted the feature matrix from the DFS function to compile all the newly generated features based on the aggregation and transformation primitives. 

## Refer to Report for Details and Visualization
https://365umedumy-my.sharepoint.com/:b:/g/personal/u2102822_siswa365_um_edu_my/ERT3kxFhScBHlP3ZHIqeSEsBgcBMQnVyras3BJrhVoWR7Q?e=oiCQNf
