# ML-DataDrivenChallange


**Introduction :**

> There are 4 data sets that have been given in the competitions.
- Submission Format
- Test set values
- Training set labels
- Training set values

> Target variable has three possible outcomes.
- Functional
- Non-functional
- Functional but needs repair

**Data Preprocessing:**

1. Removed the columns that have similar features with other features.
      - quantity_group
      - source_class
      - source_type
      - quality_group
      - payment_type
      - extraction_type_class
      - extraction_type
      - waterpoint_type_group
      - management_group
      - scheme_management

2. In the construction_year feature, there were ‘0’ in sum rows. So it was replaced by the median value, ‘1986’. Also there were different numbers of values for that. So they were summarised into decades.
3. The records were recorded by the same person. It is in the ‘recorder_by’ column. Since the value is the same, it was dropped.
4. In the column ‘ installer’, there were
      - Unknown cells and empty cells → made all as ‘unknown’
      - Same content but with spell errors → change those cells into same spellings
	> Then, other than the first 16 highest count installers, others were named as ‘other’.
5. In the column ‘funder’, 
      - Empty cells and ‘not known’ cells were changed into ‘Unknown’.
      - Other than the first 19 highest count funders, others were named as ‘other’.
6. Drop the columns which have many different values. So, those columns were dropped.
	- wpt_name
	- scheme_name
	- region_code
	- amount_tsh
	- num_private
	- subvillage
	- id
7. Filled the missing values in population column with its mean value (180) 
8. Filled the missing values in permit and public_meeting columns
9. Dropped the columns which are called funder, installer, construction_year , lga and ward. Finally used 20 columns to model training.
	- days_since_recorded 
	- gps_height 
	- longitude 
	- latitude 
	- basin 
	- region 
	- district_code 
	- population 
	- public_meeting 
	- permit 
	- extraction_type_group 
	- management 
	- payment 
	- water_quality 
	- quantity 
	- source 
	- waterpoint_type 
	- decade 
	- installer_cat 
	- funder_cat
10. One hot encoding is applied for the following categorical features.
	- funder_cat
	- basin
	- installer_cat
	- public_meeting
	- scheme_management
	- permit
	- extraction_type
	- extraction_type_class
	- management
	- payment_type
	- quality_group
	- quantity
	- source
	- source_class
	- waterpoint_type

**Accuracy:**

> By dividing the training data set into two parts, calculate the accuracy of the used model.

**Modeling :**

> RandomForest and DecisionTree models are tried. RandomForest gave the best score.

**High Score - 0.8162**

**Rank - 1844**
