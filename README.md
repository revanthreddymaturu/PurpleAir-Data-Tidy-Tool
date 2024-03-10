# PurpleAir Data Tidy Tool
Merges Purple Air SD Card Data into one file for comparison to FEM Instruments.(Note: This tool has been updated to handle frequently occurring errors to prevent manual updation and handling)

# Table of Contents
1. [General Info](#general-info)
2. [Instructions](#instructions)
3. [Data Tabs](#data-tabs)
4. [FAQs](#faqs)

## General Info
- This is an R Shiny App that allows you to tidy Purple Air Data(PM1.0, PM2.5 and PM10.0) that has been downloaded from an SD card from an offline Purple Air sensor and Download into .csv format 
- This code will only work with data exported from an SD card and not data downloaded from the Purple Air Map.
- Data Columns for SD data are different from Map columns more info here: https://community.purpleair.com/t/sd-card-file-headers/279
- Corrected PM2.5 data uses US EPA's Simple Correction Factor which is described in detail here: https://www.mdpi.com/1424-8220/22/24/9669
- Corrected PM1.0 and PM10.0 data uses Correction Factor which is developed by [CEEJH UMD](https://www.ceejh.center/)
- The data will be corrected and only show the columns that are necessary to be compared to FEM PM instruments. 


## Instructions
**Please Note:** App will not work correctly in R studio's native web launcher please change settings in Run App -> set to run External or select open in Browser when running it in R studio. 
1. Download the Repository and Make sure R, R studio and all packages are installed in order for the App to properly function
2. Run the App in your normal web browser and browse your computer for the Raw data files (multiple files can be selected at one time)
3. Select which Data will be uploaded and it will combined into one data file. Click Download and rename as you would like.

## Data Tabs
This is Information on what has been done in each of the Data Tabs that can be downloaded. 
- Raw Data: Raw Data combined into one file with no changes or corrections to the data
- Tidy Data: Converted to selected Time Zone with Both A & B Channels along with Meteorology data but no Corrections
- Average Data: Averages 2-minute Data into 60-minute Averages 
- Corrected Data: Corrects data based on QC Criteria of 70% data completeness using EPA Correction factor using both channels to generate a single PM1.0,PM2.5 and PM10.0 Values

## FAQs
1. Why does my data produce an error when reading in my raw data files?
> A: There are many sources of error for this problem including Data not in the right file format (ie. not .csv or .CSV), Contains corruption in the data file, or browser incompatibility (make sure you are using a web browser!). If errors mention a specific file you can look in the File Names tab to identify what file is giving you the error and attempt to correct it.
2. What data format does the App support?
> A: Input data must be in .csv and .CSV format and download data will be .csv as well
3. Is there a list of exact names for the columns of each dataframe including units?
> A: Yes! please view the Column test.txt file on what the column names mean and their containing units
4. What is the file limit/size for uploading data?
> A: The file limit size is based on the memory limit of your device. For best results, It is recommended to only do a few months at a time when importing data (less than 10,000 measurements) to make viewing data easier.  
5. What is the Recommended Data Table/ Column to get for Data analysis?
> A: I recommend downloading the Corrected Data Frame and using the 'PM_corr_EPA' column along with 'date' to compare to a FEM instrument
6. I have an issue/request/question about the app, how can I contact you?
> A: Please contact me through Github by creating a new issue and labelling it appropriately and I will try to get back to you ASAP.

## Credits
Github repository https://github.com/SebAire/Purple-Air-Data-Merger was used as a reference and modifications were made to existing code/tool to develop this tool to assist in PM1.0 and PM10.0 data analysis and to handle some frequently occurring errors while data merging.
