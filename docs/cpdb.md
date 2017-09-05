# The Capital Projects Database

The Capital Projects Database (CPDB), a data product produced by the New York City (NYC) Department of City Planning (DCP) Capital Planning division, captures key data points on past, present, and planned capital projects in and around NYC sponsored or managed by a capital agency. By capturing the location and timeline for capital projects CPDB enables citywide analyses of investments over time and space, and provides a central data source for agencies to evaluate synergies among projects.

Currently, CPDB aggregates and synthesizes spatial data from five NYC capital agencies, recording more than 10,000 past, present, and planned NYC capital projects occurring throughout NYC.  As new data become available these data will be processes and integrated into CPDB.

## Overview
| General information |
| :------------: | ------------- |
| Description | The Capital Planning Database (CPDB) captures key data points on past, present, and planned capital projects in and around New York City (NYC) sponsored or managed by a capital agency |
| Data format | GeoJSON, shapefile, csv |
| Projection | WGS84 |
| Date last updated | 08/15/16 |

## Methodology
## Building CPDB

### Loading data dependencies

Numerous datasets are required to build CPDB, so these are loaded into the database first.  Most of these datasets are public.

### Get raw data and choose primary data source

CPDB can be built using the public data obtained from the Capital Commitments Plans published by OMB or the data from FMS supplied by FISA.

**Capital Commitments Plan PDFs**

1. Download PDFs
2. Scrape data from PDFs
3. Load raw data table in to database as omb_capitalcommitments

**FMS data from FISA**

1. Download data from FISA FTP
2. Transform .asc file to .csv file
3. Upload .csv to DCP FTP
4. Load raw data table into database as fisa_capitalcommitments

Specify the primary data source in the *cpdb.config.json* file.  The defulat primary data source is *omb_capitalcommitments*.

**Create the CPDB base tables**

* **cpdb_projects**
	
	A project is defined as a unique FMSID

* **cpdb_budgets**
	
	A budget is a unique budget line.  Many budgets can fund one one project and many projects are funded by one budget.


* **cpdb_commitments**
	
	A commitment is an individual planned commitment.  Multiple planned commitments funs one project.

These base tables report the data at the three differnt levels.

### Developing the *cpdb_dcpattributes* table

This table contains all of DCP's value adds to the raw data, such as classifying and mapping the projects.

**Categorize the projects**

By matching words in the project's short description to a list of ~600 keywords group the projects into 3 categories:

* **IT, Vehicles, and Equipment**

	Any project that can be included in this group is added to this category.

* **Lump Sum**

	For allocations of funds that will be drawn from to create new projects.

* **Fixed Asset**
	
	For projects where the work will take place at one or many fixed locations.

Projects that can not be classifed into any of these three categories based on keywords in the short description are left as **Unknown**.

**Mapping the projects**

Projects were mapped using three methods:

1.	**Agency data**

	The Department of Design and Construction (DDC), Department of Transportation (DOT), and Department of Parks and Recreation (DPR) all publish spatial data of their captial projects, and each geometry includes the associated FMDID(s).  Therefore, we aggregate the geometries from these data sources to the FMSID and then add these geometries by joinin on FMDID.


2.	**Algorithms**

	Often the location of the project is specified in the project's short description.  Using a series of algorithms we are able to extract the specified location, such as a park id or park name, and join on geometries from an exisiting public data source, such as park properties or the facilities database.


