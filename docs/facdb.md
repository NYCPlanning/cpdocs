# City Planning Facilities Database

### Overview

The City Planning Facilities Database (FacDB) aggregates information about facilities and program sites that are owned, operated, funded, licensed or certified by a City, State, or Federal agency in the City of New York. These facilities generally impact the quality of the city’s neighborhoods, and they range across seven domains:

* Health and Human Services
* Education, Child Welfare, and Youth
* Parks, Gardens, and Historical Sites
* Libraries and Cultural Programs
* Public Safety, Emergency Services, and Administration of Justice
* Core Infrastructure and Transportation
* Administration of Government

This database and its [interactive map](http://capitalplanning.nyc/facilities) build upon City Planning’s decades-old work on the Selected Facilities and Program Sites Database, which this new product replaces. It captures the location, type, and capacity of public and private facilities in order to inform holistic neighborhood planning, strategic site selection and service delivery planning, opportunities for interagency and public-private partnerships, community outreach activities, and many other functions across City agencies.
One goal of this database is to provide a consolidated, authoritative dataset that can serve as a one-stop-shop to planners. More broadly, the intent is to provide the foundation for a more robust data-integration initiative, ensuring interoperability between disparate agencies’ datasets.

City Planning has grouped these facilities according to the seven domains bulleted above. Within each domain, each record is further categorized into a subsequent set of facility groups, subgroups, and types that are intended to make the data easy to navigate and more useful for specific planning purposes. Facility types and names are pulled directly from source datasets, wherever possible.

Currently, FacDB aggregates and synthesizes data sourced from 43 agencies, recording almost 40,000 facilities throughout NYC. More facilities will be added as the data become available to the Department of City Planning. Special thanks goes to all the agencies who make their data available for this effort, particularly those who publish their data on a routine basis. A full listing of the facility categories is provided in the [Contents and Classification Heirarchy](http://docs.capitalplanning.nyc/facdb/#contents-and-classification-heirarchy) section.

We are constantly looking for ways to improve and add additional value to the database. Please reach out to the NYC DCP Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions.

| General information |
| :------------: | ------------- |
| Dataset Name | "Facilities Database "|
| Description | The Facilities Database (FacDB) captures the locations and descriptions of public and private facilities ranging from the provision of social services, recreation, education, to solid waste management|
| Data format | [Webmap](http://capitalplanning.nyc/facilities), [Shapefile](https://carto.capitalplanning.nyc/user/cpadmin/api/v2/sql?q=SELECT%20*%20FROM%20cpadmin.facilities&format=shp&filename=facilities_all_2017-02-09), [CSV](https://carto.capitalplanning.nyc/user/cpadmin/api/v2/sql?q=SELECT%20*%20FROM%20cpadmin.facilities&format=csv&filename=facilities_all_2017-02-09) |
| Projection | WGS84 |
| Date last updated | 02/04/16 |

### Contents and Classification Heirarchy

In order of increasing granularity, each record that is included in the database is classified by DCP into a **Domain > Facility Group > Facility Subgroup > Facility Type**. There are around 450 facility types. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are also cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description. The tables below describe each of the Subgroups in each of the seven Domains; however, the Facility Types within them are not listed.

**Administration of Government Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Offices, Training, and Testing | Offices | Offices used by City agencies |
| Offices, Training, and Testing | Training and Testing | Training and testing sites used by City agencies |
| Other Property | Miscellaneous Use | City property without a categorized use |
| Other Property | Properties Leased or Licensed to Non-public Entities | Properties Leased or Licensed to Non-public Entities |
| Other Property | Undeveloped or No Use | City property and structures without a designated use |
| Parking, Maintenance, and Storage | Custodial | City agency custodial sites |
| Parking, Maintenance, and Storage | Maintenance and Garages | City agency garages and vehicle maintenance sites |
| Parking, Maintenance, and Storage | Parking | City agency parking lots |
| Parking, Maintenance, and Storage | Storage | City agency storage sites |

**Core Infrastructure and Transportation Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Material Supplies and Markets | Material Supplies | Asphalt plants and other materials processing |
| Material Supplies and Markets | Wholesale Markets | Wholesale food and commercial markets |
| Solid Waste | Solid Waste Processing | Material recovery, composting, landfill gas recovery, and scrap metal processing facilities |
| Solid Waste | Solid Waste Transfer and Carting | Waste carter sites and transfer stations |
| Telecommunications | Telecommunications | Antennas and other telecommunications sites |
| Transportation | Airports and Heliports | Publicly and privately operated airports, heliports, and seaplane bases |
| Transportation | Bus Depots and Terminals | School bus depots, MTA bus depots, and Port Authority bus terminals |
| Transportation | Public Parking Lots and Garages | Public parking lots and garages |
| Transportation | Commercial Parking Lots and Garages | Commercial parking lots and garages |
| Transportation | Other Transportation | Other transportation sites |
| Transportation | Ports and Ferry Landings | Ferry landings, cruise terminals, and ports |
| Transportation | Rail Yards and Maintenance | Rail yards and maintenance facilities |
| Water and Wastewater | Wastewater and Pollution Control | Wastewater treatment plants and other wastewater conveyance and pollution control sites |
| Water and Wastewater | Water Supply | Reservoirs and other water supply related sites |

**Education, Child Welfare, and Youth Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Camps | Camps | Preschool age and all age camps |
| Child Welfare | Child Nutrition | Summer and year-round child feeding sites |
| Childcare | Childcare | Group and school-based child care centers for infants, toddlers, and preschoolers |
| Childrens Services | Childrens Services | Foster care services, preventative care, and juvenile non-secure placement |
| Schools | Non-public Schools | Private elementary, middle, and high schools |
| Schools | Other Schools Serving Students with Disabilities | Specialized schools and educational services for students with disabilities |
| Schools | Preschools | Early Learn NYC and Universal Pre-K sites |
| Schools | Public Schools | Public elementary, middle, and high schools |
| Youth Services | Youth Services | COMPASS Programs, youth literacy, and youth employment programs |
| Higher Education | Colleges or Universities | Public and privately operated 2 and 4 year colleges and universities |
| Vocational and Proprietary Schools | Proprietary Schools | Trade schools and ESL programs |

**Health and Human Services Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Health Care | Chemical Dependency | Monitored support, inpatient, outpatient, and crisis services |
| Health Care | Hospitals and Clinics | Urgent care hospitals, diagnostic and treatment centers, and school-based health facilities |
| Health Care | Mental Health | Inpatient, outpatient, and emergency mental health services |
| Health Care | Residential Health Care | Nursing homes, hospice care, and supportive housing |
| Health Care | Other Health Care | Rehab, respite servies, vaccination services, AIDS counseling, and home health centers |
| Human Services | Community Centers | Community centers that provide multiple social services at one site |
| Human Services | Legal and Intervention Services | Early intervention, criminal defense, and mediation services |
| Human Services | Non-residential Housing and Homeless Services | Non-residential homelessness prevention services |
| Human Services | Programs for People with Disabilities | Specialized child care, caregiver support, and recreational services |
| Human Services | Senior Services | Neighborhood senior centers, meal delivery programs, and other services for seniors |
| Human Services | Shelters and Transitional Housing | Homeless shelters and transitional houseing |
| Human Services | Soup Kitchens and Food Pantries | Soup kitchens and food pantries |
| Human Services | Workforce Development | Workforce 1 Centers and other vocational services for adults |

**Parks, Gardens, and Historical Sites Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Cemeteries | Cemeteries | Cemeteries operated by NYC Parks |
| Historical Sites | Historical Sites | Historic house parks, State historic places, national monuments, and national memorials |
| Parks and Plazas | Cemeteries | Cemeteries operated by NYC Parks |
| Parks and Plazas | Gardens | Community gardens |
| Parks and Plazas | Parks | Flagship parks, community parks, state parks, and city-state parks |
| Parks and Plazas | Preserves and Conservation Areas | Nature areas, preserves, wetlands, and state forests |
| Parks and Plazas | Recreation and Waterfront Sites | Playgrounds, waterfront facilities, and recreation fields and courts |
| Parks and Plazas | Streetscapes, Plazas, and Malls | Pedestrian plazas, malls, triangle plazas, and parkways |

**Libraries and Cultural Programs Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Libraries | Academic Libraries | Libraries operated by academic institutions |
| Libraries | Public Libraries | All public libaries |
| Cultural Institutions | Historical Societies | Historical societies |
| Cultural Institutions | Museums | Publicly and privately operated museums |
| Cultural Institutions | Other Cultural Institutions | Zoos, botanical gardens, performing arts centers, and multi-disciplinary art centers |

**Public Safety, Emergency Services, and Administration of Justice Domain**

| Facility Group | Facility Subgroup | Subgroup Description |
| :------ | :-- | :-- |
| Emergency Services | Fire Services | Firehouses |
| Emergency Services | Other Emergency Services | Ambulance and Emergency Medical Stations |
| Justice and Corrections | Courthouses and Judicial | Courthouses, clerk offices, and court librarians |
| Justice and Corrections | Detention and Correctional | Correctional and dentention centers |
| Public Safety | Other Public Safety | Other public safety related support centers |
| Public Safety | Police Services | NYPD and NYCHA police stations |



## Limitations and Disclaimers

FacDB is only as good as the source data it aggregates. Currently, FacDB is the most comprehensive, spatial data resource available of facilities run by public and non-public entities in NYC, but it does not claim to capture every facility within the specified domains. Many records could not be geocoded. To learn more about how the data is processed, please review the [Methodology](http://docs.capitalplanning.nyc/facdb/#methodology).

**Duplicates.** Please be aware that this beta version of the database includes cases of duplicate records for the same facility. This is because several of the source datasets have content that overlaps with other datasets. We are working to systematically identify these remaining duplicate records and retain atrributes from the most up-to-date and detailed record.

**Administrative Addresses.** There are also known to be cases when the address provided in the source data is for a headquarters office rather the facility site location. Unfortunately these could not be systematically verified. We hope to resolve as many of these limitations as possible over time, and seek feedback from the user community on potential approaches to improving the data. For more detailed information on a specific facility please reach out to the respective oversight agency.

**Analysis Limitations.** As a result of these data limitations and inconsistencies, users should be careful in their use of this database not to develop analyses that may be suspect. For example, a comparison of the density or accessibility of facilities across neighborhoods should recognize that some of the facilities included are organizational headquarters rather than service sites, and that this database is not authoritatively comprehensive.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov).



## Methodology

### Data Processing

Since the facility records are aggregated from many datasets designed for different purposes, the data has to undergo several stages of transformation to reach its final state. The stages are described below and all the scripts used are available on the [NYC Planning GitHub page](https://github.com/NYCPlanning/facilities-db).

**Assembly.**
First, the desired columns in the source data get mapped to the columns in FacDB schema. Many values also need to be recoded and the facility records then need to be classified. The facilities are classified using categories or descriptions provided by the agency. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are also cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description.

**Geoprocessing.**
Many of the source datasets only provide addresses without no coordinates. Records without coordinates are geocoded with the [GeoClient API](https://developer.cityofnewyork.us/api/geoclient-api) using the Address and either the Borough or ZIP Code to get the the BIN, BBL, and other standardized location details. If the record can be assigned a BIN value, the BIN's centroid is used as the point geometry. Records that are provided in the source data with only coordinates and no addresses are processed by doing a spatial join with MapPLUTO to get the BBL and other location related details like Address, Borough, ZIP Code, and BIN when there is a 1-1 BIN-BBL relationship. There are also many cases where an agency provides coordinates but the coordinates they provided fall in the road bed, rather than inside a BBL boundary, due to the geocoding technique used by the source. In these cases, the geometry was replaced with the BBL centroid. Each record in the database is flagged with a code for the geoprocessing technique that was used to complete all of its information.

**Duplicate Record Removal.** Several of the source datasets have content which overlaps with other datasets. Duplicate records were identified by querying for all the records which fall on the same BIN or BBL as a record with the same Facility Subgroup or Type, same Facility Name, or same Oversight Agency. The values from the duplicate records were merged before dropping the duplicate records from the database.


<!-- The processing steps and assumptions used for each record are indicated in the Processing Flag (processingflag) field in the database. Each of the flags are defined in the table below.

| Data Processing Flag | Definition |
| :-- | :-- |
| address2geom_borough | Geometry, BBL, BIN, and zipcode were generated by NYC GeoClient using address and county or borough provided by agency. |
| address2geom_zipcode | Geometry, BBL, BIN, and borough were generated by NYC GeoClient using address and zip code provided by agency. |
| bbljoin | Geometry and address were provided by agency but without a BBL. BBL was obtained by doing a spatial join with MapPLUTO |
| bbljoin2address | Geometry was provided by agency but without an address or BBL. BBL and address were obtained by doing a spatial join with MapPLUTO |
| bbljoin_closest | Geometry was provided by agency without a BBL. No spatial overlap was found with a BBL in MapPLUTO, even though the facility is of a type which should be located on a BBL lot. The closest BBL was assigned to the record. |
| bbljoin2address_closest | Geometry was provided by agency without an address or BBL. No spatial overlap was found with a BBL in MapPLUTO, even though the facility is of a type which should be located on a BBL lot. The closest BBL was assigned to the record. |

 -->

## Data Dictionary

The following table lists and defines each of the fields presented in the Facilities Database as they are organized in the database from left to right.

| Field Alias | Field Name | Description |
| :------------------- | :------------------- | :------------------------------------------------------ |
| Unique Identifier | uid | Universal Unique Identifier.  When a row is added to the table the uid is automatically generated, enabling database replication. |
| Hash | id | An encrypted version of the row from the source data table. |
| Geom | geom | How the feature is spatially represented. |
| Old ID | idold | Non-unique identifier generated and maintained by the former database admin that relates to old version of SFPSD. |
| Agency ID | idagency | Non-unique identifier generated and maintained by the data admin of the parent agency that relates to the record in the source dataset. |
| Facility Name | facilityname | The name of the facility in proper case. |
| Address Number | addressnumber | The address number of where the facility is located. Generated by GeoSupport when not provided in the source data. |
| Street Name | streetname | The name of the street where the facility is located. Generated by GeoSupport. |
| Address | address | The concatenated value of AddressNumber and StreetName of where the facility is located. |
| City | city | The USPS prefeered name of the addressed city where the facility is located. Generated by GeoSupport and spatial joins. |
| Borough | borough | The full name the borough the facility is within. |
| Borough Code | boroughcode | The number value representing the borough the facility is within. |
| ZIP Code | zipcode | The ZIP Code the facility is within. |
| BBL | bbl | The BBL(s) the facility is located on. |
| BIN | bin | The BIN(s) the facility is located on. |
| X Coordinate | xcoord | The X coordinate of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Y Coordinate | ycoord | The Y coordinate of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Latitude | latitude | The latitude of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Longitude | longitude | The longitude of the location either calculated using the coordinates in the source data or provided by GeoSupport. |
| Domain | domain | The value representing the facility domain, the broadest category. |
| Facility Group | facilitygroup | The value representing the group type, the second broadest category. |
| Facility Sub-Group | facilitysubgroup | The value representing the subgroup type. |
| Facility Type | facilitytype | The value representing the facility type, the most granular category of facilities. |
| Capacity | capacity | How many of capacity type/unit the facility is intended to hold. |
| Capacity Type | capacitytype | The value representing the unit type of capacity, such as beds, visitors, seats, etc. |
| Utilization | utilization | How many of capacity type/unit are being utilized at the facility. |
| Utilization Rate | utilizationrate | The ratio of the of utilization over the total facility capacity. |
| Area | area | The total area of the site measured in the Area Type unit. |
| Area Type | areatype | The unit of measurement for Area. |
| Operator Type | operatortype | Indicates whether the operating entity is public or non-public. |
| Operator Name | operatorname | The name of the operating entity. |
| Operator Abbreviation | operatorabbrev | Abbreviation for the operating entity. |
| Oversight Agency | oversightagency | The name of the agency overseeing the facility. |
| Oversight Abbreviation | oversightabbrev | Abbreviation for the oversight agency. |
| Oversight Level | oversightagency | The level of government of the oversight agency: City, State, City-State, Federal, or Non-public Oversight. |
| Date Source Data Updated | datesourceupdated | The date the source data was updated within the parent database. |
| Agency Source | agencysource | The Agency whose data was used as the source for the record. |
| Source Dataset Name | sourcedatasetname | The name of the dataset the record came from. |
| Link to Data | linkdata | Link to view and/or description of data. |
| Processing Flag | processingflag | A text flag which indicates how the record was geoprocessed to fill in all required information, including geocoding and spatial joins. |



## Source Data

The following datasets were used to populate the Facilities Database. The data sources that are published online as open data are automatically downloaded and aggregated to capture any updates provided by the source agency. The aggregated database is thoroughly checked through once per year to identify any problems with the process or major changes in the source data and how it's structured.


### Amtrak (Amtrak)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### Brooklyn Bridge Park Corporation (BBPC)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### Federal Bureau of Prisons (FBOP)

| | |
| -- | -- |
| Dataset Name: | [Our Locations](https://www.bop.gov/locations/map.jsp#) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |


### Food Bank of New York City (FBNYC)

| | |
| -- | -- |
| Dataset Name:  | FBNYC Food Pantry Soup Kitchen List 8-5-16 |
| Last updated: | 8/5/16 |
| Refresh Method: | Request file from agency - Quarterly |


### Hudson River Park Trust (HRPT)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### Metropolitan Transportation Authority (MTA)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### New York City Administration for Childrens Services (NYCACS)

| | |
| -- | -- |
| Dataset Name:  | Contractor Data |
| Last updated: | 1/3/17 |
| Refresh Method: | Request file from agency - Annually |


### New York City Business Integrity Commission (NYCBIC)

| | |
| -- | -- |
| Dataset Name: | [Approved licensees and registrants for trade waste](https://data.cityofnewyork.us/Business/Approved-licensees/7atx-5a3s) |
| Last updated: | 9/5/14 |
| Refresh Method: | Pull from NYC Open Data - Annually |


### New York City Department for the Aging (NYCDFTA)

| | |
| -- | -- |
| Dataset Name: | [DFTA Contracts](https://data.cityofnewyork.us/Social-Services/DFTA-Contracts/6j6t-3ixh) |
| Last updated: | 1/20/17 |
| Refresh Method: | Pull from NYC Open Data - Weekly |


### New York City Department of Citywide Administrative Services (NYCDCAS)

| | |
| -- | -- |
| Dataset Name:  | [City Owned and Leased Properties](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-colp.page) |
| Last updated: | 10/20/16 |
| Refresh Method: | Pull from NYC Open Data - Biennially |


### New York City Department of Consumer Affairs (NYCDCA)

| | |
| -- | -- |
| Dataset Name: | [Legally Operating Businesses](https://data.cityofnewyork.us/Business/Legally-Operating-Businesses/w7w3-xahh) |
| Last updated: | 1/20/17 |
| Refresh Method: | Pull from NYC Open Data - Weekly |


### New York City Department of Correction (NYCDOC)

| | |
| -- | -- |
| Dataset Name: | [Correction Facilities Locations](http://www1.nyc.gov/site/doc/about/facilities-locations.page) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |


### New York City Department of Cultural Affairs (NYCDCLA)

| | |
| -- | -- |
| Dataset Name: | [DCLA Cultural Organizations](https://data.cityofnewyork.us/Recreation/DCLA-Cultural-Organizations/u35m-9t32) |
| Last updated: | 3/22/16 |
| Refresh Method: | Pull from NYC Open Data - Annually |


### New York City Department of Education (NYCDOE)

| | |
| -- | -- |
| Dataset Name: | [Universal Pre-K (UPK) School Locations](https://data.cityofnewyork.us/Education/Universal-Pre-K-UPK-School-Locations/kiyv-ks3f) |
| Last updated: | 1/15/16 |
| Refresh Method: | Pull from NYC Open Data - Monthly |

| | |
| -- | -- |
| Dataset Name:  | [2014-2015 Blue Book](https://dnnhh5cc1.blob.core.windows.net/portals/0/Capital_Plan/Utilization_Reports/Blue%20Book%202015-2016.pdf?sr=b&si=DNNFileManagerPolicy&sig=AExrFIUz%2BQDwk%2FlptyHq0ZkW2Ur9J69SJuy4MgQ%2BAp4%3D) |
| Last updated: | 7/20/16 |
| Refresh Method: | Request file from agency - Annually |

| | |
| -- | -- |
| Dataset Name: | [Routes](https://data.cityofnewyork.us/Transportation/Routes/8yac-vygm) |
| Last updated: | 1/1/17 |
| Refresh Method: | Pull from NYC Open Data - Monthly |


### New York City Department of Environmental Protection (NYCDEP)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### New York City Department of Health and Mental Hygiene (NYCDOHMH)

| | |
| -- | -- |
| Dataset Name: | [DOHMH Childcare Center Inspections](https://data.cityofnewyork.us/Health/DOHMH-Childcare-Center-Inspections/dsg6-ifza) |
| Last updated: | 1/23/17 |
| Refresh Method: | Pull from NYC Open Data - Daily |


### New York City Department of Homeless Services (NYCDHS)

| | |
| -- | -- |
| Dataset Name:  | DHS Shelter Listing |
| Last updated: | 11/21/16 |
| Refresh Method: | Request file from agency - Monthly |


### New York City Department of Parks and Recreation (NYCDPR)

| | |
| -- | -- |
| Dataset Name: | [Parks Properties](https://data.cityofnewyork.us/City-Government/Parks-Properties/rjaj-zgq7) |
| Last updated: | 8/27/16 |
| Refresh Method: | Pull from NYC Open Data - Monthly |


### New York City Department of Sanitation (NYCDSNY)

| | |
| -- | -- |
| Dataset Name:  | DSNY_select_facs_07262916 |
| Last updated: | 7/26/16 |
| Refresh Method: | Request file from agency - Annually |


### New York City Department of Small Business Services (NYCSBS)

| | |
| -- | -- |
| Dataset Name:  | SBS Workforce1 Career Center Locations |
| Last updated: | 11/17/16 |
| Refresh Method: | Request file from agency - Annually |


### New York City Department of Transportation (NYCDOT)

| | |
| -- | -- |
| Dataset Name: | [Municipal Parking Facilities](http://www.nyc.gov/html/dot/html/motorist/parkinglist.shtml) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |

| | |
| -- | -- |
| Dataset Name:  | Plaza Program |
| Last updated: | 7/1/16 |
| Refresh Method: | Request file from agency - Annually |

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### New York City Department of Youth and Community Development (NYCDYCD)

| | |
| -- | -- |
| Dataset Name:  | COMPASS Program Locations |
| Last updated: | 12/19/16 |
| Refresh Method: | Request file from agency - Monthly |

| | |
| -- | -- |
| Dataset Name:  | DYCD Other Program Locations |
| Last updated: | 12/19/16 |
| Refresh Method: | Request file from agency - Monthly |


### New York City HHS Accelerator (NYCHHS)

| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Contracts |
| Last updated: | 7/26/16 |
| Refresh Method: | Request file from agency - Annually |

| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Proposals |
| Last updated: | 7/26/16 |
| Refresh Method: | Request file from agency - Annually |

| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Financials |
| Last updated: | 7/26/16 |
| Refresh Method: | Request file from agency - Annually |


### New York City Housing Authority (NYCHA)

| | |
| -- | -- |
| Dataset Name: | [NYCHA PSA (Police Service Areas)](https://data.cityofnewyork.us/Housing-Development/NYCHA-PSA-Police-Service-Areas-/72wx-vdjr) |
| Last updated: | 9/5/14 |
| Refresh Method: | Pull from NYC Open Data - Annually |


### New York City Mayors Office of Management and Budget (NYCOMB)

| | |
| -- | -- |
| Dataset Name:  | District Resource Statement |
| Last updated: | 6/30/16 |
| Refresh Method: | Request file from agency - Annually |


### New York State Department of Correction and Community Supervision (NYSDOCCS)

| | |
| -- | -- |
| Dataset Name: | [Facility Listing](http://www.doccs.ny.gov/faclist.html) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |


### New York State Department of Evironmental Conservation (NYSDEC)

| | |
| -- | -- |
| Dataset Name: | [Solid Waste Management Facilities](https://data.ny.gov/Energy-Environment/Solid-Waste-Management-Facilities/2fni-raj8) |
| Last updated: | 1/9/17 |
| Refresh Method: | Pull from NYState Open Data - Annually |

| | |
| -- | -- |
| Dataset Name: | [Lands - Under the Care, Custody, and Control of DEC](http://gis.ny.gov/gisdata/inventories/details.cfm?DSID=1114) |
| Last updated: | 3/1/16 |
| Refresh Method: | Pull from NYState GIS Clearinghouse - Annually |


### New York State Department of Health (NYSDOH)

| | |
| -- | -- |
| Dataset Name: | [Health Facility General Information](https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r) |
| Last updated: | 1/20/17 |
| Refresh Method: | Pull from NYState Open Data - Weekly |


### New York State Department of Transportation (NYSDOT)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### New York State Education Department (NYSED)

| | |
| -- | -- |
| Dataset Name: | [Listings - Active Institutions with GIS coordinates and OITS Accuracy Code](https://portal.nysed.gov/discoverer/app/grid;jsessionid=eikT4MZCXS4gnCu4gkga8RxAT-LFQX1XhLGyOQErv16YJWGj_jo8!-214928944?bi_origin=dvtb&bi_cPath=dvtb&numberLocale=en_US&source=dvtb&gotoNthPage=1&bi_tool=rt&event=bi_showTool&bi_rownavdv=s25&stateStr=eNrtVlFzmzgQ%2FjPY0xtPMiBjJ3nwg4vdlGmKe8ZpmnthZEkYJRgIksHOr79Fog71JO1Q957OL9rVov202tWKz2DbLDa65VKOUDdJKRuhq67IRt08TeXI7LKCJXIEi3BCu0JiyUbvhoO%2FDJwZHTSkYac%2FASm0SIiWNNayFmyTV5pBEqNbEDkSBe2S5HFEwgBbJjLKRxFJgLNXtAioAAWcnmIRbDvIskxw9RnNWdi5mCJzFuNMKQu8jJnSPqS5knOWpbkU5066SeROmSZMEADDaQkoIY4Fa0JftIYeU1gthLLd8IShJtxl%240g5xImG4Ro8t%24u4CTaowCLGpHKwzmfuwlfqtavlmBAlHSha03HYOoov0U5wgmMNe3BCqyqvqAos880PG%2FUPIrzmtVearLjcUL1ZB11%2466CrpqP9liOWP%2FjdH%2FhZrU%2Fm0%2FjVHKHfRqov1B7pqj1S1UQNiPa3xk1ElSjJ00TZ%2Fc1Se%24wy9lqQV8d0UJ06KUQgqgMff7uU8jmlPOSM6nhVRpw4giFJ8zUsRs73bsX50yu9ax6dNZc269ga7oat6jN5eN2M7DfuVp2Gg1vab5%2FqNNvEOH8tKrv9U0ckL1ijPvs7YB5%2Fn96o9VMW%24CxmRL8MdaFq5%2F5kANM%24DsPwUine9E59v5%2FNP0mw6s%2Fv5zPv28v0k%24td%249V0qKZ%2F306nnpprjLnrfPw88yaykarB0Vdr34gHFUX%2FYffsNxn%24ufAP3hHUvvD%2F8IzQQQPj4s%24%2FdodJRkdv8SVKk%2FovBEO%2FCd4%2FGvw2r%2F7zlIqC5QBmad4Tadpj0wKG7eOZtY57sECA13NpnZtl73G3pUVviZ9LmBABVnRZ7rYZ6RWglw%2477QMtgE3YZVFhAXEyNbRc%2FgRSfd9tl1zEshIkSis8Bbc3rtR4ZnMqo548s55L2zSrJUseMb6K5IHxOseUA2%2Fskeh7aBrkQW%24n4hJrEFWIGc7xWrwk4EQBTxTwRAFPFPBEAU8U8EQBTxTwf0EBY6LpTwlPkl33gv1CC1eKFyrTT%24ncr9ncg1piZDmnxo3rL6rmCIKxs3C%2FTgPXA8PiduHOPD%244cxcfA6AagTObzSeuN15M%2FWDsTYKKh4CHczsfO%2FfwdTLtoA%24WQeQuMwrOSpb%2FCyl4PR4%3D) |
| Last updated: | 1/23/17 |
| Refresh Method: | Manual download - Weekly |


### New York State Office for People With Developmental Disabilities (NYSOPWDD)

| | |
| -- | -- |
| Dataset Name: | [Directory of Developmental Disabilities Service Provider Agencies](https://data.ny.gov/Human-Services/Directory-of-Developmental-Disabilities-Service-Pr/ieqx-cqyk) |
| Last updated: | 12/22/15 |
| Refresh Method: | Pull from NYState Open Data - Annually |


### New York State Office of Alcoholism and Substance Abuse Services (NYSOASAS)

| | |
| -- | -- |
| Dataset Name:  | List of NYC Programs |
| Last updated: | 1/3/17 |
| Refresh Method: | Receive scheduled email transfer from agency - Monthly |


### New York State Office of Children and Family Services (NYSOCFS)

| | |
| -- | -- |
| Dataset Name: | [Facilities](http://ocfs.ny.gov/main/rehab/regionalListing1.asp) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |


### New York State Office of Mental Health (NYSOMH)

| | |
| -- | -- |
| Dataset Name: | [Local Mental Health Programs](https://data.ny.gov/Human-Services/Local-Mental-Health-Programs/6nvr-tbv8) |
| Last updated: | 10/24/16 |
| Refresh Method: | Pull from NYState Open Data - Annually |


### New York State Office of Parks, Recreation and Historic Preservation (NYSOPRHP)

| | |
| -- | -- |
| Dataset Name: | [National Register of Historic Places](https://data.ny.gov/Recreation/National-Register-of-Historic-Places/iisn-hnyv) |
| Last updated: | 12/18/15 |
| Refresh Method: | Pull from NYState Open Data - Annually |

| | |
| -- | -- |
| Dataset Name: | [State Park Facility Points](https://data.ny.gov/Recreation/State-Park-Facility-Points/9uuk-x7vh) |
| Last updated: | 2/4/16 |
| Refresh Method: | Pull from NYState Open Data - Annually |


### New York State Unified Court System (NYCOURTS)

| | |
| -- | -- |
| Dataset Name: | [The Courts](http://www.nycourts.gov/courts/index.shtml) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |


### Port Authority of New York and New Jersey (PANYNJ)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### Roosevelt Island Operating Corporation (RIOC)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### Trust for Governors Island (TGI)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last updated: | 3/1/15 |
| Refresh Method: | Confirm with agency - Annually |


### United States Courts (USCOURTS)

| | |
| -- | -- |
| Dataset Name: | [Court Locator Results](http://www.uscourts.gov/court-locator/city/New%20York/state/NY) |
| Last updated: | 7/1/16 |
| Refresh Method: | Manual copy and paste - Annually |


### United States Department of Transportation (USDOT)

| | |
| -- | -- |
| Dataset Name: | [U.S. Army Corps of Engineers Ports](http://www.rita.dot.gov/bts/sites/rita.dot.gov.bts/files/publications/national_transportation_atlas_database/2015/point) |
| Last updated: | 8/1/15 |
| Refresh Method: | Pull from US DOT - Annually |


### United States Department of Transportation (USDOT)

| | |
| -- | -- |
| Dataset Name: | [Airports](http://www.rita.dot.gov/bts/sites/rita.dot.gov.bts/files/publications/national_transportation_atlas_database/2015/point) |
| Last updated: | 8/1/15 |
| Refresh Method: | Pull from US DOT - Annually |


### United States National Park Service (USNPS)

| | |
| -- | -- |
| Dataset Name: | [Administrative Boundaries of National Park System Units](https://irma.nps.gov/DataStore/Reference/Profile/2225713) |
| Last updated: | 9/30/16 |
| Refresh Method: | Pull from USNPS - Annually |


## Database structure

Currently the database consists of two tables. One table contains all the geocoded records with spatial data, and one with the records which could not be geocoded.

In the future, some supplemental information which is specific to certain facility types will also be included in the database package as relational tables. For exmaple, a table of park attributes or a table with a more granular breakdown of school enrollment by grade could be joined onto the main table using a unique ID.


