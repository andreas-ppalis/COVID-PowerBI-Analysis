# COVID-PowerBI-Analysis

This project presents a detailed dashboard analyzing vaccination activity and rapid testing patterns across various countries using a simulated dataset. It leverages Power BI, DAX calculations, and clear visual storytelling to uncover insights on:

- Vaccine types and usage
- Rapid test outcomes (positive/negative)
- Test and vaccination centers
- Citizen demographics and vaccination events

Dataset Overview

The data consists of dimension tables and fact tables stored in Excel files and folders:

Dimensions (dimensions.xlsx)

Citizens: Unique social ID, name, email, gender, DOB, nationality code.
Rapid Test Centers: Center ID and name.
States: Unique state names and codes.
Vaccination Centers: Center ID and name.
Vaccines: Vaccine ID, name, and type (e.g., mRNA, viral vector).

Facts (/facts folder)

National Plans: Vaccine availability per center and date. Key: vaccineCode + centerCode + date.
Vaccinations: Administered vaccines per citizen. Key: vaccineCode + centerCode + date + socialID.
Rapid Tests: Test events per citizen with outcomes.

Additionally, the file Snippets.txt contains useful DAX measures and column definitions used in the report.


Data Preparation & Modeling Steps

1. Load all data into Power BI (dimension and fact tables).
2. Verify and set correct column data types.
3. Create a calendar table with a dateKey column.
4. Handle nulls:
Replace null in emails with "Not Available".
Replace null in middle names with an empty string "".
5. Add dateKey columns to all fact tables containing dates.
6. Generate a unique ID for National Plan Vaccination entries: vaccineCode & "-" & centerCode & "-" & dateKey.

DAX Measures & Calculated Columns
- Citizen Age: Custom column based on birthdate.
- Weekend Flag: Identifies weekends in the calendar table.
- Month Name: Adds abbreviated month labels.
- NoOfCitizensPerDate: Calculates how many citizens were born on each date.