3.	**Research**

	For many projects the location(s) of the project is/are specified in the project's short description, but a geometry cannot be assocaited with the project by joining to an existing dataset on FMS ID or mapping the project algorithmically.  Therefore, many projects were mapped via manual research, which involved a DCP team member reading the short description of the project and creating a geometry for that projects representing where that project is taking place.

	New geometries can be added to CPDB by adding a BIN with the assocaited FMSID to the [id_bin_map.csv](https://github.com/NYCPlanning/capitalprojects_db/blob/master/capitalprojects_build/attributes/id_bin_map.csv), which works best for building based projects, or by creating a geometry using [DCP's Simple Geom Editor](https://nycplanning.github.io/simple-geom-editor/) and adding the outputted .json file to the [geometries folder](https://github.com/NYCPlanning/capitalprojects_db/tree/master/capitalprojects_build/attributes/geometries).

	We focus mapping projects that have be categorized as a "Fixed Asset."

	**Agency verified**

	During the Summer of 2017 we with the support of OMB worked with each captial agency to verify the locations of the projects that we mapped and correct them if they were incorrect, and to map where possible projects that we were not able to map and that we've classifed as a "Fixed Asset" or "Unknown" type of project.

	The agency projected new or corrected location information by providing the address, bin, bbl, or other id or the location(s) where that project was taking place

	1. Format table for database consumption
	2. Load .csv onto DCP FTP
	3. Load into databae
	4. Create geometries based on BIN, BBL, or bridge id
	5. Create geometries by geocoding addresses
	6. Aggregate geometries to the FMS ID.
	7. Append new or corrected geometries from the *dcp_cpdb_agencyverified* onto the *cpdb_dcpattributes* table and overwrite any existing geometries.

**Removing geometries**

We make mistakes.  As we've QA/QCed and worked with CPDB if we noticed any project mapped incorrectly we've added the FMSID to the [cpdb_geomsremove.csv](https://github.com/NYCPlanning/capitalprojects_db/blob/master/capitalprojects_build/cpdb_geomsremove.csv).  At the end of the build process geometries for these projects are removed as long as the geometry did not come directly from an agency.

If an agency indicated that a project cannot be mapped now or ever the geometries for these projects were removed.

**Standardizing geometries**  

* All buildings are represented as points
* Lines are turned into polygons
* All geometries are made into multi-geometries

**Create master flat file**

Run a final .sql script to create the master flat file w/ array fields that drives the Captial Projects Explorer.

### Updating the production data tables for the Captial Projects Explorer

1. 	Output 4 .csv files and 2 .shp files from the database.
2.	Upload these tables to the CartoProd server
3. 	Swap out old production tables for the new data tables
	Data should update automatically in the Captial Projects Explorer
	Explorer goes down briefly while updating the data tables

## Database structure
Three tables compose CPDB: Projects, Sites, and Budget.

## Data Dictionary
##### Projects
| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| Global Unique Identifier | guid | Universal Unique Identifier.  When a row is added to the table the guid is automatically generated, enabling database replication |
| Random ID | rid | Auto incrementing integer to track projects |
| Capital Planning ID | idcapitalplanning | Unique capital planning ID - concatenates managing agency acronym and project ID |
| Project ID | idproject | Project ID as defined by the data source |
| FMS ID | idfms | FMS ID as defined by the data source or as generated by DCP by appending the managing agency code to the beginning of the project ID.  Valid FMS ID format = three digit agency code, space, project description acronym, project ID.  Example: 805 ARDXYZ123 |
| Project Name | projectname | Name of the project |
| Project Description | projectdescription | Description of the project |
| Project Type | projecttype | Type of capital project |
| Current Status | currentstatus | Current status of the project.  Valid values are: Cancelled, Complete, Construction, Design, Other, Planning |
| Managing Agency | managingagency | Acronym of the government agency managing the project. This field dictates the agency that can view and edit the project information |
| Sponsor Agency | sponsoragency | Acronym of the government agency sponsoring or funding the project |
| Funding Amount | fundingamount | Total exact or average funding amount allocated to or needed for the project |
| Minimum Funding | fundingmin | Minimum funding amount allocated to or needed for the project.  Only for projects that have a minimum and/or maximum funding amount defined |
| Maximum Funding | fundingmax | Maximum funding amount allocated to or needed for the project.  Only for projects that have a minimum and/or maximum funding amount defined |
| Funding Status | fundingstatus | Funding status of the project.  Valid values are: Funded, Underfunded, Not Funded | 
| Funding Source | fundingsource | Source of any funds for the project | 
| Construction Start Date | constructionstart | Actual or expected date of construction starting.  Valid formats: MM/YYYY, YYYY |
| Construction End Date | constructioncomplete | Actual or expected date of construction ending.  Valid formats: MM/YYYY, YYYY | 
| Fiscal Year Construction Complete | fyconstructioncomplete | Actual or expected fiscal year of construction ending.  Valid formats: YYYY | 
| Geometry | geom | The geometry of the project. Can be multipoint, multiline, or multipoly | 


##### Sites
| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| Global Unique Identifier | guid | Universal Unique Identifier.  When a row is added to the table the guid is automatically generated |
| Project ID | idproject | Project ID as defined by the data source, which relates back to the corresponding projects table.  One to many relationship with Projects |
| Latitude | latitude | Coordinate of the site. Only for point sites | 
| Longitude | longitude | Coordinate of the site. Only for point sites |
| Segment ID | segmentid | The id of the LION segment where the site is located. Only for line sites |
| Borough Block Lot | bbl | The building, block, and lot number of the site.  Only for polygon sites | 
| Estimated Costs At Location | estimatedcostatlocation | Evenly attributed estimated costs calculated by dividing fundingamount by the total number of sites| 
| Geometry | geom | The geometry of the site. Can be point, line, or polygon |




## Source Data
The following datasets were used to populate CPDB

### Department of Design and Construction (DDC)
DDC is the City's primary capital construction manager; therefore, DDC centrally manages much of the City’s capital projects portfolio.

##### Infrastructure projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DDC Capital Projects Infrastructure Projects |
| Description | Line shapefile capturing past, present, and planned infrastructure project, primarily capturing DOT and DEP projects | 
| Agency | DDC |
| Data Format | Shapefile |
| Update Frequency | Weekly |
| Update Means | Weekly data exchange with DDC |
| Date Updated | 2/19/2016 |
| Date Received | 2/22/2016 |
| Notes | This dataset acts as the primary data source; therefore, if other datasets have the same project CPDB rejects duplicate records from other data sources | 

##### Public buildings projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DDC Capital Projects Public Buildings |
| Description | Point shapefile capturing past, present, and planned public buildings projects | 
| Agency | DDC | 
| Data Format | Shapefile |
| Update Frequency | Weekly |
| Update Means | Weekly data exchange with DDC |
| Date Updated | 2/19/2016 |
| Date Received | 2/22/2016 |
| Notes | This dataset acts as the primary data source; therefore, if other datasets have the same project CPDB rejects duplicate records from other data sources | 

### Department of Transportation (DOT)

##### Street reconstruction projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DOT Capital Projects Street Reconstruction |
| Description | Line shapefile capturing present and planned locations of DOT sponsored street reconstruction and improvement projects | 
| Agency | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Automatic data pulls from DOT's capital projects map |
| Date Updated  | 3/1/2016 |
| Date Received | 3/1/2016 |
| notes | | 

##### Intersection projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DOT Capital Projects Intersections |
| Description | Point shapefile capturing present and planned locations of DOT sponsored projects occurring at intersections | 
| Agency | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Automatic data pulls from DOT's capital projects map |
| Date Updated  | 3/1/2016 |
| Date Received | 3/1/2016 |
| notes | | 

##### Bridge projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DOT Capital Projects Bridges |
| Description | Point shapefile capturing present and planned locations of DOT sponsored projects occurring on bridges | 
| Agency | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Automatic data pulls from DOT's capital projects map |
| Date Updated | 3/18/2016 |
| Date Received | 3/18/2016 |
| notes | | 

### Department of Parks and Recreation (DPR)

##### Parks projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DPR Capital Project Tracker |
| Description | XML file from NYC Open Data capturing present and planned locations of DPR sponsored capital projects | 
| Agency | DPR | 
| Data Format | XML |
| Data Link | https://www.nycgovparks.org/bigapps/DPR_CapitalProjectTracker_001.xml |
| Update Frequency | Daily |
| Update Means | Automatic weekly pulls from DPR's Capital Projects Tracker |
| Date Updated | 4/9/2015 |
| Date Received| 2/10/2016 |
| notes | | 

### School Construction Authority (SCA)
SCA plans, manages, and executes all capital projects related to NYC public schools including the construction of new school and the renovations of existing schools.

##### Capacity projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | SCA Capital Projects Capacity |
| Description | SCA's capital projects that involve the construction of a school or the expansion of a school to increase the capacity of a school district or school respectively | 
| Agency | SCA | 
| Data Format | CSV |
| Data Link | |
| Update Frequency | Annually |
| Update Means | Systematic transformation of SCA data |
| Date Updated | 7/1/2016 |
| Date Received| 7/1/2016 |
| notes | These data were scraped from static PDF files published by SCA documenting SCA's capital plan and transformed into a CSV that could later be imported into CPDB | 

##### Investment projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | SCA Capital Projects Investments |
| Description | SCA's capital projects that improve schools, such as laboratory upgrades | 
| Agency | SCA | 
| Data Format | CSV |
| Data Link | |
| Update Frequency | Annually |
| Update Means | Systematic transformation of SCA data |
| Date Updated | 7/1/2016 |
| Date Received| 7/1/2016 |
| notes | These data were scraped from static PDF files published by SCA documenting SCA's capital plan and transformed into a CSV that could later be imported into CPDB |

### Office of Recovery and Resiliency (ORR)
ORR works wit agencies, advocates, partnerships, and industries to advance long-term plans for growth and resiliency by improving the City's physical infrastructure, economy, and quality of life.

##### Capital projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | ORR Capital Projects |
| Description | ORR's capital projects that involve the construction of a school or the expansion of a school to increase the capacity of a school district or school respectively | 
| Agency | ORR | 
| Data Format | Shapefile |
| Data Link | https://maps.nyc.gov/resiliency/ |
| Update Frequency |  |
| Update Means | Automatic data pulls from ORR's capital projects map |
| Date Updated | |
| Date Received| 8/1/2016 |
| notes | | 

##Limitations and Disclaimers
CPDB is only as good as the source data it aggregates.  Currently, CPDB is the most comprehensive spatial data resource, but it does not capture every past, present, or planned capital project within NYC.  For more detailed information on a specific capital project please reach out to the respective managing agency.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [CapitalPlanning_DL@planning.nyc.gov](mailto:CapitalPlanning_DL@planning.nyc.gov)
