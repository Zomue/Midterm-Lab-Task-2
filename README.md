
# Midterm Task 2 - Data Cleaning and Preparation using POWER QUERY 
This portfolio demonstrates the process of data preparation and cleaning uncleaned raw data using power query.

## Step 1: Download and Load Data
Download the dataset (Uncleaned_DS_jobs.csv)
Open Excel
Go to Data → New Query → Open File → Text/CSV
Click Load and then Edit using Power Query Editor
## Step 2: Duplicate Raw Data
Right-click the dataset in the Queries pane
Select Duplicate
## Step 3: Clean Salary Data
Select the Salary Estimate column
Go to Transform Menu → Extract → Text Before Delimiter
Type “(“ and click OK
Create two new columns: Min Salary and Max Salary
Select Salary Estimate column → Add Column Menu → Column from Examples → From Selections
Type the first min salary value and press Enter (all rows will auto-fill)
Rename the column to “Min Sal”
Repeat the process for Max Salary
## Step 4: Add Role Type Column
Go to Add Column Menu → Custom Column
Rename the column to “Role Type”
Use this logic:
If Job Title contains “Data Scientist” → Assign “Data Scientist”
If Job Title contains “Data Analyst” → Assign “Data Analyst”
If Job Title contains “Data Engineer” → Assign “Data Engineer”
If Job Title contains “Machine Learning” → Assign “Machine Learning Engineer”
Otherwise, assign “Other”
Change the column type to Text
## Step 5: Split Location Column
Select the Location column
Add a Custom Column with corrections:
If Location = “New Jersey” → Assign “, NJ”
If Location = “Remote” or “United States” → Assign “, Other”
If Location = “Texas” → Assign “, TX”
If Location = “California” → Assign “, CA”
Click OK, then select the new column
Go to Transform → Split Column → By Delimiter (comma “,”)
Click OK
Rename the second split column to “State Abbreviations”
Check and replace incorrect values (e.g., “Anne Rundell” → “MA”)
## Step 6: Split Size Column
Create two new columns: MinCompanySize and MaxCompanySize
Use the same method as Salary Estimate to split values
## Step 7: Handle Negative Values
Filter out -1s from the Competitors column
Filter out 0s from the Revenues column
Remove -1s from the Industry column
## Step 8: Clean Company Names
Remove any extra characters or ratings after company names
## Step 9: Copy Cleaning Steps as Proof
Go to Home Menu → Click Advanced Editor
Copy and save the code in your portfolio
## Step 10: Reshape and Group Data
Group by Role Type
Duplicate the raw data → Rename it as “Sal By Role Type dup”
Select only Role Type, Min Salary, and Max Salary columns
Change Min and Max Salary type to currency
Multiply values by 1000 (Numbers Column → Standard → Multiply → Type 1000)
Group rows by Role Type and get the average for Min and Max Salary
Group by Company Size
Create a reference of raw data → Rename it as “Sal By Role Size ref”
Select only Size, Min Salary, and Max Salary columns
Change Min and Max Salary type to currency
Multiply values by 1000
Group rows by Size and get the average for Min and Max Salary
## Step 11: Merge State Mapping
Click Unclean DS Jobs
Right-click in the Queries pane → New Query → Open Workbook State Mapping
Select the columns and click OK
Select Uncleaned DS Jobs query
Choose the State Abbreviation column in both queries
Click Merge → Click OK
Rename the merged column as “State Full Name”
Remove nulls and blanks
## Step 12: Group by State
Create a reference of raw data → Rename it as “Sal By State ref”
Select only State Full Name, Min Salary, and Max Salary columns
Change Min and Max Salary type to currency
Multiply values by 1000
Group rows by State Full Name and get the average for Min and Max Salary
## Step 13: View Query Dependencies
Go to View Menu → Click Dependencies
Check if all queries are correctly linked
## Here’s the screenshots before data cleaning.
![image](https://github.com/user-attachments/assets/fd6473b7-1ccd-45ad-98bc-10e24cd1df13)

## Here’s the screenshots when I started data cleaning.
![image](https://github.com/user-attachments/assets/b56f819e-e828-419d-926b-3c3fc03b4367)

## Here’s the screenshots of Advanced Editor.
![image](https://github.com/user-attachments/assets/f18bcf85-8953-4644-aa8a-b41d9dc16b32)

## Here’s the screenshot of Sal By Role type.
![image](https://github.com/user-attachments/assets/d808dc98-5019-4d59-9598-47a273d9f7d7)

## Here’s the screenshot of Sal By Size.
![image](https://github.com/user-attachments/assets/6056c066-f293-4d6c-b465-ef5608585dd2)

## Here’s the screenshot of the States.
![image](https://github.com/user-attachments/assets/4082e7f9-3023-41a8-8c27-e1fbf3c92e39)

## Here’s the screenshot of Sal By State.
![image](https://github.com/user-attachments/assets/ec67d4d8-f777-4ae5-9610-2fee1ad2f4b9)

## Here’s the screenshot of the Query Dependencies.
![image](https://github.com/user-attachments/assets/52341fa8-aa5a-4a4b-a374-eb1d7075ea95)


[BACK TO PORTFOLIO](https://zomue.github.io/)
