
  

# Data Quality Framework Governance (DQFG)
  

**Data Quality Framework Governance** is a structured approach to assessing, monitoring, and improving the quality of data. An effective **Data Quality Framework** considers these dimensions and integrates them into a structured approach to ensure that data serves its intended purpose, supports informed decision-making, and maintains the trust of users and stakeholders.

**Data Quality** is an ongoing process that requires continuous monitoring, assessment, and improvement to adapt to changing data requirements and evolving business needs.


**Example:** To call functions from the library.

	from DataQualityFrameworkGovernance import Uniqueness as uq
	print(uq.duplicate_rows(dataframe))


**Library structure**

****
  

<details open>
<summary><b>Accuracy</b></summary>

<ul>

<details>
<summary><i>accuracy_tolerance_numeric</i></summary>

Calculating data quality accuracy of a set of values (base values) by comparing them to a known correct value (lookup value) by setting a user-defined tolerance percentage, applicable for numeric values.

	from  DataQualityFrameworkGovernance  import  Accuracy as ac
	print(ac.accuracy_tolerance_numeric(dataframe, 'base_column', 'lookup_column', tolerance_percentage))

</details>

<details>
<summary><i>email_pattern</i></summary>

Validating accuracy of email addresses in a dataset by verifying that they follow a valid email format.

	from  DataQualityFrameworkGovernance  import  Accuracy as ac
	print(ac.email_pattern(dataframe,'email_column_name'))

</details>

<details>
<summary><i>filter_number_range</i></summary>

Number range ensures that data values are accurate and conform to expected values or constraints. It is applicable to a variety of contexts, including exam scores, weather conditions, pricing, stock prices, age, income, speed limits for vehicles, water levels, and numerous other scenarios.

	from  DataQualityFrameworkGovernance  import  Accuracy as ac
	print(ac.filter_number_range(dataframe, 'range_column_name', lower_bound, upper_bound))

	Example:
	print(ac.filter_number_range(df, 'Age', 4, 12))
	(Output will extract the age between 4(lower bound) and 12 (upper bound) from column 'Age' in the dataset 'df')

</details>

<details>
<summary><i>filter_datetime_range</i></summary>

The datetime range filter guarantees the accuracy and adherence of data values to predetermined criteria or constraints. It is applicable to a variety of contexts, including capturing outliers in date of birth, age and many more.

	from  DataQualityFrameworkGovernance  import  Accuracy as ac
	print(ac.filter_datetime_range(Dataframe, 'range_column_name', 'from_date', 'to_date', 'date_format'))

	Example:
	print(ac.filter_datetime_range(df, 'Date', '2023-01-15', '2023-03-01', '%Y-%m-%d'))

**Important**: Specify date format in *'%Y-%m-%d %H:%M:%S.%f'*  ***(It can be specified in any format, parameter value to be aligned appropriately).***

</details>

</ul>
</details>

<details open>
<summary><b>Completeness</b></summary>

<ul>

<details>
<summary><i>missing_values</i></summary>

Summary of missing values in each column.

	from  DataQualityFrameworkGovernance  import  Completeness as cp
	print(cp.missing_values(dataframe))

</details>

<details>
<summary><i>overall_completeness_percentage</i></summary>

Percentage of missing values in a DataFrame. 

  
	from  DataQualityFrameworkGovernance  import  Completeness as cp
	print(cp.overall_completeness_percentage(dataframe))

</details>

</ul>
</details>

<details open>
<summary><b>Consistency</b></summary>

<ul>

<details>
<summary><i>start_end_date_consistency</i></summary>

If data in two columns is consistent, check if the "Start Date" and "End Date" column are in the correct chronological order. 

  
  	from  DataQualityFrameworkGovernance  import  Consistency as ct
	print(ct.start_end_date_consistency(dataframe, 'start_date_column_name', 'end_date_column_name', 'date_format'))

**Important**: Specify date format in *'%Y-%m-%d %H:%M:%S.%f'*  ***(It can be specified in any format, parameter value to be aligned appropriately).***

</details>


<details>
<summary><i>count_start_end_date_consistency</i></summary>

Count of data in two columns is consistent, check if the "Start Date" and "End Date" column are in the correct chronological order. 

  
  	from  DataQualityFrameworkGovernance  import  Consistency as ct
	print(ct.count_start_end_date_consistency(dataframe, 'start_date_column_name', 'end_date_column_name', 'date_format'))
  
**Important**: Specify date format in *'%Y-%m-%d %H:%M:%S.%f'*  ***(It can be specified in any format, parameter value to be aligned appropriately).***

</details>

</ul>
</details>
  

<details open>
<summary><b>Uniqueness</b></summary>

<ul>

<details>
<summary><i>duplicate_rows</i></summary>

Identify and display **duplicate** rows in a dataset. 

  
	from  DataQualityFrameworkGovernance  import  Uniqueness as uq
	print(uq.duplicate_rows(dataframe))

</details>

<details>
<summary><i>unique_column_values</i></summary>

Display **unique column values** in a dataset. 

	from  DataQualityFrameworkGovernance  import  Uniqueness as uq
	print(uq.unique_column_values(dataframe, 'column_name'))

