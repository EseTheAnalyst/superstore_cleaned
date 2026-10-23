DATASET OVERVIEW 

This project uses a superstore retail sales dataset containing 10,704 rows and 21 columns. Each 
row represents an order line item, covering sales transactions, customers, products, discounts, 
and profitability. 

Key fields include: Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Segment, Region, 
Product ID, Category, Sub-Category, Sales, Quantity, Discount, and Profit. 
The dataset provides a foundation for analyzing sales performance, profitability, customer behavior, 
product trends, and the impact of discounts on profit. 

CLEANING AIM 

The aim of this cleaning exercise was to prepare the dataset for reliable analysis by: 
* Duplicating the Dataset 
* Initial Dataset Inspection 
* Duplicate Detection and Removal 
* Identifying and Handling Missing values 
* Removing Extra Spaces 
* Standardizing and Correcting text and categorical values 
* Validating Numerical and Data Types 
* Date Standardization 
* Identifying Data-entry errors  
* Checks for Outliers 
* Final Data Validation

1. DUPLICATE DATASET
   
The dataset was first duplicated and renamed to ensure integrity of the original data before cleaning 
can commence.

2. INITIAL DATASET INSPECTION
   
The dataset was reviewed to understand its structure, columns, data types, and the general quality 
of the data before making any changes. 
The initial inspection focused on: 
* Identifying duplicate records 
* Checking for missing values 
* Checking for unnecessary spaces 
* Identifying inconsistent text and spelling 
* Checking whether numerical values were stored consistently 
* Identifying incorrect date formats 
* Checking for errors 
* Checking for potential outliers
  
3. DUPLICATE DETECTION & REMOVAL
  
To identify duplicate entries, a new column named Duplicate Checker was created using a 
combination of IF and COUNTIF functions to flag unique versus duplicate records based on Row ID. 
The column was then filtered to isolate duplicate entries, revealing that rows sharing the same Row 
ID corresponded to identical, corresponding order entries. COUNTIF was used to quantify the 
extent of duplication, identifying 1,018 duplicate occurrences. 
After manually verifying that these entries were true duplicates (rather than legitimate repeat 
transactions), the Remove Duplicates function was applied to eliminate 509 redundant rows, and 
the duplicate checker column was deleted, ensuring a clean and accurate dataset for analysis. 

4. IDENTIFYING AND HANDLING MISSING VALUES
   
The dataset was checked for missing or blank values. 
Empty spaces were identified and replaced with NULL where appropriate to clearly distinguish 
missing information from valid data. 
This helped ensure that missing values could be handled consistently during the analysis stage. 

5. REMOVING EXTRA SPACES
   
Text fields were checked for unnecessary spaces that could cause inconsistencies when filtering, 
sorting, or performing calculations. 
The TRIM function was used to remove unwanted spaces from text values. 
The cleaned columns were then reviewed using filtering to confirm that the values had been 
standardized correctly.

6. STANDARDIZING AND CORRECTING TEXT AND CATEGORICAL VALUES
   
Text values were reviewed for spelling errors and inconsistent naming in all text fields. 
For example, inconsistent values in the Segment column were identified and standardized to 
consistent categories such as: 
* Consumer 
* Corporate 
Where abbreviated or incorrectly entered versions of these categories existed, they were corrected 
to the appropriate standardized value using the FIND AND REPLACE function. 
This was important because inconsistent text values can cause the same category to be treated as 
different categories during analysis.

7. VALIDATING NUMERICAL AND DATA TYPES
   
Numerical columns were checked to ensure that numbers were stored consistently and could be 
used correctly for calculations. 
The data was reviewed for values that may have been stored as text instead of numbers or 
otherwise formatted inconsistently. 
The ISTEXT and ISNUMBER functions were used to identify values in the Sales and Profit columns 
that were stored as text instead of numbers. 
A total of 5,824 data-type issues were identified in the Sales column, while 4,226 were identified in 
the Profit column. These issues were corrected using Excel’s Number Format to convert the values 
to numerical format. 
This ensured that the Sales and Profit columns could be correctly used for calculations and 
analysis.

