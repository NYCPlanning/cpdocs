# City Planning Facilities Database
The Facilities Database (FacDB), a data product produced by the New York City (NYC) Department of City Planning (DCP) Capital Planning Division, captures the location, type, and capacity of public and private facilities ranging across six domains:

* Health Care and Human Services
* Youth, Education, and Child Welfare
* Public Safety, Emergency Services, and Administration of Justice
* Core Infrastructure and Transportation
* Parks, Cultural, and Other Community Facilities
* Administration of Government

This data resource provides agencies and communities with easy access to data and neighborhood context needed for site planning, assessing service delivery, preparing neighborhood plans, or informing capital investment decisions. The facilities and program sites are generally operated, funded, licensed, or certified by a City, State, or Federal government agency. The facilities which are included are valuable for planning purposes because of the social services they provide and their role in land use typology which impacts activity in the neighborhood. For example parking lots and garages (including commerical garages) are captured in the database, both because they are an asset that residents and visitors use and because they could indicate increased vehicular traffic in the area.

Currently, FacDB aggregates and synthesizes data sourced from 42 agencies, recording more than 31,000 facilities throughout NYC. A full listing of the facility categories is provided in the [Overview](https://nycplanning.github.io/cpdocs/facilitiesdb/#overview).

Historically, these records were updated only once per year in DCP's Selected Facilities and Program Sites Database which is now being retired. Beginning with this September _, 2016 release, the Facilities Database is rebranded and being produced using a revamped approach that relies heavily on automating the collection and transformation of data that agencies already publish. The process has been automated to pull from all available source datasets once per month, so that the database will capture and incorporate any changes in the source data. 85% of the data sources are open datasets that agencies publish independently.

We are constantly looking for ways to improve and add additional value to the database. Please reach out to the NYC DCP Capital Planning team at [CapitalPlanning_DL@planning.nyc.gov](mailto:CapitalPlanning_DL@planning.nyc.gov) with any suggestions.

### Overview

| General information |
| :------------: | ------------- |
| Dataset Name | "Facilities Database "|
| Description | The Facilities Database (FacDB) captures the locations and descriptions of public and private facilities ranging from the provision of social services, recreation, education, to solid waste management|
| Data format | GeoJSON, Shapefile, CSV |
| Projection | WGS84 |
| Date last updated | 09/12/16 |

##### Facilities Classification Heirarchy

The following table summarizes the categories of facilities that are included in the database. Within each Facility Subgroup, there are more granular Facility Types.

| Domain | Facility Group | Facility Subgroup |
| :-- | :-- | :-- |
| Administration of Government | Offices | Offices |
| Administration of Government | Other Property | Miscellaneous Use |
| Administration of Government | Other Property | No Use |
| Administration of Government | Other Property | Undeveloped |
| Administration of Government | Parking, Maintenance, and Storage | Maintenance |
| Administration of Government | Parking, Maintenance, and Storage | Parking |
| Administration of Government | Parking, Maintenance, and Storage | Storage |
| Core Infrastructure and Transportation | Transportation | Airports and Heliports |
| Core Infrastructure and Transportation | Transportation | Bus Depots and Terminals |
| Core Infrastructure and Transportation | Transportation | Parking Lots and Garages |
| Core Infrastructure and Transportation | Transportation | Ports and Ferry Landings |
| Core Infrastructure and Transportation | Transportation | Rail Yards and Maintenance |
| Core Infrastructure and Transportation | Wastewater and Waste Management | Solid Waste Processing |
| Core Infrastructure and Transportation | Wastewater and Waste Management | Solid Waste Transfer and Carting |
| Core Infrastructure and Transportation | Wastewater and Waste Management | Wastewater Treatment Plant |
| Health Care and Human Services | Health Care | Chemical Dependency |
| Health Care and Human Services | Health Care | Hospitals and Clinics |
| Health Care and Human Services | Health Care | Mental Health |
| Health Care and Human Services | Health Care | Other Health Care |
| Health Care and Human Services | Health Care | Residential Health Care |
| Health Care and Human Services | Human Services | Housing and Homeless Services |
| Health Care and Human Services | Human Services | Legal and Intervention Services |
| Health Care and Human Services | Human Services | Programs for People with Disabilities |
| Health Care and Human Services | Human Services | Senior Services |
| Health Care and Human Services | Human Services | Soup Kitchens and Food Pantries |
| Health Care and Human Services | Human Services | Workforce Development |
| Parks, Cultural, and Other Community Facilities | Cultural Institutions | Cultural Institutions |
| Parks, Cultural, and Other Community Facilities | Cultural Institutions | Historical Societies |
| Parks, Cultural, and Other Community Facilities | Cultural Institutions | Museums |
| Parks, Cultural, and Other Community Facilities | Cultural Institutions | Other Cultural Institutions |
| Parks, Cultural, and Other Community Facilities | Historical Sites | Historical Sites |
| Parks, Cultural, and Other Community Facilities | Libraries | Academic Libraries |
| Parks, Cultural, and Other Community Facilities | Libraries | Public Libraries |
| Parks, Cultural, and Other Community Facilities | Parks and Plazas | Cemetery |
| Parks, Cultural, and Other Community Facilities | Parks and Plazas | Gardens |
| Parks, Cultural, and Other Community Facilities | Parks and Plazas | Parks |
| Parks, Cultural, and Other Community Facilities | Parks and Plazas | Preserves and Conservation Areas |
| Parks, Cultural, and Other Community Facilities | Parks and Plazas | Recreation and Waterfront Sites |
| Parks, Cultural, and Other Community Facilities | Parks and Plazas | Streetscapes, Plazas, and Malls |
| Public Safety, Emergency Services, and Administration of Justice | Emergency Services | Emergency Services |
| Public Safety, Emergency Services, and Administration of Justice | Justice and Corrections | Courthouses and Judicial |
| Public Safety, Emergency Services, and Administration of Justice | Justice and Corrections | Detention and Correctional |
| Public Safety, Emergency Services, and Administration of Justice | Public Safety | Police Services |
| Youth, Education, and Child Welfare | Camps | Camps |
| Youth, Education, and Child Welfare | Child Welfare | Child Nutrition |
| Youth, Education, and Child Welfare | Childcare | Childcare |
| Youth, Education, and Child Welfare | Childrens Services | Childrens Services |
| Youth, Education, and Child Welfare | Schools | Colleges or Universities |
| Youth, Education, and Child Welfare | Schools | Non-public Schools |
| Youth, Education, and Child Welfare | Schools | Other Schools Serving Students with Disabilities |
| Youth, Education, and Child Welfare | Schools | Preschools |
| Youth, Education, and Child Welfare | Schools | Proprietary Schools |
| Youth, Education, and Child Welfare | Schools | Public Schools |
| Youth, Education, and Child Welfare | Youth Services | Youth Services |



## Limitations and Disclaimers

The FacDB is only as good as the source data it aggregates. Currently, FacDB is the most comprehensive, spatial data resource of facilities run by public and non-public entities in NYC, but it does not claim to capture every facility within the specified domains. Many records could not be geocoded. There are also known to be cases when the address provided in the source data is for a headquarters office rather the facility site location. Unfortunately these could not be systematically verified. For more detailed information on a specific facility please reach out to the respective oversight agency.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [CapitalPlanning_DL@planning.nyc.gov](mailto:CapitalPlanning_DL@planning.nyc.gov).



## Methodology

### Data Processing

Since the facility records are aggregated from many datasets designed for different purposes, the data has to undergo several stages of transformation to reach its final state. The stages are described below and all the scripts used are available on the [NYC Planning GitHub page](https://github.com/NYCPlanning/scripts/tree/master/facilities-database/assembly).

**Assembly.**
First, the desired columns in the source data get mapped to the columns in FacDB schema. Many values also need to be recoded and the facility records then need to be classified. The facilities are classified using categories or descriptions provided by the agency. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are also cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description.

**Geoprocessing.**
Many of the source datasets only provide addresses, no coordinates, and visa versa. Records without coordinates are geocoded with the [GeoClient API](https://developer.cityofnewyork.us/api/geoclient-api) using the Address and either the Borough or ZIP Code to get the coordinates and the BIN and BBL. Records with only coordinates and no addresses are processed by doing a spatial join with MapPLUTO to get the BBL and then the BBL is run through GeoClient to get the address and other location related details like Borough, ZIP Code, and BIN. There are also many cases where the coordinates provided by the agency fall in the road bed, rather than inside a BBL boundary, due to the geocoding technique used by the source. In these cases, the coordinates were left as provided, and the BBL was joined on according to which BBL edge was closest to the point coordinates. This closest BBL was then run through GeoClient to fill in missing information. Each record in the database is flagged in the with a code for the geoprocessing technique that was used to complete all of its information.

**Duplicate Record Removal.** Several of the source datasets have content which overlaps with other datasets. Duplicate records were identified by querying for all the records which fall on the same BBL as a record with the same Facility Group. The contents of this subset is this examined for similarities in the Facility Name. The record with the most complete or most updated information was kept and other duplicate record is removed from the database. In this release, _ duplicate records were removed.



## Data Dictionary

The following table lists and defines each of the fields presented in the Facilities Database as they are organized in the database from left to right.

| Field Alias | Field Name | Description |
| :------------------- | :------------------- | :------------------------------------------------------ |
| Global Unique Identifier | guid | Universal Unique Identifier.  When a row is added to the table the guid is automatically generated, enabling database replication. |
| ID | id | An alpha numeric unique identifier created and maintained by the database admin that is X number of characters long and a concatenation of A, B, and C. |
| Old ID | idold | Non-unique identifier generated and maintained by the former database admin that relates to old version of SFPSD. |
| Agency ID | idagency | Non-unique identifier generated and maintained by the data admin of the parent agency that relates to the record in the source dataset. |
| Facility Name | facilityname | The name of the facility in proper case. |
| Address Number | addressnumber | The address number of where the facility is located. Generated by GeoSupport when not provided in the source data. |
| Street Name | streetname | The name of the street where the facility is located. Generated by GeoSupport. |
| Address | address | The concatenated value of AddressNum and StreetName of where the facility is located. |
| City | city | The name of the addressed city where the facility is located. Generated by GeoSupport. |
| Borough | borough | The full name the borough the facility is within. |
| Borough Code | boroughcode | The number value representing the borough the facility is within. |
| ZIP Code | zipcode | The ZIP Code the facility is within. |
| BBL | bbl | The BBL(s) the facility is located on. |
| BIN | bin | The BIN(s) the facility is located on. |
| Park ID | parkid | The Park ID(s) associated with the facility. |
| X Coordinate | xcoord | The X coordinate of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Y Coordinate | ycoord | The Y coordinate of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Latitude | latitude | The latitude of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Longitude | longitude | The longitude of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Facility Type | facilitytype | The value representing the facility type, the most granular category of facilities. |
| Domain | domain | The value representing the facility domain, the broadest category. |
| Facility Group | facilitygroup | The value representing the group type, the second broadest category. |
| Facility Sub-Group | facilitysubgroup | The value representing the subgroup type. |
| Agency Classification 1 | agencyclass1 | The unmodified classification or descriptor of the facility record provided in the source data. Depending on the user's needs, these descriptors may provide additional details not captured in the Facility Type. |
| Agency Classification 2 | agencyclass2 | An additional unmodified classification or descriptor of the facility record provided in the source data. |
| COLP Primary Use Type | colpusetype | The Primary Use Type provided for the facility in the City Owned and Leased Properties (COLP) dataset. |
| Capacity | capacity | How many of capacity type/unit the facility is intended to hold. |
| Utilization | utilization | How many of capacity type/unit are being utilized at the facility. |
| Capacity Type | capacitytype | The value representing the unit type of capacity, such as beds, visitors, seats, etc. |
| Utilization Rate | utilizationrate | The ratio of the of utilization over the total facility capacity. |
| Area | area | The total area of the site measured in the Area Type unit. |
| Area Type | areatype | The unit of measurement for Area. |
| Service Area | servicearea | Indicates if the facility serves a regional or local population, which is determined by the Facility Type of facility according to Fair Share guidelines.  Value is calculated based on Facility Type. |
| Operator Type | operatortype | Indicates whether the operating entity is public or non-public. |
| Operator Name | operatorname | The name of the operating entity. |
| Operator Abbreviation | operatorabbrev | Abbreviation for the operating entity. |
| Oversight Agency | oversightagency | The name of the agency overseeing the facility. |
| Overight Abbreviation | oversightabbrev | Abbreviation for the oversight agency. |
| Date Active | dateactive | The date the facility became active in the database. |
| Date Inactive | dateinactive | The date the facility became inactive in the database. |
| Inactive Status | inactivestatus | The value indicating the status of the facility, whether it is in operation or not in operation.  Value is calculated based on DateInactive.  If DateInactive is not NULL then Status is Inactive. |
| Tags | tags | A series of tags classifying the facility. |
| Notes | notes | A space for the database admin to include any freestyle notes about the record. |
| Date Source Data Received | datesourcereceived | The date the source data was received from the parent agency. |
| Date Source Data Updated | datesourceupdated | The date the source data was updated within the parent database. |
| Date Created | datecreated | The date the record was created. |
| Date Edited | dateedited | The date the record was edited. |
| Creator | creator | The user who created the record. |
| Editor | editor | The user who last edited the record. |
| Geom | geom | How the feature is spatially represented. |
| Agency Source | agencysource | The Agency whose data was used as the source for the record. |
| Source Dataset Name | sourcedatasetname | The name of the dataset the record came from. |
| Link to Data | linkdata | Link to view and/or description of data. |
| Link to Direct Download | linkdownload | Link to directly download data. |
| Data Type | datatype | Format of the raw data received from the source. Examples: Shapefile, List of Addresses, or CSV with Coordinates. |
| Data Refresh Means | refreshmeans | The method for updating the records from this source dataset. |
| Data Refresh Frequency | refreshfrequency | The frequency of scheduled updates based on how frequently the source data is updated. |
| Processing Flag | processingflag | A text flag which indicates how the record was geoprocessed to fill in all required information, including geocoding and spatial joins. |
| Building ID | buildingid | The ID of the building that the school is within. |
| Building Name | buildingname | The name of the school(s) within the building. |
| Organization Level | schoolorganizationlevel | The Organization Level of the school. |
| Children | children | Indicates if the facility serves children, which are persons that are 12 years old or younger. |
| Youth | youth | Indicates if the facility serves youth, which are persons that are 13 years old or less than 18 years old. |
| Seniors | senior | Indicates if the facility serves seniors, which are persons that are 65 years old or older. |
| Families | family | Indicates if the facility serves familes, which are groups of persons that span multiple age cohorts. |
| Disabilities | disabilities | Indicates if the facility serves persons with disabilities. |
| Dropouts | dropouts | Indicates if the facility serves dropouts. |
| Unemployed | unemployed | Indicates if the facility serves unemployed persons. |
| Homeless | homeless | Indicates if the facility serves homeless persons. |
| Immigrants | immigrants | Indicates if the facility serves immigrants. |
| Group Quarters | groupquarters | Indicates if the facility contains group living quarters. |



## Source Data

The following datasets were used to populate the Facilities Database. The data sources that are published online as open data are automatically downloaded and aggregated once a month to capture any updates provided by the source agency. The aggregated database is thoroughly checked through once per year to identify any problems with the process or major changes in the source data and how it's structured.

### Amtrak (Amtrak)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | Amtrak |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Brooklyn Bridge Park Corporation (BBPC)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | BBPC |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Food Bank for New York City (FBNYC)

| | |
| -- | -- |
| Dataset Name | "FBNYC Food Pantry Soup Kitchen List 8-5-16" |
| Agency Abbreviation | FBNYC |
| Data Format | CSV with Coordinates |
| Update Frequency | Quarterly |
| Update Means | Request file from agency |
| Date Updated | 8/5/16 |
| Date Received | 8/5/16 |
| Notes | |

### Federal Bureau of Prisons (FBOP)

| | |
| -- | -- |
| Dataset Name | "Our Locations" |
| Agency Abbreviation | FBOP |
| Data Format | Addresses |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |

### Hudson River Park Trust (HRPT)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | HRPT |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Metropolitan Transportation Authority - Long Island Railroad (MTA-LIRR)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | MTA-LIRR |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Metropolitan Transportation Authority - Metro North (MTA-MN)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | MTA-MN |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Metropolitan Transportation Authority - New York City Transit (MTA-NYCT)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | MTA-NYCT |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Administration for Childrens Services (NYCACS)

| | |
| -- | -- |
| Dataset Name | "Contractor Data" |
| Agency Abbreviation | NYCACS |
| Data Format | CSV with Coordinates |
| Update Frequency | Annually |
| Update Means | Request file from agency |
| Date Updated | 7/20/16 |
| Date Received | 7/20/16 |
| Notes | |

### New York City Business Integrity Commission (NYCBIC)

| | |
| -- | -- |
| Dataset Name | "Approved licensees and registrants for trade waste" |
| Agency Abbreviation | NYCBIC |
| Data Format | CSV with Coordinates |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYC Open Data |
| Date Updated | 9/5/14 |
| Date Received | 7/1/16 |
| Notes | |

### New York City Department of Consumer Affairs (NYCDCA)


| | |
| -- | -- |
| Dataset Name | "Legally Operating Businesses" |
| Agency Abbreviation | NYCDCA |
| Data Format | CSV with Address |
| Update Frequency | Nightly pull |
| Update Means | Geocode - Pull from NYC Open Data |
| Date Updated | 6/24/16 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Citywide Administrative Services (NYCDCAS)

Data was obtained from DCAS's 2016 Gazetteer requests for Fire Department of New York (NYCFDNY) and New York Police Department (NYCNYPD).

| | |
| -- | -- |
| Dataset Name | "Gazetteer 2016" |
| Agency Abbreviation | NYCDCAS |
| Data Format | CSV with Address |
| Update Frequency | Annually |
| Update Means | Geocode - Request from Agency |
| Date Updated | 8/20/16 |
| Date Received | 8/20/16 |
| Notes | |

### New York City Department of Cultural Affairs (NYCDCLA)

| | |
| -- | -- |
| Dataset Name | "DCLA Cultural Organizations" |
| Agency Abbreviation | NYCDCLA |
| Data Format | CSV with Address |
| Update Frequency | Nightly pull |
| Update Means | Geocode - Pull from NYC Open Data |
| Date Updated | 3/22/16 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Environmental Protection (NYCDEP)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | NYCDEP |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |


### New York City Department for the Aging (NYCDFTA)

| | |
| -- | -- |
| Dataset Name | "DFTA Contracts" |
| Agency Abbreviation | NYCDFTA |
| Data Format | CSV with Address |
| Update Frequency | Weekly |
| Update Means | Geocode - Pull from NYC Open Data |
| Date Updated | 7/15/16 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Corrections (NYCDOC)

| | |
| -- | -- |
| Dataset Name | "Correction Facilities Locations" |
| Agency Abbreviation | NYCDOC |
| Data Format | Addresses |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |

### New York City Department of Education (NYCDOE)

| | |
| -- | -- |
| Dataset Name | "2014-2015 Blue Book - for CEQR Analysis" |
| Agency Abbreviation | NYCDOE |
| Data Format | CSV with Coordinates |
| Update Frequency | Annually |
| Update Means | Request file from agency |
| Date Updated | 7/20/16 |
| Date Received | 7/20/16 |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "Routes" |
| Agency Abbreviation | NYCDOE |
| Data Format | CSV with Coordinates |
| Update Frequency | Monthly |
| Update Means | Pull from NYC Open Data |
| Date Updated | 8/1/16 |
| Date Received | 8/1/16 |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "Universal Pre-K (UPK) School Locations" |
| Agency Abbreviation | NYCDOE |
| Data Format | CSV with Coordinates |
| Update Frequency | Monthly |
| Update Means | Pull from NYC Open Data |
| Date Updated | 1/15/16 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Health and Mental Hygiene (NYCDOHMH)

| | |
| -- | -- |
| Dataset Name | "DOHMH Childcare Center Inspections" |
| Agency Abbreviation | NYCDOHMH |
| Data Format | CSV with Addresses |
| Update Frequency | Weekly |
| Update Means | Geocode - Pull from NYC Open Data |
| Date Updated | 7/28/16 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Transportation (NYCDOT)

| | |
| -- | -- |
| Dataset Name | "Municipal Parking Facilities" |
| Agency Abbreviation | NYCDOT |
| Data Format | Webmap |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |


| | |
| -- | -- |
| Dataset Name | "Plaza Program" |
| Agency Abbreviation | NYCDOT |
| Data Format | Shapefile |
| Update Frequency | Annually |
| Update Means | Request file from agency |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |


| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | NYCDOT |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Parks and Recreation (NYCDPR)

| | |
| -- | -- |
| Dataset Name | "Parks Parks Properties" |
| Agency Abbreviation | NYCDPR |
| Data Format | Shapefile |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYC Open Data |
| Date Updated | 7/27/16 |
| Date Received | 7/27/16 |
| Notes | |

### New York City Department of Sanitation (NYCDSNY)

| | |
| -- | -- |
| Dataset Name | "DSNY_select_facs_07262916" |
| Agency Abbreviation | NYCDSNY |
| Data Format | Shapefile |
| Update Frequency | Annually |
| Update Means | Request file from agency |
| Date Updated | 7/26/16 |
| Date Received | 7/26/16 |
| Notes | |

### New York City Housing Authority (NYCHA)

| | |
| -- | -- |
| Dataset Name | "NYCHA PSA (Police Service Areas)" |
| Agency Abbreviation | NYCHA |
| Data Format | Shapefile |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYC Open Data |
| Date Updated | 9/5/14 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Health and Hospitals Corporation (NYCHHC)

| | |
| -- | -- |
| Dataset Name | "Health and Hospitals Corporation (HHC) Facilities" |
| Agency Abbreviation | NYCHHC |
| Data Format | CSV with Coordinates |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYC Open Data |
| Date Updated | 9/5/14 |
| Date Received | 8/1/16 |
| Notes | |

### New York City Department of Health and Human Services (NYCHHS)

| | |
| -- | -- |
| Dataset Name | "HHS Accelerator - Contracts" |
| Agency Abbreviation | NYCHHS |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Manual download |
| Date Updated | 7/26/16 |
| Date Received | 7/26/16 |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "HHS Accelerator - Financials" |
| Agency Abbreviation | NYCHHS |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Manual download |
| Date Updated | 7/26/16 |
| Date Received | 7/26/16 |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "HHS Accelerator - Proposals" |
| Agency Abbreviation | NYCHHS |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Manual download |
| Date Updated | 7/26/16 |
| Date Received | 7/26/16 |
| Notes | |

### New York City Mayor's of Management and Budget (NYCOMB)

| | |
| -- | -- |
| Dataset Name | "District Resource Statement" |
| Agency Abbreviation | NYCOMB |
| Data Format | CSV with Coordinates |
| Update Frequency | Annually |
| Update Means | Request from Agency |
| Date Updated | 6/30/16 |
| Date Received | 6/30/16 |
| Notes | |

### New York State Unified Court System (NYCOURTS)

| | |
| -- | -- |
| Dataset Name | "The Courts" |
| Agency Abbreviation | NYCOURTS |
| Data Format | Addresses |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |

### New York State Department of Environmental Conservation (NYSDEC)

| | |
| -- | -- |
| Dataset Name | ""Lands - Under the Care" |
| Agency Abbreviation | Custody |
| Data Format | and Control of DEC" |
| Update Frequency | NYSDEC |
| Update Means | Shapefile |
| Date Updated | Nightly pull |
| Date Received | Pull from NYState GIS Clearinghouse |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "Solid Waste Management Facilities" |
| Agency Abbreviation | NYSDEC |
| Data Format | CSV with Coordinates |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYState Open Data |
| Date Updated | 3/1/16 |
| Date Received | 8/1/16 |
| Notes | |

### New York State Department of Corrections and Community Supervision (NYSDOCCS)

| | |
| -- | -- |
| Dataset Name | "Facility Listing" |
| Agency Abbreviation | NYSDOCCS |
| Data Format | Addresses |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |

### New York State Department of Health (NYSDOH)

| | |
| -- | -- |
| Dataset Name | "Health Facility General Information" |
| Agency Abbreviation | NYSDOH |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Pull from NYState Open Data |
| Date Updated | 7/28/16 |
| Date Received | 7/28/16 |
| Notes | |

## ADD nursing home bed count data

### New York State Department of Transportation (NYSDOT)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | NYSDOT |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### New York State Education Department (NYSED)

| | |
| -- | -- |
| Dataset Name | "LIstings - Active Institutions with GIS coordinates and OITS Accuracy Code" |
| Agency Abbreviation | NYSED |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Manual download |
| Date Updated | 7/26/16 |
| Date Received | 7/26/16 |
| Notes | |

## ADD enrollment datasets

### New York State Office of Alcoholism and Substance Abuse Services (NYSOASAS)

| | |
| -- | -- |
| Dataset Name | "List of NYC Programs" |
| Agency Abbreviation | NYSOASAS |
| Data Format | CSV with Addresses |
| Update Frequency | Quarterly |
| Update Means | Request file from agency |
| Date Updated | 8/9/16 |
| Date Received | 8/9/16 |
| Notes | |

### New York State Office of Children and Family Services (NYSOCFS)

| | |
| -- | -- |
| Dataset Name | "Facilities" |
| Agency Abbreviation | NYSOCFS |
| Data Format | Addresses |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |

### New York State Office of Mental Health (NYSOMH)

| | |
| -- | -- |
| Dataset Name | "Local Mental Health Programs" |
| Agency Abbreviation | NYSOMH |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Pull from NYState Open Data |
| Date Updated | 7/16/16 |
| Date Received | 7/16/16 |
| Notes | |

### New York State Office of Parks, Recreation and Historic Preservation (NYSOPRHP)

| | |
| -- | -- |
| Dataset Name | "National Register of Historic Places" |
| Agency Abbreviation | NYSOPRHP |
| Data Format | CSV with Coordinates |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYState Open Data |
| Date Updated | 12/18/15 |
| Date Received | 8/1/16 |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "State Park Facility Points" |
| Agency Abbreviation | NYSOPRHP |
| Data Format | CSV with Coordinates |
| Update Frequency | Nightly pull |
| Update Means | Pull from NYState Open Data |
| Date Updated | 12/18/15 |
| Date Received | 8/1/16 |
| Notes | |

### New York State Office for People With Developmental Disabilities (NYSOPWDD)

| | |
| -- | -- |
| Dataset Name | "Directory of Developmental Disabilities Service Provider Agencies" |
| Agency Abbreviation | NYSOPWDD |
| Data Format | CSV with Coordinates |
| Update Frequency | Weekly pull |
| Update Means | Pull from NYState Open Data |
| Date Updated | 12/22/15 |
| Date Received | 8/1/16 |
| Notes | |

### Port Authority of New York and New Jersey (PANYNJ)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | PANYNJ |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Roosevelt Island Operating Corporation (RIOC)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | RIOC |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### Trust for Governors Island (TGI)

| | |
| -- | -- |
| Dataset Name | "Selected Facilities and Program Sites Database" |
| Agency Abbreviation | TGI |
| Data Format | Shapefile |
| Update Frequency | NA |
| Update Means | NA |
| Date Updated | 3/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### United States Courts (USCOURTS)

| | |
| -- | -- |
| Dataset Name | "Court Locator Results" |
| Agency Abbreviation | USCOURTS |
| Data Format | Addresses |
| Update Frequency | Annually |
| Update Means | Manual copy and paste |
| Date Updated | 7/1/16 |
| Date Received | 7/1/16 |
| Notes | |

### United States Department of Transportation (USDOT)

| | |
| -- | -- |
| Dataset Name | "Airports" |
| Agency Abbreviation | USDOT |
| Data Format | Shapefile |
| Update Frequency | Annually |
| Update Means | Pull from US DOT |
| Date Updated | 8/1/15 |
| Date Received | 8/1/16 |
| Notes | |

| | |
| -- | -- |
| Dataset Name | "U.S. Army Corps of Engineers Ports" |
| Agency Abbreviation | USDOT |
| Data Format | Shapefile |
| Update Frequency | Annually |
| Update Means | Pull from US DOT |
| Date Updated | 8/1/15 |
| Date Received | 8/1/16 |
| Notes | |

### United States National Parks Service (USNPS)

| | |
| -- | -- |
| Dataset Name | "Administrative Boundaries of National Park System Units" |
| Agency Abbreviation | USNPS |
| Data Format | Shapefile |
| Update Frequency | Nightly pull |
| Update Means | Pull from USNPS |
| Date Updated | 6/30/16 |
| Date Received | 8/1/16 |
| Notes | |



## Database structure

Currently the database consists of two tables. One table contains all the geocoded records with spatial data, and one with the records which could not be geocoded.

In the future, some supplemental information which is specific to certain facility types will also be included in the database package as relational tables. For exmaple, a table of park attributes or a table with a more granular breakdown of school enrollment by grade could be joined onto the main table using a unique ID.


