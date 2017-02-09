# Capital Projects Database
The Capital Projects Database, a data product produced by the New York City Department of City Planning (NYC Planning) Capital Planning team, is based on data published in the [FY 17 NYC Capital Commitment Plan](http://www1.nyc.gov/site/omb/publications/fy17-accp.page) published in October 2016.  NYC Planning adds value to the data extracted from the Capital Commitment Plan by linking these projects to data from the [FY 17 Capital Budget](http://www1.nyc.gov/assets/omb/downloads/pdf/cb6-16.pdf) and [Checkbook NYC](http://checkbooknyc.com/spending_landing/yeartype/B/year/118), and making geometries where possible for projects within the Capital Commitment Plan creating a map of the City's planned capital investments footprint.

The Capital Projects Explorer is a starting point for planners exploring what capital projects are taking place within an area, means to identify potential conflicts and synergies among capital projects, and resource for all City agencies to learn more about capital projects by providing easy access to high level information on planned capital projects.  This tool and associated data can help to foster interagency coordination and advance neighborhood-based planning, reducing situations of project conflicts and increasing opportunities to capitalize on project synderies, and support strategic capital investment planning across City agencies.

The primary function of the Capital Projects Explorer is to enable a user to easily access information about the capital budget, view all of the capital projects with spatial data on one map, explore key data points associated with a capital project.
 
This document provides key information about the Capital Projects Database, the data resource powering the Capital Projects Explorer.

We are constantly seeking feedback on how to improve and make this data resource most valuable.  Please reach out to the NYC Planning Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions or comments.

### Overview
| General information |
| :------------: | ------------- |
| Dataset name | "Capital Projects Database"
| Description | The Capital Projects Database captures high-level information on planned capital projects that appear in the FY 17 NYC Capital Commitment Plan published in October 2016, links these projects to data from the FY 17 Capital Budget and Checkbook NYC, and if possible spatially references the capital projects |
| Data format | Webmap, GeoJSON, Shapefile, CSV |
| Projection | WGS84 |
| Date last updated | 10/28/16 |

##Limitations and Disclaimers

The Capital Projects Database is only as good as the source data it extracts and aggregates.  Currently, the Capital Projects Database is the most comprehensive spatial data resource of planned City capital construction sites, but it does claim to capture all historic, current, or future City capital construction sites.  Many capital projects could not be spatially referenced because of limited discriptions; therefore, the map of capital projects is incomplete.  Also, there are known cases of projects being geocoded to office headquarters, rather than the site where the capital investment is being made; unfortunately, these records could not by systematically verified and corrected.  Through user feedback we look to resolve these limitation over time.

<b>Analyses Limitations:</b> As a result of these data limitations users should be careful in how they use these data in any analysis, espically spatial analyses.
For example: An analysis or comparision of number of projects planned for an area or total dollars planned to be spent in across neighborhoods should recgonize that not all of the projects are spatially referenced, projects may be incorrectly spatially referenced, one project can span across many locations, and this database is not authoritatively comprehensive.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [CapitalPlanning_DL@planning.nyc.gov](mailto:CapitalPlanning_DL@planning.nyc.gov).  For more detailed information on a specific capital project please reach out to the respective managing agency.


##Methodology

The Capital Projects Database is based on data extracted from the fiscal year 2017 Capital Commitment Plan released in October 2016, which is published by the NYC Office of Management and Budget (OMB) in a .pdf format in four volumes.  To transform a .pdf into a spatial database several steps need to be taken to extract the data from the pdfs, link the data to other datasets, and georeference captial projects.  Each of the data processing scripts used to create the Capital Projects Database as well as instructions on how to build the database are available on [NYC Planning's GitHub](https://github.com/NYCPlanning/capitalprojects_db).

### Data scraping
A JavaScript script was written and used to extract the budget line, FMS number, managing agency, project ID, description, cost description, city dollars committed, non-city dollars committed, and the planned commit date for each commitment in each volume of the fiscal year 2017 Capital Commitment Plan and write these key data points to an output .csv file.  The four .csv files outputted by the data scraping script were merged into a single .csv file, which was then loaded into PostGIS, which will be known as the commitments master table

### Creating the database tables
<b>Projects:</b>  A project is defined as being a distinct capital investment, which is identified by having a unique managing agency and project ID in FMS.  The combination of managing agency and project ID will be referred to as MA Project ID.  The Projects table reports information at the project level.  To create the project table unique MA Project ID were extracted from the commitments master table, along with the longest description associated with each unique MA Project ID, as well as the sum of city dollars committed and the sum of non-city dollars committed for each MA Project ID.

Since the three digit managing agency is not intuitive <b>managing agency acronym</b> and <b>managing agency name</b> fields were added to the Projects table.  The two fields were populated via a lookup table that contains the agency acronym and agency name associated with each agency code.

<b>Commitments:</b>  A commitment is defined as an individual amount of money that funds a project that draws from one budget and has a planned commit date.  The Commitments table has a many-to-one relationship with Projects, and is linked by MA Project ID, which means that many commitments are associated with one project.

To create the Commitments table unique MA Project ID, budget line, cost description, planned commit date were extracted from the commitments master table, along with the sum of city dollars committed and the sum of non-city dollars committed for each of the commitments.

<b>Budgets:</b>  A budget is defined as a large sum of money in which funds are drawn from and allocated towards projects via commitments.  The Budget table has a many-to-one relationship with Projects, and is linked by MA Project ID, meaning that many budgets can fund one project.

To create the Budgets table unique MA Project ID and budget line were extracted from the commitments master table, along with the sum of city dollars committed and the sum of non-city dollars committed for each of the MA Project ID and budget lines.

The fields <b>project type</b>, <b>sponsor agency acronym</b>, and <b>sponsor agency name</b> were added to the Budgets table.  The three fields were populated via a lookup table that contains the agency acronym, agency name, and project type associated with each project type code, which is the first one or two letters of the budget line.

A <b>total cost field</b> was added to each of the three tables and the sum of the city dollars and non-city dollars was used to generate each of the total cost fields in the Project, Commitments, and Budgets tables.

One goal of the Capital Planning Database is to map capital projects; therefore, spatial data needed to be created for each project where possible.  To distinguish between data attributes that were directly derived from the 2017 Capital Commitment Plan and data attributes that were created by NYC Planning the table <b>DCP Attributes</b> was created by extracting the managing agency, project ID, MA Project ID, and description from the Projects table.  The following fields were added to the DCP Attributes table:

* Location Status
* Geometry
* Geom Source
* Geom Source Dataset
* Geom Source Agency
* BBL
* BIN
* Segment ID
* Park ID
* Date Edited

A description of each of these fields as well as attribute values can be found in the Data Dictionary section of this document.  The purpose of these fields is to store geographic data points and track where the geographic came from or how the spatial data were generated.

### Adding geographic data 
To track what projects could / could not be georeferenced capital projects were classified as having one of four different location statuses: single site (discrete), multi-site (nondiscrete), sites tbd (tbd), and nonspatial (nonspatial).  A single site project is an investment that is taking place at one location, while a multi-site project is an investment that spans two or more locations.  If specific sites are not yet known for the investment then the project is classified as 'sites tbd,' while projects that do not have any site specific investments are designated as being nonspatial.

Each record was assigned a Location Status.  Some projects had their Location Status value populated systematically by pulling out key words from the description field, such as projects that contained “city wide” or “multi-site” in the description were marked as ‘non-discrete,’ or joining the Projects table to other datasets as described below.  Still, many of the records were populated manually, which required a person to read the description of the project, determine what the Location Status should be, and update the Location Status value accordingly.

Next, several methods were used to generate geographic data.

The first and simplest method involved <u>joining on geometries from existing datasets published by other City agencies</u> via MA Project ID or an exact match with the project description.  The name of the dataset and the agency that supplied the dataset from which the geometry was derived is noted in the Source Dataset and Source Agency fields in the DCP Attributes table, and the Geom Source field was marked as ‘Agency.’

To enable better rendering of geometries in Mapbox GL all line geometries were converted to polygons by adding a 15m buffer around each line segment.

For projects where the geometry was derived from an exisitng dataset using this first method, if the geometry associated with a project was one point or one polygon the Location Status was updated to be ‘discrete;’ if the geometry for the project was two or more points or two or more polygons the location status was set to ‘non-discrete.’

The second method to match geographic data with projects involved several iterations of <u>fuzzy string matching</u>, a technique of finding texts that approximately match a pattern.  This method looked to match park IDs, park names, and facility names from the parks properties dataset or facilities database, which have associated geometries, with the project description of projects with a Locaton Status of single site that were still missing a geometry.  If a match was found between the Projects table and another source using fuzzy string matching the match was manually verified before the geometry of the project in the Projects table was updated.  In these cases the Location Status was set to ‘discrete,’ the Geom Source was set to ‘algorithm,’ and the Source Dataset and Source Agency fields were updated with name of the dataset and name of the agency that supplied the data from which the geometry was derived.

The third method required a lot of <u>research</u> to be done to add geometries to the remaining projects marked as having a single site Location Status but no geometry.  The geometries of these records were populated manually and involved a DCP team member reading the description of the project and to the best of his/her ability give that project a spatial location by assigning it a bbl, bin, segment ID, or park ID.  After, the geometries associated with these spatial identifiers (i.e. bbl) were used to update the geometry for these projects DCP Attributes table.  If a project could not be tied to an exisiting geometry (i.e. bbl) or the existing geometry was errenous (i.e. a large park) then a DCP team member created a new geometry to represent the project.  At this point, all projects with a Location Status of single site have a geometry where it was possible to map that project.  Examples of descriptions for ‘discrete’ projects that were not spatially referenced include “Roof Replacement” and “Bio swale #12;” these sites exist but based on the information given the site could not be georeferenced.

More work needs to be done to verify geometries created for projects and clean up erroneous geometries; additionally,geometries for projects with a ‘non-discrete’ or ‘tbd’ Location Status need to be generated where possible.	

## Data Dictionary
The following lists and defines each of the data tables and associated fields in the Capital Projects Database.

<b>Projects</b>
Distinct capital investments, which are identified by having a unique Managing Agency and Project ID in FMS.

| Field Alias | Field Name | Description | Data Type | Source
| :------------------- | :------------------- | :------------------------------------------------------ | :------------------- | :------------------- |
| Managing Agency | managingagency | Three digit agency code that indicates what NY City agency is managing the project | text | Capital Commitment Plan |
| Project ID | projectid |  Alphanumeric ID for the project as defined by the managing agency | text | Capital Commitment Plan |
| MA Project ID | maprojid | The primary key and unique identifier for the projects table, which is a concatenation of Managing Agency and Project ID | text | DCP | 
| Description | description | Description of the project according to the managing agency | text | Capital Commitment Plan |
| Managing Agency Acronym | magency | The acronym of the managing agency | text | DCP |
| Managing Agency Name | magencyname | The full name of the managing agency | text | DCP |
| City Cost | citycost | The total of city funds committed for the project, which is the sum of the city cost field in the commitment table for the MA Project ID | double precision | Capital Commitment Plan | 
| Non-City Cost | noncitycost | The total of non-city funds committed for the project, which is the sum of the non-city cost field in the commitment table for the MA Project ID | double precision | Capital Commitment Plan | 
| Total Cost | totalcost | The total amount of funds committed to the project, which is the sum of City Cost and Non-City Cost | DCP | 

<b>Commitments</b>
An individual amount of money that funds a project that draws from one budget and has a planned commit date.  The Commitments table has a many-to-one relationship with Projects, and is linked by MA Project ID, which means that many commitments are associated with one project.

| Field Alias | Field Name | Description | Data Type | Source
| :------------------- | :------------------- | :------------------------------------------------------ | :------------------- | :------------------- |
| Managing Agency | managingagency | Three digit agency code that indicates what NY City agency is managing the project | text | Capital Commitment Plan |
| Project ID | projectid |  Alphanumeric ID for the project as defined by the managing agency | text | Capital Commitment Plan |
| MA Project ID | maprojid | The secondary key, which is a concatenation of Managing Agency and Project ID | text | DCP | 
| Budget Line | budgetline | Alphanumeric ID for the budget from which funds are drawn to fund the commitment | text | Capital Commitment Plan |
| Planned Commit Date | plancommdate | The month and year the funds will be commited to the managing agency | text | Capital Commitment Plan |
| Cost Description | costdescription | Description of the what the planned commitment will be spent on in relation to the project | text | Capital Commitment Plan |
| City Cost | citycost | The amount of city funds committed to the commitment | double precision | Capital Commitment Plan | 
| Non-City Cost | noncitycost | The amount of non-city funds committed to the commitment | double precision | Capital Commitment Plan | 
| Total Cost | totalcost | The total amount of funds committed to the commitment, which is the sum of City Cost and Non-City Cost | double precision | DCP | 

<b>Budgets</b>
A budget is large sum of money from which funds are drawn and allocated towards projects via commitments.  The Budgets table has a many-to-one relationship with Projects, and is linked by MA Project ID, meaning that many budgets can fund one project.

| Field Alias | Field Name | Description | Data Type | Source
| :------------------- | :------------------- | :------------------------------------------------------ | :------------------- | :------------------- |
| Managing Agency | managingagency | Three digit agency code that indicates what NY City agency is managing the project | text | Capital Commitment Plan |
| Project ID | projectid |  Alphanumeric ID for the project as defined by the managing agency | text | Capital Commitment Plan |
| MA Project ID | maprojid | The secondary key, which is a concatenation of Managing Agency and Project ID | text | DCP |  
| Budget Line | budgetline | Alphanumeric ID for the budget from which funds are drawn to fund the commitment | text | Capital Commitment Plan |
| City Cost | citycost | The total amount of city funds committed to the project from the budget line | double precision | Capital Commitment Plan | 
| Non-City Cost | noncitycost | The total amount of non-city funds committed to the project from the budget line | double precision | Capital Commitment Plan | 
| Total Cost | totalcost | The total amount of funds committed to the project from the budget line, which is the sum of City Cost and Non-City Cost | double precision | DCP | 
| Project Type | projecttype | The budget category, which is defined by the first one or two letters of a budget line | text | Capital Commitment Plan | 
| Sponsor Agency Acronym | sagency | The acronym of the sponsor agency, which is based off of the Project Type | text | DCP |
| Sponsor Agency Name | sagencyname | The full name of the sponsor agency | text | DCP |

<b>DCP Attributes</b>
Data created by NYC Planning to add value to data derived from the Capital Commitment Plan and other published sources.  This table contains the spatial data.

| Field Alias | Field Name | Description | Data Type | Source
| :------------------- | :------------------- | :------------------------------------------------------ | :------------------- | :------------------- |
| Managing Agency | managingagency | Three digit agency code that indicates what NY City agency is managing the project | text | Capital Commitment Plan |
| Project ID | projectid |  Alphanumeric ID for the project as defined by the managing agency | text | Capital Commitment Plan |
| MA Project ID | maprojid | The primary key and unique identifier for the projects table, which is a concatenation of Managing Agency and Project ID | text | DCP | 
| Description | description | Description of the project according to the managing agency | text | Capital Commitment Plan |
| Location Status | locationstatus | Description of the location of the project.  Possible values are: Single site: the project is located at one location; Multi-site: the project spans multiple locations; Sites TBD: The location(s) of the projects have yet to be identified but a general area where the project may take place may be known; Non-spatial: The project is not assoicated with one or many locations | text | DCP | 
| Geom Source | geomsource | Note about how the geometry was created | text | DCP |
| Source Dataset | sourcedataset | If the geometry was not created by DCP the source dataset where the geometry was derived from is noted | text | DCP |
Source Agency | sourceagency | If the geometry was not created by DCP and came from a spatial dataset created by another agency the agency where the geometry came from is noted | text | DCP |
| BBL | bbl | The ID(s) of the NYC tax lot(s) where the project is taking place | text | DCP |
| BIN | bin | The ID(s) of the NYC building(s) where the project is taking place | text | DCP |
| Segment ID | segmentid | The ID(s) of the NYC LION segment(s) where the roadway project is taking place | text | DCP |
| Park ID | parkid | The ID(s) of the NYC park(s) where the project is taking place | text | DCP |
| Geometry | geom | The geometry of the project. Can be multipoint or multipolygon | geometry | Agency or DCP | 


Data attribute definitions
DCP Attributes, Location Status
| Attribute | Alias | Definition |
| :------------------- | :------------------- | :------------------- | :------------------- |
| discrete | Single Site | The project is at one site, which is a building, tax lot, contigious street segment, intersection or park |
| nondiscrete | Multi Site | The project spans multiple sites |
| tbd | Sites TBD | The specific site(s) have not yet been identified, but a general area where the project will take place many have been identified |
| nonspatial | Non Spatial | The project is not tied to a physical location |



## Source Data
The following datasets were used to populate the Capital Projects Explorer.  The data sources that are publisehd online as open data are automatically downloaded and integrated at regular intervals.  The database is regularly checked thoroughly to identify problems with the update processes or major changes to the source data. 

### Department of Design and Construction (DDC)
DDC is the City's primary capital construction manager; therefore, DDC centrally manages much of the City’s capital projects portfolio.

##### Infrastructure projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Dataset Name | "DDC Capital Projects Infrastructure Projects" |
| Agency Abbreviation | DDC |
| Data Format | Shapefile |
| Update Frequency | Weekly |
| Update Means | Data exchange with DDC |
| Date Updated | 2/19/2016 |
| Date Received | 2/22/2016 |
| Data Link | http://maps.nyc.gov/doitt/nycitymap/ |
| Notes | This dataset acts as a primary data source; therefore, if other datasets have the same project CPDB rejects duplicate records from other data sources | 

##### Public buildings projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "DDC Capital Projects Public Buildings" |
| Agency Abbreviation | DDC | 
| Data Format | Shapefile |
| Update Frequency | Weekly |
| Update Means | Data exchange with DDC |
| Date Updated | 2/19/2016 |
| Date Received | 2/22/2016 |
| Data Link | http://maps.nyc.gov/doitt/nycitymap/ |
| Notes | This dataset acts as a primary data source; therefore, if other datasets have the same project CPDB rejects duplicate records from other data sources | 

### Department of Transportation (DOT)

##### Street reconstruction projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "DOT Capital Projects Street Reconstruction" |
| Agency Abbreviation | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Pulls from DOT's capital projects map |
| Date Updated  | 3/1/2016 |
| Date Received | 3/1/2016 |
| Data Link | |
| Notes | | 

##### Intersection projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "DOT Capital Projects Intersections" |
| Agency Abbreviation | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Pulls from DOT's capital projects map |
| Date Updated  | 3/1/2016 |
| Date Received | 3/1/2016 |
| Data Link | |
| Notes | | 

##### Bridge projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "DOT Capital Projects Bridges" |
| Agency Abbreviation | DOT | 
| Data Format | Shapefile |
| Update Frequency | Three times per year |
| Update Means | Request file from agency |
| Date Updated | 3/18/2016 |
| Date Received | 3/18/2016 |
| Data Link | |
| Notes | | 

### Department of Parks and Recreation (DPR)

##### Parks projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "DPR Capital Project Tracker"|
| Agency Abbreviation | DPR | 
| Data Format | XML |
| Update Frequency | Daily |
| Update Means | Pulls from DPR's Capital Projects Tracker |
| Date Updated | 4/9/2015 |
| Date Received| 2/10/2016 |
| Data Link | https://www.nycgovparks.org/bigapps/DPR_CapitalProjectTracker_001.xml |
| Notes | | 

### School Construction Authority (SCA)
SCA plans, manages, and executes all capital projects related to NYC public schools including the construction of new schools and the renovations of existing schools.

##### Capacity projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "SCA Capital Projects Capacity" |
| Agency Abbreviation | SCA | 
| Data Format | CSV |
| Update Frequency | Annually |
| Update Means | Systematic transformation of SCA data |
| Date Updated | 7/1/2016 |
| Date Received| 7/1/2016 |
| Data Link | |
| Notes | These data were scraped from static PDF files published by SCA documenting SCA's capital plan and transformed into a CSV | 

##### Investment projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "SCA Capital Projects Investments" |
| Agency Abbreviation | SCA | 
| Data Format | CSV |
| Update Frequency | Annually |
| Update Means | Systematic transformation of SCA data |
| Date Updated | 7/1/2016 |
| Date Received| 7/1/2016 |
| Data Link | |
| Notes | These data were scraped from static PDF files published by SCA documenting SCA's capital plan and transformed into a CSV |

### Office of Recovery and Resiliency (ORR)
ORR works with agencies, partners, advocates, and industries to advance long-term plans for growth and resiliency by improving the City's physical infrastructure, economy, and quality of life.

##### Capital projects
|               |                                    |
| --------------------------------- | ------------------------------------------------------- |
| Name | "ORR Capital Projects" |
| Agency Abbreviation | ORR | 
| Data Format | Shapefile |
| Update Frequency |  |
| Update Means | Automatic data pulls from ORR's capital projects map |
| Date Updated | |
| Date Received| 8/1/2016 |
| Data Link | https://maps.nyc.gov/resiliency/ |
| Notes | | 

## Database structure
Currently, the Capital Projects Explorer consists of one table.  Each record in the table represents one capital "project."  One "project" can have one or multiple geometries represting the site(s) where the capital project is occurring, but a record can only have one geometry type (MultiPoint or MultiPolygon).  

		
