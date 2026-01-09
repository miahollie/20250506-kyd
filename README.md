# Assigning Ethnic, Voter and Income Characteristics to NYC's City Council Districts
This repository includes code that cleans and assigns data about people to NYC City Council Districts. This work supports the online, nonprofit newsroom THE CITY's "Get to Know Your City Council District" [news app](https://www.thecity.nyc/2025/12/10/nycha-rad-pact-boulevard-linden-violations/). The news app was originally published in 2023 and updated mid-2025. 

## Data
#### This analysis uses eight data sources:

1. 2023 5-Year Census American Community Survey:
    - B04006 | People Reporting Ancestry
    - B03001 | Hispanic Or Latino Origin By Specific Origin
    - B02018 | Asian Alone By Selected Groups
2. [2024 Presidential General Election Results](https://www.vote.nyc/page/election-results-summary-2024)
3. [2022 New York State Gubernatorial General Election Results](https://www.vote.nyc/page/election-results-summary-2022)
4. [2021 New York City Local General Election Results](https://www.vote.nyc/page/election-results-summary-2021)
5. [February 2025 Enrollment by County](https://elections.ny.gov/enrollment-election-district?q=/enrollment-election-district%3Fq%3D/enrollment-election-district%3Fq%3D/enrollment-election-district%3Fq%3D/enrollment-election-district%3Fq%3D/enrollment-election-district%3F/enrollment-election-district%3D&%2Fenrollment-election-district=&f%5B0%5D=filter_term%3A601)
6. [November 2024 Enrollment by County](https://elections.ny.gov/enrollment-election-district?q=/enrollment-election-district%3F/enrollment-election-district%3D&%2Fenrollment-election-district=&f%5B0%5D=filter_term%3A571)
7. [November 2022 Enrollment by County](https://elections.ny.gov/enrollment-election-district?q=/enrollment-election-district%3Fq%3D/enrollment-election-district%3Fq%3D/enrollment-election-district%3F/enrollment-election-district%3D&%2Fenrollment-election-district=&f%5B0%5D=filter_term%3A281)
8. [November 2021 Enrollment By County](https://elections.ny.gov/enrollment-election-district?f[0]=filter_term%3A286&page=0)

## Pre-requisites
The kyd-env folder includes all packages needed to complete this analysis.

## Methodology

#### 1_crosswalk.ipynb
- Create crosswalks that connect various periods of time to 2025 City Council Districts. 
#### 2_ethnicity.ipynb
- Read in the Asian, Hispanic and Ancestry Census files.
- Reshape, or "melt" each dataframe so that the data is in a format we can analyze
- Combine all of the data together, so that we have a column for Census Tract, Ethnicity and Count. 
- Perform a series of groupings to get the "top" ethnic group in each tract (i.e. group with the highest population count). 
- Save to file
#### 3_elections.ipynb
- Read in election results from 2021, 2022 and 2024.
- Clean the results.
- Assign votes and turnout rates to city council districts using relationship file.
#### 4_enrollment.ipynb
- Use voter enrollment files to find turnout rates in 2021, 2022 and 2024.
- Use voter enrollment files to assign numbers of Dems, Reps, etc., in each City Council District. 
#### 5_income.ipynb
- Read in Census data related to median income.
- Assign median incomes to City Council districts using relationship file.
- Save to file.
#### 6_race.ipynb
- Read in Census data related to population by race.
- Assign counts based on race to City Council districts using relationship file.
- Save to file. 

## Licensing
All code in this repository is available under the MIT License. The data file in the output/ directory is available under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?
Contact Mia Hollie at mhollie@thecity.nyc.