8. DATE STANDARDIZATION
    
The dataset contained dates in several different formats. 
Examples identified during the cleaning process included: 
* 4-Jan-23 
* 13.04.2023 
* 18/04/2023 00:00:00 
* 18/04/2023 
* 20231304 
These dates were converted into a consistent date format: 
MM-DD-YYYY 
Standardizing the dates ensured that the entire date column could be properly sorted, filtered, 
compared, and used for time-based analysis.

9. IDENTIFYING DATA ENTRY ERRORS
    
After the initial cleaning steps, the dataset was reviewed for remaining errors. 
The cleaned data was examined for: 
* Incorrect values 
* Inconsistent categories 
* Formatting problems 
* Invalid dates 
* Unexpected entries 
* Remaining duplicate records 
The purpose of this step was to make sure that errors introduced or overlooked during the earlier 
cleaning stages were identified before analysis.

10. CHECKS FOR OUTLIERS
    
The dataset was also checked for potential outliers. 
Unusually high or low values were examined to determine whether they represented: 
* Genuine observations 
* Data-entry errors 
* Formatting issues 
* Values requiring further investigation 
Potential outliers were reviewed rather than automatically removed, since an unusual value does 
not necessarily mean that the value is incorrect.

11. FINAL DATA VALIDATION
    
After completing the cleaning process, the dataset was reviewed again to confirm that the cleaning 
steps had been applied correctly. 
The final validation included: 
* Rechecking duplicate records 
* Confirming missing values were handled appropriately 
* Checking standardized text categories 
* Confirming numerical values were correctly formatted 
* Confirming dates followed the standardized format 
* Reviewing errors and potential outliers 
The cleaned dataset was then considered ready for the analysis stage.

CLEANING WORKFLOW 

DATASET DUPLICATION → INITIAL DATASET INSPECTION → DUPLICATE DETECTION & 
REMOVAL → IDENTIFYING AND HANDLING MISSING VALUES → REMOVING EXTRA SPACES 
→ STANDARDIZING AND CORRECTING TEXT AND CATEGORICAL VALUES → VALIDATING 
NUMERICAL AND DATA TYPES → DATE STANDARDIZATION → IDENTIFYING DATA ENTRY 
ERRORS → CHECKS FOR OUTLIERS → FINAL DATA VALIDATION 

DATA QUALITY ISSUES AND ACTIONS TAKEN 

| Data Quality Issue | Action Taken |
|--------------------|--------------|
| 1,018 duplicate occurrences | Verified and removed 509 redundant rows |
| 14,765 missing/blank values | Reviewed and handled using Find & Replace to replace blank spaces with NULL |
| Extra spaces in text fields | Removed using TRIM |
| 494 inconsistent and incorrect text entries in the Segment column | Standardized using Find & Replace |
| Inconsistent date formats in the Order Date column | Converted to a standardized format |
| 5,824 numerical data-type issues in the Sales column | Checked using ISTEXT and ISNUMBER, fixed using Number Format to convert to numbers |
| 4,226 numerical data-type issues in the Profit column | Checked using ISTEXT and ISNUMBER, fixed using Number Format to convert to numbers |
 
CLEANING IMPACT 

| Metric | Before Cleaning | After Cleaning |
|--------|-----------------|----------------|
| Rows | 10,704 | 10,195 |
| Columns | 21 | 21 |
| Duplicate occurrences | 1,018 | 0 |
| Redundant records | 509 | 0 |
| Missing/blank values | 14,765 | Replaced with NULL |
| Date formats | Inconsistent | Standardized |
| Text inconsistencies | 494 | 0 |
| Data type issues | 10,050 | 0 |
 
 
 TOOLS USED 
    * Microsoft Excel 
    * IF 
    * COUNTIF 
    * TRIM 
    * CELL 
    * ISTEXT 
    * ISNUMBER 
    * Filtering 
    * Sorting 
    * Find & Replace 
    * Date formatting 
    * Text to Columns 
    * Remove Duplicates
