VecDyn
======

The Global **Vec**tor Population **Dyn**amics Database

Instructions
------------
*How to submit data, minimal requirements and procedures*

In order to submit data to the VecDyn database (*temporary procedures*)  
1. Fill in the template, making sure all the requirements are met (*see template description*).  
2. Go to https://vectorbyte.org and sign up / log in to access appropriate pages.  
3. Navigate to 'submit data' via the 'submissions' button.   
4. Fill in 'Data Series Information' fields (*under 'Data set category' select 'VecDyn Data Submission'*).  
5. Attach your completed 'VecDyn_template.csv' and hit submit.  
We'll contact you once your data has been incorporated into the database.




-   The database template file, its field descriptions, and a minimal example file are located in the `Template` directory. Notice that all files are in plain text '.csv' format, and not in Excel format or similar. This facilitates text parsing by scripts, prevents data loss/corruption, and allows for detailed comparisons of changes via version control systems.

-   Any suggestions or todos with regards to the database (e.g., new columns, schema modifications etc.) can be logged as [Issues on GitHub](https://github.com/vectorbite/VecDyn/issues). Issues allow for discussions among multiple users, file attachments, colour-coded labels etc.

-   The `GPDD` directory also contains the documentation of the [**G**lobal **P**opulation **D**ynamics **D**atabase](http://www3.imperial.ac.uk/cpb/databases/gpdd), a pre-existing database of population dynamics, hosted in Silwood Park, Imperial College London since 1999. VecDyn aims to learn from both GPDD's success and potential shortcomings as it moves forward.

<br/>

VecDyn Template Description
---------------------------
 
<br/>   

Data Series Information
------------------------
*The following information should be supplied separately when a data set is submitted*


Field Name | Format|Requirement| Details   | Additional Notes
-----------| ------| -------  |-----------|--------------
title | String | Required|Short title identifying the data series| E.g. “Mosquito Surveillance in Iowa”
collection_auth | String | Required | Name of lead collection author or collection authority |E.g. family name, given names; OR ‘Iowa State’
DOI|String|Optional|Digital Object Identifier (DOI)|If the dataset was already published elsewhere, use the original DOI
pub_date|ISO 8601 date format (YYYY-MM-DD)|Required|Publication date|In case the data set was already published elsewhere, use the date of first publication.
description|text|Required|Description of dataset|A short description of the study  e.g. ‘Long term, fixed trapped, municipal surveillance of west Nile vector population in Colorado from 2000-2010”|
contact_name|String|Required|Author|contact name|Name, person, authority, etc. that may be contacted with inquiries about the data (may differ from the contact details of the submitter – these details will be stored on the VectorBite DB)
auth_affiliation|String|Required|Author/contact affiliation|
auth_email|String|Optional|Contact email|
ORCID|String|Optional|ORCID code|A digital identifier which provides researchers with a unique ID (see https://orcid.org/)
keywords|String|Optional|Keywords for web searches|
<br/>

Meta Data (part of the VecDyn data collection template)
-------------------------------------------------------
*The data entered into these fields should be repeated for each row/observation in the VecDyn data collection template*
<br/>

Field Name | Format|Requirement| Details   | Additional Notes
-----------| ------| -------  |-----------|-----------------
data_set_name|String|Required|Short title identifying the data set|The title should be related to the data series title e.g. “Tiger Mosquito Surveillance in Iowa”
taxon_name|String|Required|Classification of sample collected|Use the Catalogue of Life 2017 checklist to obtain the taxon name, only use names which are classed as ‘accepted’. See http://www.catalogueoflife.org/annual-checklist/2017/|
country|String |Required|Country where study was conducted|Use the United Nations's "Standard Country" names. See here https://unstats.un.org/unsd/methodology/m49/| 
location_description|String|Required|Study location description|Description of study location e.g.. towns and regions etc
location_environment|Lookup|Optional|General description about the location|Where possible, please use the Environment Ontology search feature to characterize the location’s environment (see http://www.environmentontology.org/Browse-EnvO)
study_lat_DD|Double (float)|Required|Latitude of study area as a decimal degree|General location of the study Ranges[-90,+90] for latitude (north-south measurement)| 
study_long_DD | Double (float) |Required|Longitude of study area as a decimal degree| Ranges [-180,180] for longitude (east-west measurement)
spatial_accuracy|integer|Optional|Spatial accuracy of the given coordinates|Value between 0 - 6 indicating the accuracy of the location given. 0 = Unknown, 1 = >100 km radius, 2 = 10 - <100km, 3 = 1 - <9km, 4 = 0.1 - 1km, 5 = 10 - 100m, 6 = accurate survey (incl. GPS) <= 10m
location_extent|integer|Optional|Indicating the size of the study site.|A value between 1 - 4.  Where available absolute size is recorded in the Area field. 1 = Region >10 km radius, 2 = Local Area 1-10 km radius, 3 = Extended Site 0.1-1 km radius, 4 = Precise Site <0.1 km radius|
geo_datum|String|Required|Geodetic datum | E.g..  WGS 84|
species_id_method|String|Optional|Species Identification Method|A description of the methods species identification.
study_design|String|Optional|Study design methodology|Indicate if  observational study i.e.prospective , retrospective, or experimental etc|
sampling_strategy|String|Optional|Indicate the strategy used to select the sample| E.g.. simple random sampling, stratified, convenience sampling, cluster, sampling, census etc|
sampling_method|String|Required|Sampling apparatus (e.g..  trap type, observation method)|E.g. “CDC light trap w/ CO2”,  “Prokopack backpack aspirator”, “Quadrat count”|
sampling_protocol|String|Required|How entities were sampled |e.g. ‘Count’, ‘Count (millions)’, ‘Harvest’, ‘Index of abundance’, ‘Index of territories’, ‘Leaf area’, ‘Mean Count’, ‘Not Specified’, ‘Percent cover’ and ‘Sample’.
measurement_unit|String|Required|Unit of measurement|The entity observed. Entries could include, 'individuals', ‘adults’, ‘cells’, ‘egg masses’, and ‘pelts’|
sample_collection_area|String|Optional|The spatial extent (area or volume) of the sample|If relevant (e.g.., when collection method is transect or quadrat), in units of area or volume, the spatial coverage of the sampling unit e.g. “100 m^2”, “1  liter”, “1 ha”, “10m^3”| 
value_transform|String|Optional|Note if the original values have been transformed – list details of the reference value of any data transformation| e.g..Base Year, Log, None, Not Specified, Proportion, Unknown, x 1000 lbs|
 
 

Time Series Data
----------------
*Data to be displayed in Time-Series, each row represents a seperate observation in the VecDyn template*

Field Name | Format|Requirement| Details   | Additional Notes
-----------| ------| -------  |-----------|-----------------
sample_start_date|ISO 8601 date format (YYYY-MM-DD)| Optional|Start date |Only required when the collector wants to sample populations within specific time frames e.g. between when a trap was set and when the sample was collected|
sample_start_time|ISO 8601 time format (hh:mm:ss)| Optional|Start time|Only required when the collector wants to sample populations within specific time frames e.g. time example: 15:53:00|
sample_end_date|ISO 8601 time format (hh:mm:ss)| Required|Collection date |  The date the sample was collected. If collection occurs monthly use the first day of each month i.e. 2001-01-01, 2001-02-01. Date example: 2008-09-15, Datetime example: 2008-09-15T15:53:00|
sample_end_time|ISO 8601 time format (hh:mm:ss)| Optional|Time of the sample  collection |  The time the sample was collected. time example: 15:53:00|
value| float| Required| The numerical amount or result from the sample collection| The population data from study
sample_info|text| Optional| Additional sample information| Should be used when more information is required to understand the experiment, for example experimental variables, sub-locations, etc.Could report general info regarding sample location. Some users may report wind speeds Examples: “Forest” vs “Field”, “Winter”vs “Summer”, “Inside” vs “Outside”, “200 meters above sea level”
 sample_name|text|Optional|A human readable sample name| May exist solely for the benefit of the depositor in organizing their data, use their own internal naming conventions etc.Naming convention is not restricted, but any encoded metadata should be revealed in the other data fields. For example, you may name a sample named ‘Aphid1_StickyTrap_Jan4,’ but you will still have “Sticky Trap” listed in a Collection Method field, and “Jan 4, 2017” in the date field.| 
 
 







