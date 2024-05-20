# Debt Collection Team A

This project aims to collect data on known debt collectors in the MassCourtsPlus.org databases.

Read the report for more details.

Note: This repo contains details about court cases that may have sensitive data

## Table of Contents

1. [Dependencies](#dependencies)
2. [Data Sources](#data-sources)
3. [Organization](#organization)
4. [Appendix](#appendix)

## Dependencies

- Python3
  - numpy
  - pandas
  - pymysql
  - matplotlib
  - torch
  - transformers
  - sklearn
- Jupyter Notebook

## Data Sources

- MySQL Server on MassCourtsPlus.org
- Mass.gov Debt Collector Licensee files (quarterly)
- RMAI certification records

## Organization

The repo is organized into 3 folders:
- data
  - contains all CSV and XLSX files including its parser
- deliverables
  - contains presentations and reports
- nb
  - contains all notebooks used to generate data for the reports

### Notebooks

This section gives a brief about what each of the notebooks do

data:
- debt-collector-licensee-parser
  - Finds all debt collectors
  - Parses all other files in the directory to be used with collectors notebook
  - Creates debt-collector-licensee-all.csv
  - Creates debt-collector-licensee-all.csv

nb:
- collectors
  - Figures out who is a debt collector
  - Figures out percentage of small claims cases by debt collectors
  - creates data/case_claims.csv
- default_cases
  - Used to determine what cases are default cases in the database
- Defendant_percentage_Yiyang
  - Find information about the defendents
- many_access
  - Used to find a way to shorten query time
- masscourtsplus_All_column_names
  - Shows what information is in each table of each database
- MassCourtsPlus_BU_2024_Yiyang_cai
  - Find information about wage garnishes
- MassCourtsPlus_wgbh_Question1
  - Find information about court cases by district
- ProSe Default
  - Find information about Pro Se and Default being the result of one another
- PreSe_Proper_ALL
  - Find information about Pro Se Proper cases
- Question1_10
  - Find information about court cases by district
- small-claims
  - Find out the number of cases by debt collectors (outdated)
- special_cases
  - Tries to identify special cases not in the initial questions


## Appendix

### Known Issues

- Some of the CSV files in data are not accessible for unknown reasons
- Some of the plaintiffs in the data parser result in float values
- Date filtering must be the last filter in collectors.ipynb
- Extra column in case_claims with index should be ignored if exists
- data/rmai_certified_individuals is only 40% completed