</details>

<details>
<summary><i>unique_column_count</i></summary>

Count **unique column values** in a dataset. 

	from  DataQualityFrameworkGovernance  import  Uniqueness as uq
	print(uq.unique_column_count(dataframe, 'column_name'))

</details>

</ul>
</details>


<details open>
<summary><b>Validity</b></summary>

<ul>

<details>
<summary><i>validate_age</i></summary>

Validate age based on the criteria in a dataset. 

  	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.validate_age(dataframe, 'age_column', min_age, max_age))

</details>

<details>
<summary><i>validate_age_count</i></summary>

Count age based on the criteria in a dataset. 

  	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.validate_age_count(dataframe, 'age_column', min_age, max_age))

</details>

<details>
<summary><i>is_within_range</i></summary>

If all values in a given array list are present in a specific column of a dataset then it provides a status message indicating whether all names are found or not. **Array values must be within square brackets.**

  	#Examples
  	#array list = ["Tom", "Jerry", "Donald"] - Text
	#array list = [10, 20, 30] - Numeric
	#array list = [True, False] - Boolean
	#array list = [0, 1] - Flag

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_within_range(dataframe, 'column_name_to_look', [array_list]))

</details>

<details>
<summary><i>is_number_in_column</i></summary>

 Examines each value in a **column** and appends a new column to the existing column, indicating whether the values are numeric.

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_number_in_column(dataframe, 'column_name'))

</details>

<details>
<summary><i>is_number_in_dataset</i></summary>

Examines each value in a **dataset** and appends a new column for each existing column, indicating whether the values are numeric.

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_number_in_dataset(dataframe))

	#Example for specific column selection
	is_number_in_dataset(dataframe[['column1','column7']])

</details>

<details>
<summary><i>is_text_in_column</i></summary>

 Examines each value in a **column** and appends a new column to the existing column, indicating whether the values are text. **Result would be false, if text or string contains number.**

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_text_in_column(dataframe, 'column_name'))

</details>

<details>
<summary><i>is_text_in_dataset</i></summary>

Examines each value in a **dataset** and appends a new column for each existing column, indicating whether the values are text. **Result would be false, if text or string contains number.**

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_text_in_dataset(dataframe))

	#Example for specific column selection
	is_text_in_dataset(dataframe[['column1','column7']])

</details>

<details>
<summary><i>is_date_in_column</i></summary>

 Examines each value in a **column** and appends a new column to the existing column, indicating whether the values are in date time, in a speciifed format.

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_date_in_column(dataframe,'column_name', date_format))

**Important**: Specify date format in *'%Y-%m-%d %H:%M:%S.%f'*  ***(It can be specified in any format, parameter value to be aligned appropriately).***

</details>

<details>
<summary><i>is_date_in_dataset</i></summary>

 Examines each value in a **dataset** and appends a new column for each existing column, indicating whether the values are in date time, in a speciifed format.

	from  DataQualityFrameworkGovernance  import  Validity as vl
	print(vl.is_date_in_dataset(dataframe, date_format))

	#Example for specific column selection
	is_date_in_dataset(dataframe[['column1','column7']], date_format='%Y-%m-%d')

**Important**: Specify date format in *'%Y-%m-%d %H:%M:%S.%f'*  ***(It can be specified in any format, parameter value to be aligned appropriately).***

</details>

</details>


</ul>
</details>

</ul>
</details>

<details open>
<summary><b>Datastats</b></summary>

<ul>

<details>
<summary><i>count_rows</i></summary>

Count the number of rows in a DataFrame. 
  
  	from  DataQualityFrameworkGovernance  import  Datastats as ds
	print(ds.count_rows(dataframe))

</details>

<details>
<summary><i>count_columns</i></summary>

Count the number of columns in a DataFrame. 

    
  	from  DataQualityFrameworkGovernance  import  Datastats as ds
	print(ds.count_columns(dataframe))

</details>

<details>
<summary><i>count_dataset</i></summary>

Count the number of rows & columns in a DataFrame. 
    
  	from  DataQualityFrameworkGovernance  import  Datastats as ds
	print(ds.count_dataset(dataframe))

</details>

<details>
<summary><i>limit_max_length</i></summary>

 Limits the maximum length of a string to specific length. Example, when applied to the input string 'ABCDEFGH', the function returns 'ABCDE', effectively truncating the original string to the first 5 characters.
    
  	from  DataQualityFrameworkGovernance  import  Datastats as ds
	print(ds.limit_max_length(dataframe, column_name, start_length, length))

	#Example: 'ABCDEFGH' input string returns 'ABCDE'
	print(limit_max_length(df,'column_name',0,5))

</details>

</ul>
</details>


<details open>
<summary><b>Data Interoperability</b></summary>

<ul>

<details>
<summary><i>data_migration_reconciliation</i></summary>

**Data migration reconciliation** is a crucial step in ensuring the accuracy and integrity of data transfer between a source and target system. The process involves comparison of the source and target data to identify any disparities. If the columns in both datasets differ, the process returns an ouput to align the source and target dataset. 

