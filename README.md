# EDAFinal_PFAS

## Summary

The purpose of this repository is to compile relevant data and code to analyze PFAS level in North Carolina. Within the repository are raw datasets as well as processed datasets using the provided code. The code section is split into three files, wrangled data, exploration of data, and analysis of data. The goals of this analysis are to determine if any sites within North Carolina display a high concentration of PFAS or other contaminants. This repository is built in a way that new raw data can be added in the future to create visuals of PFAS contamination in NC as well as run other analysis.

## Investigators

Karly Nocera, Tay Holliday, Duke University, Nicholas School of the Environment, karly.nocera@duke.edu, tjh55@duke.edu

## Keywords

PFAS
PFOA
Gen-x
Analyte
Per- and polyfluoroalkyl substances (PFAS)
Water Contamination
North Carolina Water
Water Quality
Point source pollution

## Database Information

Raw data comes from North Carolina's Department of Environmental Quality (DEQ) in two datasets:
1. The 2018 Emerging Compounds Monitoring Reports of various watersheds and public water supply (PWS) reservoirs
2. 2019 wastewater treatment plant (WWTP) samples.

Both datasets were first accessed by Karly Nocera in 2020. Processed data was created by Karly Nocera and Tay Holliday in 2021, creating new fields to help in analysis.

## Folder structure, file formats, and naming conventions 

There are 3 main folders within the repository: Code, Data, and Output. The Data folder contains two sub-folders: Processed and Raw. Within the raw folder are csv files containing data obtained from the EPA and Waste Water Treatment Plants. Within the Processed folder are csv files that have been wrangled through the data wrangling code within the code folder. In the code folder there are 5 R markdown files: 
1. A project template markdown file with which was the foundation to create the final project;
2. A wrangle markdown file which is R code that takes raw data from the raw data file and creates a much neater and easier to use processed data csv file;
3. An explore markdown file that explores the data in a visual and informative way;
4. An analysis file to answer visual analyses;
4. A final markdown file combining the codes for submission.

CSV files contain the data used in this repository. R Markdown files contain the R code with which the data is run through.

Naming conventions are as follows: for data, if it is for one given year, the year comes first, followed by the source. After this, any additional identifying keyword is added. Example: 2019_WWTP_Aug is the csv file that pertains to 2019 Waste Water Treatment Plant for the month of August. The use of the words long and wide indicate if the data set has the analyte in a singular column (long) or if each analyte is given its own column (wide). Another keyword used is "clean" which indicates that the data file has been processed with some values removed to make it easier to analyze.

## Metadata

2018_PublicSupply_original.csv
  columns: Location, Site, Lab, Sample.Date, Analyte, ppt, lab.qual
    Location: Code for the given site
    Site: Site name
    Lab: Lab where data was processed
    Sample.Date: Sample date and time
    Analyte: Type of Analyte tested
    ppt: level of contaminant in parts per trillion
    lab.qual: qualification value for testing
2019_WWTP_original_asdataset.csv
  columns: Site, Analyte, Sample.Date, ppt, lab.qual
    Site: Site name
    Sample.Date: Sample date and time
    Analyte: Type of Analyte tested
    ppt: level of contaminant in parts per trillion
    lab.qual: qualification value for testing
chainlenght.csv
  columns: Chain_Length, Acronym
    Chain_Length: If the analyte is considered long or short chain
    Acronym: Acromnym for the given analyte
Locations_latlong.csv
  columns: Type, Site, lat, long
    Type: WWTP or Source data
    Site: Name of the site
    Lat: Latitude
    Long: longitude
sitetype.csv
  columns: Type, Site
    Type: WWTP or Source data
    Site: Name of the site 

## Scripts and code

ProjectTemplate.Rmd was the foundation to the clean, explore, anad analysis files.
PFAS_Wrangle.Rmd is used to tidy the raw data into clean processed datasets.
PFAS_explore.Rmd is used to explore the data quickly.
PFAS_analysis.Rmd is the analysis script combined from both authors to perform various analysis.
PFAS_final.Rmd is the final combined script based on the Project Template.

## Quality assurance/quality control

We double checked that the site name matched the location code. Lat and Long were examined to see if they matched the location described. We also checked to make sure there were no misspelled sites that may result in data being analyzed incorrectly. 