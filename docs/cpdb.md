# The Capital Projects Database

The Capital Projects Database (CPDB), a data product produced by the New York City (NYC) Department of City Planning (DCP) Capital Planning division, captures key data points on potential, planned, and ongoing capital projects sponsored or managed by a capital agency in and around NYC.

Information reported in the Capital Commitment Plan published by the NYC Office of Management and Budget (OMB) three times per year is the foundation that CPDB is then built off of; therefore, only the capital projects that appear in the Capital Commitment Plan are reflected in CPDB.  Other open data resources are also leveraged to map the capital projects.

CPDB supports the most comprehensive map of potential, planned, and ongoing capital projects taking place across NYC enabling Planners to better understand and communicate New York City’s capital project portfolio within and across particular agencies. This integrated but not exhaustive view provides a broad understanding of what projects are taking place within a certain area, and a starting point to discovering opportunities for strategic neighborhood planning.


## I. Overview

| | |
| :------------: | ------------- |
| Dataset Name | "Capital Projects Database"|
| Description | The Capital Projects Database (CPDB) captures key data points on, including spatial data, potential, planned, and ongoing capital projects reported in the Capital Commitment Plan published by the NYC Office of Management and Budget (OMB)|
| Data format | [Webmap](https://capitalplanning.nyc.gov/capitalprojects/explorer#13.62/40.7094/-74.0058), Shapefile: [Points](https://cartoprod.capitalplanning.nyc/user/cpp/api/v2/sql?skipfields=cartodb_id&q=SELECT%20*%20FROM%20(SELECT%20a.the_geom,%20a.the_geom_webmercator,%20magency,%20magencyacro,%20description,%20totalcommit,%20b.maprojid,%20totalspend,%20sagencyacro,%20maxdate,%20mindate,%20projecttype%20FROM%20cpdb_dcpattributes_pts%20a%20LEFT%20JOIN%20cpdb_projects_combined%20b%20ON%20a.maprojid%20=%20b.maprojid)%20x&format=shp&filename=projects-points_complete_2017-09-15) & [Polygons](https://cartoprod.capitalplanning.nyc/user/cpp/api/v2/sql?skipfields=cartodb_id&q=SELECT%20*%20FROM%20(SELECT%20a.the_geom,%20a.the_geom_webmercator,%20magency,%20magencyacro,%20description,%20totalcommit,%20b.maprojid,%20totalspend,%20sagencyacro,%20maxdate,%20mindate,%20projecttype%20FROM%20cpdb_dcpattributes_poly%20a%20LEFT%20JOIN%20cpdb_projects_combined%20b%20ON%20a.maprojid%20=%20b.maprojid)%20x&format=shp&filename=projects-polygons_complete_2017-09-15), GeoJSON: [Points](https://cartoprod.capitalplanning.nyc/user/cpp/api/v2/sql?skipfields=cartodb_id&q=SELECT%20*%20FROM%20(SELECT%20a.the_geom,%20a.the_geom_webmercator,%20magency,%20magencyacro,%20description,%20totalcommit,%20b.maprojid,%20totalspend,%20sagencyacro,%20maxdate,%20mindate,%20projecttype%20FROM%20cpdb_dcpattributes_pts%20a%20LEFT%20JOIN%20cpdb_projects_combined%20b%20ON%20a.maprojid%20=%20b.maprojid)%20x&format=geojson&filename=projects-points_complete_2017-09-15) & [Polygons](https://cartoprod.capitalplanning.nyc/user/cpp/api/v2/sql?skipfields=cartodb_id&q=SELECT%20*%20FROM%20(SELECT%20a.the_geom,%20a.the_geom_webmercator,%20magency,%20magencyacro,%20description,%20totalcommit,%20b.maprojid,%20totalspend,%20sagencyacro,%20maxdate,%20mindate,%20projecttype%20FROM%20cpdb_dcpattributes_poly%20a%20LEFT%20JOIN%20cpdb_projects_combined%20b%20ON%20a.maprojid%20=%20b.maprojid)%20x&format=geojson&filename=projects-polygons_complete_2017-09-15), [CSV](https://cartoprod.capitalplanning.nyc/user/cpp/api/v2/sql?skipfields=cartodb_id&q=SELECT%20*%20FROM%20cpdb_projects_combined&format=csv&filename=projects_complete_2017-09-15) |
| Projection | WGS84 |
| Date last updated | March 2020 |
| Capital Commitment Plan version | January 2020 |

## II. Limitations and Disclaimers

CPDB is only as good as the source data it extracts and aggregates; therefore, CPDB includes data on current and planned NYC capital projects reported in OMB's Capital Commitment Plan and it does not capture all historic, current, or future capital projects.  

**CPDB is not a project or financial management system**.  Data on project timeline may be incorrect and budgetary information may be incomplete since all monies committed to or spent on a project may not be captured.  CPDB does capture planned commitments allocated to projects that may never come to fruition; these instances are most frequent for projects funded by discretionary funding sources, such as council member funding.

Currently, CPDB is the most comprehensive spatial data resource of current and planned City capital projects, but the **spatial data are not 100% reliable, accurate, or exhaustive**.

* The **map of capital projects is incomplete** because many capital projects could not be spatially referenced due to vague descriptions not including the name of a site.  

* **Some projects are mapped incorrectly**.  Some projects are geocoded to agency's headquarters rather than the site where the capital investment and construction is taking place.  Other projects are mapped to the wrong site as a result of two places having the same name or similar names. Unfortunately, these records cannot be systematically verified and corrected.

Through user feedback we look to resolve these limitation over time.

**For more detailed information on a specific capital project please reach out to the respective managing or sponsor agency.**

As a result of these limitations and inconsistencies, **CPDB should not be used for quantitative analyses**.  CPDB should be used for planning coordination and information purposes only.
If CPDB is used for any spatial analyses it is crucial to recognize that not all of the projects are spatially referenced, projects may be incorrectly spatially referenced, one project can span across many locations, and this database is not authoritatively comprehensive.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [CapitalPlanning_DL@planning.nyc.gov](mailto:CapitalPlanning_DL@planning.nyc.gov).

## III. Methodology
**Building CPDB**

### Loading data dependencies

Numerous datasets are required to build CPDB, so these are loaded into the database first.  Most of these datasets are public.

### Get raw data and choose primary data source

CPDB can be built using the public data obtained from the Capital Commitments Plans published by OMB or the data from FMS supplied by FISA.

**Capital Commitments Plan PDFs**

1. Download PDFs
2. Scrape data from PDFs
3. Load raw data table into database as omb_capitalcommitments

**FMS data from FISA**

1. Download data from FISA FTP
2. Transform .asc file to .csv file
3. Upload .csv to DCP FTP
4. Load raw data table into database as fisa_capitalcommitments

Specify the primary data source in the *cpdb.config.json* file.  The default primary data source is *omb_capitalcommitments*.

**Create the CPDB base tables**

* **cpdb_projects**
	
	A project is defined as a unique FMSID

* **cpdb_budgets**
	
	A budget is a unique budget line.  Many budgets can fund one one project and many projects are funded by one budget.


* **cpdb_commitments**
	
	A commitment is an individual planned commitment.  Multiple planned commitments fund one project.

These base tables report the data at the three different levels.

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

Projects that can not be classified into any of these three categories based on keywords in the short description are left as **Unknown**.

**Mapping the projects**

Projects were mapped using three methods:

1.	**Agency data**

	The Department of Design and Construction (DDC), Department of Transportation (DOT), and Department of Parks and Recreation (DPR) all publish spatial data of their capital projects, and each geometry includes the associated FMDID(s).  Therefore, we aggregate the geometries from these data sources to the FMSID and then add these geometries by joining on FMDID.


2.	**Algorithms**

	Often the location of the project is specified in the project's short description.  Using a series of algorithms we are able to extract the specified location, such as a park id or park name, and join on geometries from an existing public data source, such as park properties or the facilities database.


3.	**Research**

	For many projects the location(s) of the project is/are specified in the project's short description, but a geometry cannot be associated with the project by joining to an existing dataset on FMS ID or mapping the project algorithmically.  Therefore, many projects were mapped via manual research, which involved a DCP team member reading the short description of the project and creating a geometry for that projects representing where that project is taking place.

	New geometries can be added to CPDB by adding a BIN with the assocaited FMSID to the [id_bin_map.csv](https://github.com/NYCPlanning/capitalprojects_db/blob/master/capitalprojects_build/attributes/id_bin_map.csv), which works best for building based projects, or by creating a geometry using [DCP's Simple Geom Editor](https://nycplanning.github.io/simple-geom-editor/) and adding the outputted .json file to the [geometries folder](https://github.com/NYCPlanning/capitalprojects_db/tree/master/capitalprojects_build/attributes/geometries).

	We focus mapping projects that have be categorized as a "Fixed Asset."

	**Agency verified**

	During the Summer of 2017 we with the support of OMB worked with each capital agency to verify the locations of the projects that we mapped and correct them if they were incorrect, and to map where possible projects that we were not able to map and that we've classified as a "Fixed Asset" or "Unknown" type of project.

	The agency projected new or corrected location information by providing the address, bin, bbl, or other id or the location(s) where that project was taking place

	1. Format table for database consumption
	2. Load .csv onto DCP FTP
	3. Load into database
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

Run a final .sql script to create the master flat file that aggregates information, such as spending data, to the project level.

### Updating the production data tables for the Capital Projects Explorer

1. 	Output 4 .csv files and 2 .shp files from the database.
2.	Upload the files to the CartoProd server.
	* cpdb_projects.csv
	* cpdb_budgets.csv
	* cpdb_commitments.csv
	* cpdb_projects_combined.csv
	* cpdb_dcpattributes_pts.shp
	* cpdb_dcpattributes_poly.shp
3.	Run one final SQL script in Carto to create array fields and create new table named cpdb_projects_combined from output.
4. 	Point Explorer to reference latest datasets

## IV. Data Dictionary

The source data used to build CPDB determines what attributes are reported by the final product.  Using FMS data from FISA provides the greatest level of detail and accuracy, and outputs the most attributes.  Attributes marked with a **' * '** are exclusive to FISA source data. 

The tables that compose CPDB are all related by the FMS ID.

##### Projects (cpdb_projects)
Reports information from the Capital Commitment Plan at the project level.  A project is a unique FMS ID. 

| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| FMS ID | maprojid | Unique identifier that defines a discrete project.  The maprojid is a concatenation of *magency* and *projectid* and it is the primary key.|
| Managing Agency | magency | Three digit code of the distinct City agency managing the project.|
| Project ID | projectid | Alphanumeric code created by the sponsor agency that identifies a distinct project. A Project ID must be unique within a managing agency.|
| Description | description | Short description of the project as described by the sponsor agency.  If one FMS ID had many descriptions the longest description is reported by CPDB. |
| $ City Cost (Non-Exempt) * | ccnonexempt | Sum of City Cost (Non-Exempt) funding across all commitments associated with the project. |
| $ City Cost (Exempt) * | ccexempt | Sum of City Cost (Exempt) funding across all commitments associated with the project. |
| $ City Cost | citycost | Sum of City funding across all commitments associated with the project.  (If FISA is the source data $ City Cost is the sum of $ City Cost (Exempt) and $ City Cost (Non-Exempt)). |
| $ Non-City Cost State * | nccstate | Sum of State funding across all commitments associated with the project. |
| $ Non-City Cost Federal * | nccfederal | Sum of Federal funding across all commitments associated with the project. |
| $ Non-City Cost Other * | nccother | Sum of Other funding across all commitments associated with the project. |
| $ Non-City Cost | noncitycost | Sum of Non-City funding across all commitments associated with the project. (If FISA is the source data $ Non-City Cost is the sum of $ Non-City Cost State, $ Non-City Cost Federal, and $ Non-City Cost Other). |
| $ Total Planned Commitments | totalcost | Sum of $ City Cost and $ Non-City Cost, which reports the total planned commitments for the project allocated in the Capital Commitment Plan. |
| Managing Agency Acronym | magencyacro | Common acronym of the city agency managing the project.  This value is derived from the three digit managing agency code. |
| Managing Agency Name | magencyname |  Common name for the city agency mananging the project.  This value is derived from the three digit managing agency code. |
| Capital Commitment Plan version | ccpversion | Reports the version of the Capital Commitment Plan which the record is based on. |

##### Budgets (cpdb_budgets)
Reports information from the Capital Commitment Plan for projects at the budget level.  One project can be funded by many budgets.

| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| FMS ID | maprojid | Unique identifier that defines a discrete project.  The maprojid is a concatenation of *magency* and *projectid* and it is the foreign key.|
| Managing Agency | magency | Three digit code of the distinct City agency managing the project.|
| Project ID | projectid | Alphanumeric code created by the sponsor agency that identifies a distinct project. A Project ID must be unique within a managing agency.|
| Budget Line | budgetline | Unique identifier of the budget used to fund the project. |
| Project type | projecttype |  Short description of the type of project based on the budget funding the project. |
| Sponsor Agency Acronym | sagencyacro | Common acronym of the city agency sponsoring the project.  This value is derived from the budget line. |
| Sponsor Agency Name | sagencyname |  Common name for the city agency sponsoring the project.  This value is derived from the budget line. |
| $ City Cost (Non-Exempt) * | ccnonexempt | Sum of City Cost (Non-Exempt) funding across all commitments associated with the project drawn from the specified budget line. |
| $ City Cost (Exempt) * | ccexempt | Sum of City Cost (Exempt) funding across all commitments associated with the project drawn from the specified budget line. |
| $ City Cost | citycost | Sum of City funding across all commitments associated with the project drawn from the specified budget line.  (If FISA is the source data $ City Cost is the sum of $ City Cost (Exempt) and $ City Cost (Non-Exempt)). |
| $ Non-City Cost State * | nccstate | Sum of State funding across all commitments associated with the project drawn from the specified budget line. |
| $ Non-City Cost Federal * | nccfederal | Sum of Federal funding across all commitments associated with the project drawn from the specified budget line. |
| $ Non-City Cost Other * | nccother | Sum of Other funding across all commitments associated with the project drawn from the specified budget line. |
| $ Non-City Cost | noncitycost | Sum of Non-City funding across all commitments associated with the project drawn from the specified budget line. (If FISA is the source data $ Non-City Cost is the sum of $ Non-City Cost State, $ Non-City Cost Federal, and $ Non-City Cost Other). |
| $ Total Planned Commitments | totalcost | Sum of $ City Cost and $ Non-City Cost, which reports the total planned commitments drawn from the specified budget line for the project allocated in the Capital Commitment Plan. |
| Capital Commitment Plan version | ccpversion | Reports the version of the Capital Commitment Plan which the record is based on. |

##### Commitments (cpdb_commitments)
Reports information from the Capital Commitment Plan at the commitment level.  Many commitments can fund one project.

| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| FMS ID | maprojid | Unique identifier that defines a discrete project.  The maprojid is a concatenation of *magency* and *projectid* and it is the foreign key.|
| Managing Agency | magency | Three digit code of the distinct City agency managing the project.|
| Project ID | projectid | Alphanumeric code created by the sponsor agency that identifies a distinct project. A Project ID must be unique within a managing agency.|
| Budget Line | budgetline | Unique identifier of the budget used to fund the project. |
| Planned Commit Date | plancommdate |  Month and year of when the planned commitment is projected to be committed. |
| Commitment Description | commitmentdescription | Short description of what the planned commtiment will specifically fund.  Not all commitments have descriptions. |
| Commitment Code | commitmentcode |  Four letter or digit code indicating what part of the project the associated funding is for, such as design, construction, or contingency. |
| Ten Year Plan Categroy * | typc | Three leter code indicating what ten year plan category the planned commitment supports. |
| Ten Year Plan Categroy Name * | typcname |  Ten year plan category the planned commitment supports. |
| $ City Cost (Non-Exempt) * | ccnonexempt | Amount City Cost (Non-Exempt) funding associated with the commitment. |
| $ City Cost (Exempt) * | ccexempt | Amount of City Cost (Exempt) funding associated with the commitment. |
| $ City Cost | citycost | Amount of City funding associated with the commitment.  (If FISA is the source data $ City Cost is the sum of $ City Cost (Exempt) and $ City Cost (Non-Exempt)). |
| $ Non-City Cost State * | nccstate | Amount of State funding associated with the commitment. |
| $ Non-City Cost Federal * | nccfederal | Amount of Federal funding associated with the commitment. |
| $ Non-City Cost Other * | nccother | Amount of Other funding associated with the commitment. |
| $ Non-City Cost | noncitycost | Amount of Non-City funding associated with the commitment. (If FISA is the source data $ Non-City Cost is the sum of $ Non-City Cost State, $ Non-City Cost Federal, and $ Non-City Cost Other). |
| $ Total Planned Commitments | totalcost | Sum of $ City Cost and $ Non-City Cost, which reports the total planned commitments associated with the commitment for the project allocated in the Capital Commitment Plan. |
| Capital Commitment Plan version | ccpversion | Reports the version of the Capital Commitment Plan which the record is based on. |

##### DCP Attributes (cpdb_dcpattributes)
Reports information generated by DPC, including spatial data, at the project level.  These data are published as two tables *_pts* and *_poly* where data are separated based on the geometry type.

| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| FMS ID | maprojid | Unique identifier that defines a discrete project.  The maprojid is a concatenation of *magency* and *projectid* and it is the primary key.|
| Managing Agency | magency | Three digit code of the distinct City agency managing the project.|
| Project ID | projectid | Alphanumeric code created by the sponsor agency that identifies a distinct project. A Project ID must be unique within a managing agency.|
| Managing Agency Acronym | magencyacro | Common acronym of the city agency managing the project.  This value is derived from the three digit managing agency code. |
| Description | description | Short description of the project as described by the sponsor agency.  If one FMS ID had many descriptions the longest description is reported by CPDB. |
| Category | typecategory | Classification given by DCP based on keywords found in the short description describing if a projects is Fixed Asset, Lump Sum, or ITT, Vehicles, and Equipment.| 
| Geometry Source | geomsource | Description of where the geometry associated with the project came from.|
| Data Name | dataname | Name of the dataset where the geometry associated with the project came from.|
| Data Source | datasource | Acronym of the agency that supplied the dataset from which the geometry associated with the project came from.|
| Data Date | datadate | Date the geometry was updated. |
| Capital Commitment Plan version | ccpversion | Reports the version of the Capital Commitment Plan which the record is associated with. |
| Geometry | geom | Spatial data information. |

##### Project Combined (cpdb_projects_combined)
Master flat file used to power the Capital Projects Explorer that aggregates and reports data at the project level.

| Field Alias | Field Name | Description                                             |
| :------------------- | :------------------- | :------------------------------------------------------ |
| FMS ID | maprojid | Unique identifier that defines a discrete project.  The maprojid is a concatenation of *magency* and *projectid* and it is the primary key.|
| Managing Agency | magency | Three digit code of the distinct City agency managing the project.|
| Project ID | projectid | Alphanumeric code created by the sponsor agency that identifies a distinct project. A Project ID must be unique within a managing agency.|
| Managing Agency Acronym | magencyacro | Common acronym of the city agency managing the project.  This value is derived from the three digit managing agency code. |
| Managing Agency Name | magencyname |  Common name for the city agency managing the project.  This value is derived from the three digit managing agency code. |
| Description | description | Short description of the project as described by the sponsor agency.  If one FMS ID had many descriptions the longest description is reported by CPDB. |
| Sponsor Agency Acronym | sagencyacro | Array of the common acronyms of the city agency / agencies sponsoring the project.  This value is derived from the budget line(s). |
| Project type | projecttype |  Array of the short description(s) of the project type(s) based on the budget(s) funding the project. |
| Ten Year Plan Category * | typc | Array of three letter code(s) indicating what ten year plan category / categories the project supports. |
| $ City Cost (Non-Exempt) * | ccnonexempt | Sum of City Cost (Non-Exempt) funding across all commitments associated with the project. |
| $ City Cost (Exempt) * | ccexempt | Sum of City Cost (Exempt) funding across all commitments associated with the project. |
| $ City Cost | totalcityplannedcommit | Sum of City funding across all commitments associated with the project.  (If FISA is the source data $ City Cost is the sum of $ City Cost (Exempt) and $ City Cost (Non-Exempt)). |
| $ Non-City Cost State * | nccstate | Sum of State funding across all commitments associated with the project. |
| $ Non-City Cost Federal * | nccfederal | Sum of Federal funding across all commitments associated with the project. |
| $ Non-City Cost Other * | nccother | Sum of Other funding across all commitments associated with the project. |
| $ Non-City Cost | totalnoncityplannedcommit | Sum of Non-City funding across all commitments associated with the project. (If FISA is the source data $ Non-City Cost is the sum of $ Non-City Cost State, $ Non-City Cost Federal, and $ Non-City Cost Other). |
| $ Total Planned Commitments | totalcommit | Sum of $ City Cost and $ Non-City Cost, which reports the total planned commitments for the project allocated in the Capital Commitment Plan. |
| Min Date | mindate | Earliest date recorded in relation to the project in either the Capital Commitment Plan or Checkbook NYC. |
| Max Date | maxdate | Latest *Planned Commit Date* recorded in the Capital Commitment Plan associated with the project. |
| $ Total Spend | totalspend | Sum of all liquidations (check amounts) recorded in Checkbook NYC for the associated project. |
| $ Total Commit Spend | totalcommitspend | Sum of *Total Planned Commitments* and *Total Spend* | 
| Capital Commitment Plan version | ccpversion | Reports the version of the Capital Commitment Plan which the record is associated with. |


## V. Source Data
The following datasets and resources are used to create CPDB

**Primary base data resource**

### Capital Commitment Plan published by the NYC Office of Management and Budget (OMB)
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | OMB's Capital Commitment Plan |
| Description | Document published by OMB three times per year reporting all planned commitments for current and planned projects between today and until ten years into the future. | 
| Agency | OMB |
| Data Format | ASC or PDF |
| Update Frequency | 3 times per year |
| Update Means | Regular data exchange with OMB or scrape latest public Capital Commitment Plan |

**Spatial data resources**

### Department of Design and Construction (DDC)

##### Infrastructure projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DDC Capital Projects Infrastructure Projects |
| Description | Line shapefile capturing past, present, and planned infrastructure project, primarily capturing DOT and DEP projects | 
| Agency | DDC |
| Data Format | Shapefile |
| Update Frequency | Weekly |
| Update Means | Weekly data exchange with DDC |

##### Public buildings projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DDC Capital Projects Public Buildings |
| Description | Point shapefile capturing past, present, and planned public buildings projects | 
| Agency | DDC | 
| Data Format | Shapefile |
| Update Frequency | Weekly |
| Update Means | Weekly data exchange with DDC |

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

##### Intersection projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DOT Capital Projects Intersections |
| Description | Point shapefile capturing present and planned locations of DOT sponsored projects occurring at intersections | 
| Agency | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Automatic data pulls from DOT's capital projects map |

##### Bridge projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DOT Capital Projects Bridges |
| Description | Point shapefile capturing present and planned locations of DOT sponsored projects occurring on bridges | 
| Agency | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Automatic data pulls from DOT's capital projects map |

### Department of Parks and Recreation (DPR)

##### Parks projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DPR Capital Project Tracker |
| Description | XML file from NYC Open Data capturing present and planned locations of DPR sponsored and managed capital projects | 
| Agency | DPR | 
| Data Format | XML |
| Data Link | https://www.nycgovparks.org/bigapps/DPR_CapitalProjectTracker_001.xml |
| Update Frequency | Daily |
| Update Means | Automatic pulls from DPR's Capital Projects Tracker |

##### Parks properties
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | DPR Parks Properties |
| Description | Shapefile depicting all properties owned and managed by DPR | 
| Agency | DPR | 
| Data Format | Shapefile |
| Data Link | https://data.cityofnewyork.us/City-Government/Parks-Properties/rjaj-zgq7/data |
| Update Frequency | As needed |
| Update Means | Automatic pulls from Open Data |

### Office of Recovery and Resiliency (ORR)

##### Capital projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | ORR Capital Projects Map |
| Description | Map of capital projects that support resiliency and recovery efforts | 
| Agency | ORR | 
| Data Format | Shapefile |
| Data Link | https://maps.nyc.gov/resiliency/ |
| Update Frequency | As needed |
| Update Means | Automatic data pulls from ORR's capital projects map |

### Department of City Planning (DCP)

##### Facilities Database
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | Facilities Database |
| Description | The most comprehensive dataset of public and private facilities and program sites that shape the quality of New York City neighborhoods | 
| Agency | DCP | 
| Data Format | Shapefile |
| Data Link | https://capitalplanning.nyc.gov/facilities |
| Update Frequency | As needed |
| Update Means | Automatic data pulls from DPR's Facilities Explorer |

### School Construction Authority (SCA)
SCA plans, manages, and executes all capital projects related to NYC public schools including the construction of new schools and the renovation of existing schools.

##### Investment projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | SCA Capital Projects Investments |
| Description | SCA's capital projects that improve schools, such as laboratory upgrades | 
| Agency | SCA | 
| Data Format | PDF |
| Update Frequency | Annually |
| Update Means | Scrape latest public SCA Capital Plan |


##### Capacity projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | SCA Capital Projects Capacity |
| Description | SCA's capital projects that involve the construction of a school or the expansion of a school to increase the capacity of a school or school district | 
| Agency | SCA | 
| Data Format | PDF |
| Update Frequency | Annually |
| Update Means | Scrape latest public SCA Capital Plan |





