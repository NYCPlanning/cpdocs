# Capital Projects Explorer
The Capital Projects Explorer integrates disparate datasets of capital projects published by capital agencies into one database and map-based data explorer.

The Capital Projects Explorer’s primary purpose is to provide a common operational picture to capital planners and budget staff across City agencies, which can in turn minimize conflicts among different agencies’ capital projects, maximize opportunities for coordinated capital investment planning and funding alignment, and provide a starting point for integrated neighborhood-based planning. This is certainly not a complete map of capital construction sites funded by NYC, but the Capital Projects Explorer is currently the best starting point for exploring capital projects in NYC.

Special thanks to the NYC Departments of Parks and Recreation, Transportation, Design and Construction, the School Construction Authority, and the Mayor’s Office of Recovery and Resiliency for publishing spatial data on capital projects.



### Overview
| General information |
| :------------: | ------------- |
| Dataset name | "Capital Projects Explorer"
| Description | The Capital Projects Explorer captures high-level information on past, present, and planned capital projects in NYC by aggregating spatial data on capital projects published by capital agencies. |
| Data format | Webmap, GeoJSON, Shapefile, CSV |
| Projection | WGS84 |
| Date last updated | 10/28/16 |

###Limitations and Disclaimers

The Capital Projects Explorer is only as good as the source data it aggregates. Currently, there is no data standard for capital project mapping and agencies are not required to map their capital projects; therefore, the Capital Projects Explorer makes some assumptions to aggregate and normalize the data into one data table. As a result, this data source has some major limitations.

<b>Duplicates</b> This version of the Capital Projects Explorer includes some duplicate records for the same capital project because some of the source datasets have overlapping content, but different unique identifiers for a project, making it difficult to systematically identify and reconcile duplicate records.

<b>Inconsistent data standards</b> Capital agencies manage their capital projects data separately and have varying data standards that meet their needs; therefore, the Capital Projects Explorer makes some assumptions to reconcile key common attributes across datasets and integrate the data into one database.

<b>Project definition</b> Capital agencies define capital projects differently; therefore, the projects in this explorer vary in size, scope, and impact. The inconsistent definition of a capital project has the potential to skew analyses generated from these data - e.g. comparing the number of capital projects in or amount of funding dedicated to a neighborhood to another con produce misleading results.

<b>Completeness</b> This dataset does not capture the entirety of NYC's Capital Budget. The Capital Projects Explorer is built using records from agencies' project management systems, which do not always maintain a link to budget lines, making it impossible to account for the whole Capital Budget.

<b>Different update frequencies</b> Data from source agencies are updated at various frequencies, ranging from daily updates to infrequent updates. As a result, the freshness of the data in the Capital Projects Explorer varies depending on the data source.

As a result of these data limitations and inconsistencies, the Capital Projects Explorer is not an analysis tool, it does not report any metrics, and the data should not be used for quantitative analyses - it is built for planning coordination purposes only.

Please consult NYC Planning’s Capital Planning Docs for more details about these data limitations.


##Methodology

### Data Processing 

The Capital Projects Explorer aggregates records from numerous datasets designed for different purposes; therefore, the data need to undergo several stages of transformation before being integrated into the single table.  The stages are described below and all of the data processing scripts used are available on the NYC Planning GitHub page.

<b>Assembly.</b>  First, the desired columns in the source data are mapped to the fields in the Capital Projects Explorer's data schema.  Second, the source data values are formatted to match the datatype of the corresponding field.  Next, source data values are standardized before being loaded into the Capital Projects Explorer.  Data standardization mostly occurs in the managing agency, sponsor agency, and current status fields.  Lastly, missing data points are identified and filled in if it is possible to derive the missing values from other existing data attributes.

<b>Geoprocessing.</b>  The format of the source datasets vary.  If the source data are not in a spatial data format spatial data was created for the Capital Projects Explorer.  The process of creating spatial data varies by source dataset but generally it involves joining the source dataset to an existing spatial dataset by a common data attribute.

<b>Duplicate record removal.</b>  Several source datasets have overlapping content.  Duplicate records are identified and reconciled when two or more records shared the same FMS ID.  If two or more records share the same FMS ID the record from the most authoritative data source is kept.  The authoritative ranking of data sources is 1) DDC 2) DOT 3) DPR 4) SCA 5) ORR with DDC being the most authoritative data source.


## Data Dictionary
The following table lists and defines each of the fields presented in the Capital Projects Explorer as they are organized in the database from left to right.

| Field Alias | Field Name | Description | Source                                            |
| :------------------- | :------------------- | :------------------------------------------------------ | :---------- |
| Random ID | rid | Auto incrementing integer that is automatically generated each time a new row is added in the table. | DCP |
| Capital Planning ID | cpid | Unique capital planning ID that concatenates managing agency acronym and project ID. | DCP |
| Project ID | projectid | Project ID as defined by the data source. | Agency | 
| FMS ID | maprojid | FMS ID as defined by the data source or as generated by DCP by appending the managing agency code to the beginning of the project ID.  Valid FMS ID format = three digit agency code+' '+project type acronym+project ID.  Example: 805 ARDXYZ123 | Agency |
| Name | name | Name of the project. | Agency |
| Description | descriptio | Description of the project. | Agency |
| Type | type | Type of capital project. | Agency |
| Category | category | Category the project is grouped into according to DCP. | DCP |
| Current Status | cpstatus | Current status of the project normalized by DCP.  Valid values are: Cancelled, Complete, Construction, Design, Other, Planning, Procurement, Proposed. | Agency - DCP standardized | 
| Agency Project Status | astatus | Current status as recorded in the agency's raw data | Agency |
| Managing Agency | magency | Acronym of the government agency managing the project. | Agency - DCP standardized | 
| Sponsor Agency | sagency | Acronym of the government agency sponsoring or funding the project | Agency - DCP standardized | 
| Funding Amount | fundamount | Total exact funding amount allocated to or needed for the project | Agency |
| Minimum Funding | fundmin | Minimum funding amount allocated to or needed for the project.  Only for projects that have a minimum and/or maximum funding amount defined | Agency |
| Maximum Funding | fundmax | Maximum funding amount allocated to or needed for the project.  Only for projects that have a minimum and/or maximum funding amount defined | Agency |
| Funding Status | fundstatus | Indicates if the project is funded, underfunded, or not funded | Agency |
| Funding Source | fundsource | Source of any funds for the project | Agency |
| Construction Start Date | constart | Actual or expected date of construction starting. | Agency |
| Construction End Date | conend | Actual or expected date of construction ending. | Agency |
| Fiscal Year Construction Complete | fyconend | Actual or expected fiscal year of construction ending.  Valid formats: YYYY | Agency |
| Contact | contact | Contact name and number for the person responsible		 for managing the project. | Agency |
| Source | source | Acronym of the agency that supplied the dataset from which the record was derived | DCP |
| Source Dataset | sourcedata | Name of the source dataset where the record was derived. | DCP |
| Source Link | sourcelink | Hyperlink to the raw data from which the record was derived. | DCP |
| Geometry | geom | The geometry of the project. Can be multipoint, multiline, or multipoly | Agency or DCP | 

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

		
