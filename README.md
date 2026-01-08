# Assigning Ethnic, Voter and Income Characteristics to NYC's City Council Districts
This repository includes code that cleans and assigns data about people to NYC City Council Districts. This work supports the online, nonprofit newsroom THE CITY's "Get to Know Your City Council District" [news app](https://www.thecity.nyc/2025/12/10/nycha-rad-pact-boulevard-linden-violations/). The news app was originally published in 2023 and updated mid-2025. 

## Data
#### This analysis uses three data sources:

1. 2023 5-Year Census American Community Survey:
    - B04006 | People Reporting Ancestry
    - B03001 | Hispanic Or Latino Origin By Specific Origin
    - B02018 | Asian Alone By Selected Groups

#### After downloading, follow these steps to clean the files:
- Rename the zipped folders and data files. 
- Do a TEXTSPLIT() of the "Geography" column on "US" and of the "Geographic Area Name" column on ";". 
- Clean up the columns so that you have just the census tracts and county names remaining from the step above.
- Filter for only Bronx, Richmond, Queens, Kings and New York County. Paste the selection onto another sheet. You should be left with 2,327 rows, which equals the number of census tracts in NYC. 
- Rename the columns, remove the margin of error columns, and correct the data types of each column.
- Optional: Get rid of columns in the cleaned sheet that wouldn't be useful in the actual analysis (e.g. 'Other Groups' or 'Not Specified'), but keep them in the raw sheets.

## Pre-requisites
The pact-env folder includes all packages needed to complete this analysis.

## Methodology


#### kyd_ethnic_pop.ipynb
- Read in the Asian, Hispanic and Ancestry Census files (already manually cleaned)
- Reshape, or "melt" each dataframe so that the data is in a format we can analyze
- Combine all of the data together, so that we have a column for Census Tract, Ethnicity and Count. 
- Perform a series of groupings to get the "top" ethnic group in each tract (i.e. group with the highest population count). 
- Save to file
#### 2_violations.ipynb
- Read RAD addresses file and housing code violations file
- Clean violations file
- Merge to the two files together on address and borough columns
- Perform analysis
#### 3_omo.ipynb
- Read RAD addresses file and omo charges file
- Clean charges file
- Merge to the two files together on address and borough columns
- Perform analysis
#### 4_leftovers.ipynb
- This file is not part of the final analysis. It includes code used in previous iterations of this analysis that I'd like to save and reference in the future. 

## Licensing
All code in this repository is available under the MIT License. The data file in the output/ directory is available under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?
Contact Mia Hollie at mhollie@thecity.nyc.