**Output of column name mismatch**
| Column | MatchStatus | TableLocation |
|--|--|--|
| Department | Unmatched | Source |
| Departmentt | Unmatched | Target |
| EmployeeID | Matched | NotApplicable |

After structural alignment is confirmed, a comprehensive check is performed by comparing the content of each column. Any inconsistencies between the source and target data are flagged as mismatches. This includes the identification of specific 'column name(s)' where discrepancies occur, 'row number or position' and 'mismatched records' in both the source and target datasets. This comprehensive reporting ensures that discrepancies can be easily located and addressed, promoting data accuracy and the successful completion of the migration process.

  	from  DataQualityFrameworkGovernance  import  Interoperability as io
	print(io.data_migration_reconciliation(source_dataframe, target_dataframe))

	#Example of saving source and target dataframe from csv file

	import pandas as pd
	source_dataframe = pd.read_csv('source_data.csv')
	target_dataframe = pd.read_csv('target_data.csv')

**Result**
| Column | Row no. / Position |Source Data |Target Data |
|--|--|--|--|
| Column name | 2 | 33 | 3 |
| Column name | 289 | Donald Trump | Donald Duck |  

</details>

<details>
<summary><i>data_integration_reconciliation</i></summary>

**Data integration reconciliation** involves combining data from different sources into a unified view. This function compares two datasets, source_dataset and target_dataset, based on a unique identifier, ID. It checks for disparities in each column, cell by cell, between the two datasets. For each mismatch, it identifies the specific column and provides a status of "Matched" or "Mismatched." If the columns in both datasets differ, the process returns an ouput to align the source and target dataset. 

**Example output of column name mismatch**
| Column | MatchStatus | TableLocation |
|--|--|--|
| Department | Unmatched | Source |
| Departmentt | Unmatched | Target |
| EmployeeID | Matched | NotApplicable |

After structural alignment is confirmed, a comprehensive check is performed by comparing the content of each column. Any inconsistencies between the source and target data are flagged as mismatches.

**Parameters:**

**source_dataset:** The source dataset, a DataFrame containing the data to be compared.
**target_dataset:** The target dataset, a DataFrame containing the data to be compared against the source dataset
**ID**: A unique identifier column present in both datasets, used to match rows between the two datasets.

**Return Value:**

**status:** A string indicating the overall comparison status, either "Matched" or "Mismatched."
**mismatched_columns:** A list of columns that have mismatches between the two datasets.

	import pandas as pd
  	from  DataQualityFrameworkGovernance  import  Interoperability as io

	source_dataset = pd.DataFrame({
		'Ordinal': [54, 55, 56, 57],
		'Name': ['Theresa May','Boris Johnson', 'Liz Truss', 'Rishi Sunak'],
		'Monarch': ['Elizabeth II', 'Elizabeth II', 'Elizabeth II & Charles III', 'Charles III']
		})

	target_dataset = pd.DataFrame({
		'Ordinal': [55, 56, 57],
		'Name': ['Boris Johnson', 'Liz Truss', 'Rishi Sunak'],
		'Monarch': ['Elizabeth II', 'Elizabeth II', 'Charles III']
		})

	comparison_results = io.data_integration_reconciliation(source_dataset, target_dataset, 'Ordinal')
	print(comparison_results)


**Result**
| Ordinal | Status | Mismatched_Columns | MergeStatus | Name_source | Name_target | Monarch_source | Monarch_target |
|--|--|--|--|--|--|--|--|
|54|Mismatch|Name, Monarch|left_only|Theresa May|NaN|Elizabeth II|NaN|
|56|Mismatch|Monarch|both| Liz Truss| Liz Truss|Elizabeth II & Charles III|Elizabeth II|
|55|Match|None|both|Boris Johnson|Boris Johnson|Elizabeth II|Elizabeth II|
|57|Match|None|both|Rishi Sunak|Rishi Sunak|Charles III|Charles III|

</details>

<details>
<summary><i>data_consolidation</i></summary>

**Data consolidation** is a process of combining information from multiple datasets to create a unified dataset. This function with three parameters – dataset1, dataset2, and a parameter to determine consolidation direction (0 for rows ,1 for columns), users can choose between consolidating data by rows or columns.

**Compile by Rows (0):**

When choosing compile=0, the function will stack the datasets vertically, effectively appending the rows of dataset2 beneath the rows of dataset1.

**Compile by Columns (1):**

Alternatively, selecting compile=1 will concatenate the datasets side by side, merging columns from dataset2 to the right of those from dataset1.

  	from  DataQualityFrameworkGovernance  import  Interoperability as io

	CompileByColumns = io.data_consolidation(df1, df2,1)
	CompileByRows = io.data_consolidation(df1, df2,0)

</details>

</ul>
</details> 

****

**Supporting python libraries:**
  

- Pandas
- re
  

****

[Homepage](https://github.com/RajithPrabakaran/DataQualityFrameworkGovernance)

[Bug Tracker](https://github.com/RajithPrabakaran/DataQualityFrameworkGovernance/issues)  

[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
