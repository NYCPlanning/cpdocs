# City Planning Facilities Database

## I. Overview

The City Planning Facilities Database aggregates more than 35,000 records from 43 different public data sources provided by City, State, and Federal agencies. While each source agency classifies its facilities according to their own naming systems, we have grouped all facilities and program sites into the following seven categories to help planners navigate the data more easily:

* Health and Human Services
* Education, Child Welfare, and Youth
* Parks, Gardens, and Historical Sites
* Libraries and Cultural Programs
* Public Safety, Emergency Services, and Administration of Justice
* Core Infrastructure and Transportation
* Administration of Government

Within each of these domains, each record is further categorized into a set of facility groups, subgroups, and types that are intended to make the data easy to navigate and more useful for specific planning purposes. Facility types and names appear as they do in source datasets, wherever possible. A full listing of the facility categories is provided in the [Contents and Classification Hierarchy](http://docs.capitalplanning.nyc/facdb/#ii-contents-and-classification-hierarchy) section.

This database and its [interactive map](http://capitalplanning.nyc.gov/facilities) build upon City Planning’s decades-old work on the Selected Facilities and Program Sites Database, which this new product replaces. Improvements include more facility types, improved data quality, and a restructured database for easier use. We have also automated our means of refreshing the data from the majority of sources – we anticipate that the data will be refreshed on at least a quarterly basis (although source datasets may be refreshed less frequently). Please read more about the [limitations](http://docs.capitalplanning.nyc/facdb/#iii-limitations-and-disclaimers) of this data product below.

More facilities will be added as the data become available to the Department of City Planning. Special thanks goes to all the agencies who make their data available for this effort, particularly those who publish their data on a routine basis.

We are constantly looking for ways to improve and add additional value to the database. Please reach out to the NYC DCP Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov with any suggestions).

| General information |
| :------------: | ------------- |
| Dataset Name | "Facilities Database "|
| Description | The Facilities Database (FacDB) captures the locations and descriptions of public and private facilities ranging from the provision of social services, recreation, education, to solid waste management|
| Data format | [Webmap](http://capitalplanning.nyc.gov/facilities), [Shapefile](https://carto.capitalplanning.nyc/user/cpadmin/api/v2/sql?q=SELECT%20*%20FROM%20cpadmin.facilities&format=shp&filename=facilities_all_2017-02-24), [CSV](https://carto.capitalplanning.nyc/user/cpadmin/api/v2/sql?q=SELECT%20*%20FROM%20cpadmin.facilities&format=csv&filename=facilities_all_2017-02-24) |
| Projection | WGS84 |
| Date last updated | 02/24/16 |

## II. Contents and Classification Hierarchy

In order of increasing granularity, each record that is included in the database is classified by DCP into a **Domain > Facility Group > Facility Subgroup > Facility Type**. There are around 450 facility types. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are also cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description. The tables below describe each of the Subgroups in each of the seven Domains; however, the Facility Types within them are not listed.

####Education, Child Welfare, and Youth Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Schools (K-12) | ----------- | Preschools, K-12 schools, and higher education overseen by NYC Dept. of Education and NYS Education Department |
| | Public Schools | Public and charter elementary, middle, and high schools |
| | Non-public Schools | Private elementary, middle, and high schools |
| | Other Schools Serving Students with Disabilities | Specialized schools and educational services for students with disabilities |
| Child Care and Pre-Kindergarten | ----------- | Childcare centers overseen by NYC Administration for Childrens Services and NYC Dept. of Mental Health and Hygiene |
| | DOE Universal Pre-Kindergarten | NYC DOE designated Universal Pre-K center |
| | Dual Child Care and Universal Pre-K | Center that offers both a NYC DOE desgiated Universal Pre-K services and other child care services |
| | Child Care | Group and school-based child care centers for infants, toddlers, and preschoolers |
| | Preschools for Students with Disabilities | Center specialized on preschool students with disabilities |
| Children's Services | ----------- | Services overseen by NYC Health and Human Services and NYC Administration for Children's Services |
| | Foster Care Services and Residential Care | Foster care services and juvenile non-secure placement |
| | Preventative Care, Evaluation Services, and Respite | Preventative care and intervention services |
| Child Welfare | ----------- | Child feeding centers tracked by New York State Education Department |
| | Child Nutrition | Summer and year-round child feeding sites |
| | School-Based Food Services | Feed services located at schools |
| Youth Services | ----------- | Services overseen by NYC Dept. of Youth and Community Development |
| | Comprehensive After School System (COMPASS) Sites | Comprehensive After School System (COMPASS) Sites |
| | Youth Centers, Literacy Programs, Job Training, and Immigrant Services | Youth Centers, Literacy Programs, Job Training, and Immigrant Services |
| Camps | ----------- | Camps overseen by NYC Dept. of Mental Health and Hygiene |
| | Camps | Preschool age and all age camps |
| Higher Education | ----------- | Public and privately operated 2 and 4 year colleges and universities |
| | Colleges or Universities | Public and privately operated 2 and 4 year colleges and universities |
| Vocational and Proprietary Schools | ----------- | ESL schools and trade colleges |
| | Proprietary Schools | ESL schools and trade colleges |


####Parks, Gardens, and Historical Sites Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Parks and Plazas | ----------- | Properties operated by NYC Parks, NYC Dept. of Transportation, NYS Office of Parks, Recreation and Historic Preservation, NYS Dept. of Conservation, and City-State corporations and trusts |
| | Parks | Flagship parks, community parks, state parks, and city-state parks |
| | Recreation and Waterfront Sites | Playgrounds, waterfront facilities, and recreation fields and courts |
| | Streetscapes, Plazas, and Malls | Pedestrian plazas, malls, triangle plazas, and parkways |
| | Gardens | Community gardens |
| | Preserves and Conservation Areas | Nature areas, preserves, wetlands, and state forests |
| | Cemeteries | Cemeteries operated by NYC Parks |
| Historical Sites | ----------- | Sites operated by NYC Parks, NYS Office of Parks, Recreation and Historic Preservation, and US National Park Service |
| | Historical Sites | Historic house parks, State historic places, national monuments, and national memorials |


####Libraries and Cultural Programs Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Libraries | ----------- | Libraries operated by New York Public Libraries, Queens Public Libraries, and Brooklyn Public Libraries and academic institutions |
| | Public Libraries | All public libaries |
| | Academic and Special Libraries | Libraries operated by academic institutions or other specialized organizations |
| Cultural Institutions | ----------- | Institutions licensed or funded by the NYC Dept. of Cultural Affairs |
| | Museums | Publicly and privately operated museums |
| | Historical Societies | Historical societies |
| | Other Cultural Institutions | Zoos, botanical gardens, performing arts centers, and multi-disciplinary art centers |


####Public Safety, Emergency Services, and Administration of Justice Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Emergency Services | ----------- | Services provided by Fire Dept. of New York |
| | Fire Services | Firehouses |
| | Other Emergency Services | Ambulance and Emergency Medical Stations |
| Public Safety | ----------- | Services provided by New York Police Dept. and New York Housing Authority Police |
| | Police Services | NYPD and NYCHA police stations |
| | School-Based Safety Program | Public safety program on a school campus |
| | Other Public Safety | Other public safety related support centers |
| Justice and Corrections | ----------- | Courts and correctional facilities operated by NYC. Dept. of Correction, NYS Unified Court System, NYS Dept. of Corrections and Community Supervision, US Courts, and Federal Bureau of Prisons |
| | Courthouses and Judicial | Courthouses, clerk offices, and court librarians |
| | Detention and Correctional | Correctional and dentention centers |


####Health and Human Services Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Health Care | ----------- | Health facilities overseen by NYC Health and Hospitals Corporation, NYC Health and Human Services, NYS Dept. of Health, NYS Office of Mental Health, and NYS Office of Alcoholism and Substance Abuse Services |
| | Hospitals and Clinics | Urgent care hospitals, diagnostic and treatment centers, and school-based health facilities |
| | Mental Health | Inpatient, outpatient, and emergency mental health services |
| | Residential Health Care | Nursing homes, hospice care, and supportive housing |
| | Chemical Dependency | Monitored support, inpatient, outpatient, and crisis services |
| | Health Promotion and Disease Prevention | Programs focused on improving health through education and disease prevention |
| | Other Health Care | Rehab, respite servies, vaccination services, AIDS counseling, and home health centers |
| Human Services | ----------- | Services overseen by NYC Dept. of Homeless Services, NYC Dept. of Human Resources, NYC Mayorality, and others |
| | Senior Services | Neighborhood senior centers, meal delivery programs, and other services for seniors |
| | Community Centers and Community School Programs | Community centers that provide multiple social services at one site |
| | Financial Assistance and Social Services | SNAP, Child Support, and Medicaid Centers operated by NYC Human Resources Administration |
| | Workforce Development | Workforce 1 Centers and other vocational services for adults |
| | Legal and Intervention Services | Early intervention, criminal defense, and mediation services |
| | Programs for People with Disabilities | Specialized child care, caregiver support, and recreational services |
| | Shelters and Transitional Housing | NOTE: These records will be incorporated soon, once the data is finished being assembled for inclusion in the database. |
| | Non-residential Housing and Homeless Services | Non-residential homelessness prevention services |
| | Soup Kitchens and Food Pantries | Soup kitchens and food pantries |


####Core Infrastructure and Transportation Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Solid Waste | ----------- | Sites overseen and operated by NYC Dept. of Sanitation, NYC Business Integrity Commission, and NYS Dept. of Conservation |
| | Solid Waste Processing | Material recovery, composting, landfill gas recovery, and scrap metal processing facilities |
| | Solid Waste Transfer and Carting | Waste carter sites and transfer stations |
| Water and Wastewater | ----------- | Sites overseen and operated by NYC Dept. of Environmental Protection |
| | Wastewater and Pollution Control | Wastewater treatment plants and other sites related to wastewater conveyance and pollution control |
| | Water Supply | Sites related to water supply |
| Transportation | ----------- | Sites operated or overseen by Metropolitan Transportation Authority, Port Authority of NY and NJ, NYC Dept. of Transportation, NYC Dept. of Consumer Affairs, US Dept. of Transportation, and others |
| | Parking Lots and Garages | Publicly and commerially operated parking lots and garages |
| | Bus Depots and Terminals | School bus depots, MTA bus depots, and Port Authority bus terminals |
| | Rail Yards and Maintenance | Rail yards and maintenance facilities |
| | Ports and Ferry Landings | Ferry landings, cruise terminals, and ports |
| | Airports and Heliports | Publicly and privately operated airports, heliports, and seaplane bases |
| | Other Transportation | Uncategorized transportation related sites |
| Telecommunications | ----------- | Sites operated or overseen by Dept. of Information Technology and Telecommunications and other City telecommunications services |
| | Telecommunications | Antennas and other telecommunications sites |
| Material Supplies and Markets | ----------- | Sites operated or overseen by Dept. of Information Technology and Telecommunications and other City telecommunications services |
| | Material Supplies | Asphalt plants and other material processing facilities |
| | Wholesale Markets | Wholesale food and commercial markets |


####Administration of Government Domain####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Offices, Training, and Testing | ----------- | All City owned or leased offices overseen by Dept. of Citywide Administrative Services |
| | Offices | Offices used by City agencies |
| | Training and Testing | Training and testing sites used by City agencies |
| City Agency Parking, Maintenance, and Storage | ----------- | City owned or leased properites used for City vehicle and equipment-related operations by Dept. of Citywide Administrative Services |
| | Custodial | City agency custodial sites |
| | Maintenance and Garages | City agency vehicle maintenance sites |
| | City Agency Parking | City agency parking lots |
| | Storage | City agency storage sites |
| Other Property | ----------- | City owned or leased property without a categorized use overseen by Dept. of Citywide Administrative Services |
| | Miscellaneous Use | Property without a categorized use |
| | Properties Leased or Licensed to Non-public Entities | Properties Leased or Licensed to Non-public Entities |


## III. Limitations and Disclaimers

The City Planning Facilities Database (FacDB) is only as good as the source data it aggregates, and the Department of City Planning cannot verify the accuracy of all records. Please read more about specific data and analysis limitations before using this data.

**Analysis Limitations.** As a result of these data limitations and inconsistencies listed below, users should be careful in their use of this database not to develop analyses that may be suspect. For example, a comparison of the density or accessibility of facilities across neighborhoods should recognize that some of the facilities included are organizational headquarters rather than service sites, and that this database is not authoritatively comprehensive. In addition, we rely on source data from other agencies to populate the database, and some of these sources may fall out-of-date. Users can find the date of each source dataset’s latest update in the [Source Data](http://docs.capitalplanning.nyc/facdb/#vi-source-data) section.

**Missing Records.** Currently, FacDB is the most comprehensive, spatial data resource available of facilities run by public and non-public entities in NYC, but it does not claim to capture every facility within the specified domains. Some facilities are deliberately excluded in the data that source agencies provide in order to protect the safety and privacy of their clients. Many records also could not be geocoded. To learn more about how the data is processed, please review the [Methodology](http://docs.capitalplanning.nyc/facdb/#iv-methodology).

**Duplicates.** Please be aware that this beta version of the database includes cases of duplicate records for the same facility. This is because several of the source datasets have content that overlaps with other datasets. We are working to systematically identify these remaining duplicate records and retain all useful attributes from each record.

**Administrative Addresses.** There are also known to be cases when the address provided in the source data is for a headquarters office rather the facility site location. Unfortunately, these could not be systematically verified. We hope to resolve as many of these limitations as possible over time, and seek feedback from the user community on potential approaches to improving the data. For more detailed information on a specific facility please reach out to the respective oversight agency.

**Public Accessibility of Sites.** DCP is unable to verify the public accessibility of all sites. For example, some playgrounds or playing fields may only be accessible to participants in certain programs.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov).



## IV. Methodology

### Data Processing

Since the facility records are aggregated from many datasets designed for different purposes, the data has to undergo several stages of transformation to reach its final state. The stages are described below and all the scripts used are available on the [NYC Planning GitHub page](https://github.com/NYCPlanning/facilities-db).

**Assembly.**
First, the desired columns in the source data get mapped to the columns in FacDB schema. Many values also need to be recoded and the facility records then need to be classified. The facilities are classified using categories or descriptions provided by the agency. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are also cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description.

**Geoprocessing.**
Many of the source datasets only provide addresses without no coordinates. Records without coordinates are geocoded with the [GeoClient API](https://developer.cityofnewyork.us/api/geoclient-api) using the Address and either the Borough or ZIP Code to get the BIN, BBL, and other standardized location details. If the record can be assigned a BIN value, the BIN's centroid is used as the point geometry. Records that are provided in the source data with only coordinates and no addresses are processed by doing a spatial join with MapPLUTO to get the BBL and other location related details like Address, Borough, ZIP Code, and BIN when there is a 1-1 BIN-BBL relationship. There are also many cases where an agency provides coordinates but the coordinates they provided fall in the road bed, rather than inside a BBL boundary, due to the geocoding technique used by the source. In these cases, the geometry was replaced with the BBL centroid, if a BIN could not be assigned and used for the geometry instead. Each record in the database is flagged with a code for the geoprocessing technique that was used to complete all of its information.

**Duplicate Record Removal.** Several of the source datasets have content which overlaps with other datasets. Duplicate records were identified by querying for all the records which fall on the same BIN or BBL as a record with the same Facility Subgroup or Type, same Facility Name, or same Oversight Agency. The values from the duplicate records were merged before dropping the duplicate records from the database.


<!-- The processing steps and assumptions used for each record are indicated in the Processing Flag (processingflag) field in the database. Each of the flags are defined in the table below.

| Data Processing Flag | Definition |
| :-- | :-- |
| address2geom_borough | Geometry, BBL, BIN, and Zip Code were generated by NYC GeoClient using address and county or borough provided by agency. |
| address2geom_zipcode | Geometry, BBL, BIN, and borough were generated by NYC GeoClient using address and zip code provided by agency. |
| bbljoin | Geometry and address were provided by agency but without a BBL. BBL was obtained by doing a spatial join with MapPLUTO |
| bbljoin2address | Geometry was provided by agency but without an address or BBL. BBL and address were obtained by doing a spatial join with MapPLUTO |
| bbljoin_closest | Geometry was provided by agency without a BBL. No spatial overlap was found with a BBL in MapPLUTO, even though the facility is of a type which should be located on a BBL lot. The closest BBL was assigned to the record. |
| bbljoin2address_closest | Geometry was provided by agency without an address or BBL. No spatial overlap was found with a BBL in MapPLUTO, even though the facility is of a type which should be located on a BBL lot. The closest BBL was assigned to the record. |

 -->

## V. Data Dictionary

The following table lists and defines each of the fields presented in the Facilities Database as they are organized in the database from left to right.

| Field Alias | Field Name | Description |
| :------------------- | :------------------- | :-------------------- |
| Unique Identifier | uid | Universal Unique Identifier.  When a row is added to the table the uid is automatically generated, enabling database replication. |
| Hash | id | An encrypted version of the row from the source data table. |
| Geom | geom | How the feature is spatially represented. |
| Old ID | idold | Non-unique identifier generated and maintained by the former database admin that relates to old version of SFPSD. |
| Agency ID | idagency | Non-unique identifier generated and maintained by the data admin of the parent agency that relates to the record in the source dataset. |
| Facility Name | facilityname | The name of the facility in proper case. |
| Address Number | addressnumber | The address number of where the facility is located, validated by GeoClient. If the address that is available for the site is not complete with an address number (only the street name), this field is left blank. |
| Street Name | streetname | The name of the street where the facility is located, validated by GeoClient. If the address that is available for the site is not complete with an address number (only the street name), this field is left blank. |
| Address | address | The concatenated value of AddressNumber and StreetName of where the facility is located. If there is not a valid, complete address available, any location description that was provided is included in this field. |
| City | city | The USPS preferred name of the addressed city where the facility is located. Generated by GeoClient and spatial joins. This field contains some blanks for facilities that do not overlap with the shoreline Zip Code boundaries. |
| Borough | borough | The full name the borough the facility is within. |
| Borough Code | boroughcode | The number value representing the borough the facility is within. |
| ZIP Code | zipcode | The ZIP Code the facility is within. This field contains some blanks for facilities that do not overlap with the shoreline Zip Code boundaries. |
| Latitude | latitude | The latitude of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| Longitude | longitude | The longitude of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| X Coordinate | xcoord | The X coordinate of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| Y Coordinate | ycoord | The Y coordinate of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| BIN | bin | The [BIN](http://a030-goat.nyc.gov/goat/glossary.aspx#bin) values for the buildings the facility is located in. This field contains blanks, because 1) some lots do not have buildings on them, and 2) some lots have multiple buildings and a single BIN could not be reliably assigned given the information provided in the source data. |
| BBL | bbl | The [BBL](http://a030-goat.nyc.gov/goat/glossary.aspx#bbl) values for the tax lots the facility is located on. This field contains blanks, because some facility categories, like pedestrian plazas are not located on tax lots. |
| Community Board | communityboard | The Community District the facility is within. This field contains blanks because the Community District boundaries do not capture facilities beyond the shoreline. |
| Council District | councildistrict | The City Council District the facility is within |
| Census Tract | censustract | The U.S. Census Tract the facility is within |
| NTA | censustract | The Neighborhood Tabulation Area (NTA) the facility is within. This field contains blanks because the NTA boundaries do not capture facilities beyond the shoreline. |
| Domain | domain | The value representing the facility domain, the broadest category. |
| Facility Group | facilitygroup | The value representing the group type, the second broadest category. |
| Facility Sub-Group | facilitysubgroup | The value representing the subgroup type. |
| Facility Type | facilitytype | The value representing the facility type, the most granular category of facilities. |
| Capacity | capacity | How many of capacity type/unit the facility is intended to hold. For many types of facilities, no capacity information was available. The capacity-related fields are blank when no information was provided in the source data. |
| Capacity Type | capacitytype | The value representing the unit type of capacity, such as beds, visitors, seats, etc. |
| Utilization | utilization | How many of capacity type/unit are being utilized at the facility. |
| Utilization Rate | utilizationrate | The ratio of the of utilization over the total facility capacity. |
| Area | area | The total area of the site measured in the Area Type unit. For many types of facilities, no area information was available. The area-related fields are blank when no information was provided in the source data. |
| Area Type | areatype | The unit of measurement for Area. |
| Operator Type | operatortype | Indicates whether the operating entity is public or non-public. |
| Operator Name | operatorname | The name of the operating entity. |
| Operator Abbreviation | operatorabbrev | Abbreviation for the operating entity. |
| Oversight Agency | oversightagency | The name of the agency overseeing the facility. |
| Oversight Abbreviation | oversightabbrev | Abbreviation for the oversight agency. |
| Oversight Level | oversightlevel | The level of government of the oversight agency: City, State, City-State, Federal, or Non-public Oversight. |
| Date Source Data Updated | datesourceupdated | The date the source data was updated within the parent database. |
| Agency Source | agencysource | The Agency whose data was used as the source for the record. |
| Source Dataset Name | sourcedatasetname | The name of the dataset the record came from. |
| Link to Data | linkdata | Link to view and/or description of data. |
| Processing Flag | processingflag | A text flag which indicates how the record was geoprocessed to fill in all required information, including geocoding and spatial joins. |



## VI. Source Data

The following datasets were used to populate the Facilities Database. The data sources that are published online as open data are automatically downloaded and aggregated to capture any updates provided by the source agency. The aggregated database is thoroughly checked through once per year to identify any problems with the process or major changes in the source data and how it's structured.



### NYC Administration for Children's Services (NYCACS)

| | |
| -- | -- |
| Dataset Name:  | Contractor Data |
| Last Updated: | 1/3/17 |
| Refresh Method: | Request file from agency |


### NYC Business Integrity Commission (NYCBIC)

| | |
| -- | -- |
| Dataset Name: | [Approved licensees and registrants for trade waste](https://data.cityofnewyork.us/Business/Approved-licensees/7atx-5a3s) |
| Last Updated: | 9/5/14 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department for the Aging (NYCDFTA)

| | |
| -- | -- |
| Dataset Name: | [DFTA Contracts](https://data.cityofnewyork.us/Social-Services/DFTA-Contracts/6j6t-3ixh) |
| Last Updated: | 1/20/17 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Citywide Administrative Services (NYCDCAS)

| | |
| -- | -- |
| Dataset Name: | [City Owned and Leased Properties](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-colp.page) |
| Last Updated: | 10/20/16 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Consumer Affairs (NYCDCA)

| | |
| -- | -- |
| Dataset Name: | [Legally Operating Businesses](https://data.cityofnewyork.us/Business/Legally-Operating-Businesses/w7w3-xahh) |
| Last Updated: | 1/20/17 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Correction (NYCDOC)

| | |
| -- | -- |
| Dataset Name: | [Correction Facilities Locations](http://www1.nyc.gov/site/doc/about/facilities-locations.page) |
| Last Updated: | 7/1/16 |
| Refresh Method: | Confirm on agency's website |


### NYC Department of Cultural Affairs (NYCDCLA)

| | |
| -- | -- |
| Dataset Name: | [DCLA Cultural Organizations](https://data.cityofnewyork.us/Recreation/DCLA-Cultural-Organizations/u35m-9t32) |
| Last Updated: | 3/22/16 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Education (NYCDOE)

| | |
| -- | -- |
| Dataset Name:  | [2015-2016 Blue Book](https://dnnhh5cc1.blob.core.windows.net/portals/0/Capital_Plan/Utilization_Reports/Blue%20Book%202015-2016.pdf?sr=b&si=DNNFileManagerPolicy&sig=AExrFIUz%2BQDwk%2FlptyHq0ZkW2Ur9J69SJuy4MgQ%2BAp4%3D) |
| Last Updated: | 11/1/16 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name: | [Routes](https://data.cityofnewyork.us/Transportation/Routes/8yac-vygm) |
| Last Updated: | 1/1/17 |
| Refresh Method: | Pull from NYC Open Data |

| | |
| -- | -- |
| Dataset Name: | [Universal Pre-K (UPK) School Locations](https://data.cityofnewyork.us/Education/Universal-Pre-K-UPK-School-Locations/kiyv-ks3f) |
| Last Updated: | 1/15/16 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Environmental Protection (NYCDEP)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### NYC Department of Health and Mental Hygiene (NYCDOHMH)

| | |
| -- | -- |
| Dataset Name: | [DOHMH Childcare Center Inspections](https://data.cityofnewyork.us/Health/DOHMH-Childcare-Center-Inspections/dsg6-ifza) |
| Last Updated: | 1/23/17 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Parks and Recreation (NYCDPR)

| | |
| -- | -- |
| Dataset Name: | [Parks Properties](https://data.cityofnewyork.us/City-Government/Parks-Properties/rjaj-zgq7) |
| Last Updated: | 8/27/16 |
| Refresh Method: | Pull from NYC Open Data |


### NYC Department of Sanitation (NYCDSNY)

| | |
| -- | -- |
| Dataset Name:  | DSNY_select_facs_07262916 |
| Last Updated: | 7/26/16 |
| Refresh Method: | Request file from agency |


### NYC Department of Small Business Services (NYCSBS)

| | |
| -- | -- |
| Dataset Name:  | SBS Workforce1 Career Center Locations |
| Last Updated: | 11/17/16 |
| Refresh Method: | Request file from agency |


### NYC Department of Transportation (NYCDOT)

| | |
| -- | -- |
| Dataset Name:  | Plaza Program |
| Last Updated: | 2/24/17 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | Facilities Data - Bridge Houses |
| Last Updated: | 2/23/17 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | Facilities Data - Ferry Terminals and Landings |
| Last Updated: | 2/23/17 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | Facilities Data - Parking Facilities |
| Last Updated: | 2/23/17 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | Facilities Data - Manned Facilities |
| Last Updated: | 2/23/17 |
| Refresh Method: | Request file from agency |


### NYC Department of Youth and Community Development (NYCDYCD)

| | |
| -- | -- |
| Dataset Name:  | COMPASS Program Locations |
| Last Updated: | 12/19/16 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | DYCD Other Program Locations |
| Last Updated: | 12/19/16 |
| Refresh Method: | Request file from agency |


### NYC HHS Accelerator (NYCHHS)

| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Financials Contracts |
| Last Updated: | 7/26/16 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | Financial Management System - Human Services Contracts |
| Last Updated: | 7/26/16 |
| Refresh Method: | Request file from agency |

| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Selected Proposals |
| Last Updated: | 7/26/16 |
| Refresh Method: | Request file from agency |


### NYC Human Resources Administration/Department of Social Services (NYCHRA/DSS)

| | |
| -- | -- |
| Dataset Name: | [HRA Locations](https://www1.nyc.gov/site/hra/locations/locations.page) |
| Last Updated: | 2/27/17 |
| Refresh Method: | Pull from agency's webmap |


### NYC Mayors Office of Management and Budget (NYCOMB)

| | |
| -- | -- |
| Dataset Name:  | District Resource Statement |
| Last Updated: | 6/30/16 |
| Refresh Method: | Request file from agency |


### NYS Department of Correction and Community Supervision (NYSDOCCS)

| | |
| -- | -- |
| Dataset Name: | [Facility Listing](http://www.doccs.ny.gov/faclist.html) |
| Last Updated: | 7/1/16 |
| Refresh Method: | Confirm on agency's website |


### NYS Department of Evironmental Conservation (NYSDEC)

| | |
| -- | -- |
| Dataset Name: | [Solid Waste Management Facilities](https://data.ny.gov/Energy-Environment/Solid-Waste-Management-Facilities/2fni-raj8) |
| Last Updated: | 1/9/17 |
| Refresh Method: | Pull from NYState Open Data |

| | |
| -- | -- |
| Dataset Name: | [Lands - Under the Care, Custody, and Control of DEC](http://gis.ny.gov/gisdata/inventories/details.cfm?DSID=1114) |
| Last Updated: | 3/1/16 |
| Refresh Method: | Pull from NYState GIS Clearinghouse |


### NYS Department of Health (NYSDOH)

| | |
| -- | -- |
| Dataset Name: | [Health Facility General Information](https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r) |
| Last Updated: | 1/20/17 |
| Refresh Method: | Pull from NYState Open Data |


### NYS Department of Transportation (NYSDOT)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### NYS Education Department (NYSED)

| | |
| -- | -- |
| Dataset Name: | [Listings - Active Institutions with GIS coordinates and OITS Accuracy Code](https://portal.nysed.gov/discoverer/app/grid;jsessionid=eikT4MZCXS4gnCu4gkga8RxAT-LFQX1XhLGyOQErv16YJWGj_jo8!-214928944?bi_origin=dvtb&bi_cPath=dvtb&numberLocale=en_US&source=dvtb&gotoNthPage=1&bi_tool=rt&event=bi_showTool&bi_rownavdv=s25&stateStr=eNrtVlFzmzgQ%2FjPY0xtPMiBjJ3nwg4vdlGmKe8ZpmnthZEkYJRgIksHOr79Fog71JO1Q957OL9rVov202tWKz2DbLDa65VKOUDdJKRuhq67IRt08TeXI7LKCJXIEi3BCu0JiyUbvhoO%2FDJwZHTSkYac%2FASm0SIiWNNayFmyTV5pBEqNbEDkSBe2S5HFEwgBbJjLKRxFJgLNXtAioAAWcnmIRbDvIskxw9RnNWdi5mCJzFuNMKQu8jJnSPqS5knOWpbkU5066SeROmSZMEADDaQkoIY4Fa0JftIYeU1gthLLd8IShJtxl%240g5xImG4Ro8t%24u4CTaowCLGpHKwzmfuwlfqtavlmBAlHSha03HYOoov0U5wgmMNe3BCqyqvqAos880PG%2FUPIrzmtVearLjcUL1ZB11%2466CrpqP9liOWP%2FjdH%2FhZrU%2Fm0%2FjVHKHfRqov1B7pqj1S1UQNiPa3xk1ElSjJ00TZ%2Fc1Se%24wy9lqQV8d0UJ06KUQgqgMff7uU8jmlPOSM6nhVRpw4giFJ8zUsRs73bsX50yu9ax6dNZc269ga7oat6jN5eN2M7DfuVp2Gg1vab5%2FqNNvEOH8tKrv9U0ckL1ijPvs7YB5%2Fn96o9VMW%24CxmRL8MdaFq5%2F5kANM%24DsPwUine9E59v5%2FNP0mw6s%2Fv5zPv28v0k%24td%249V0qKZ%2F306nnpprjLnrfPw88yaykarB0Vdr34gHFUX%2FYffsNxn%24ufAP3hHUvvD%2F8IzQQQPj4s%24%2FdodJRkdv8SVKk%2FovBEO%2FCd4%2FGvw2r%2F7zlIqC5QBmad4Tadpj0wKG7eOZtY57sECA13NpnZtl73G3pUVviZ9LmBABVnRZ7rYZ6RWglw%2477QMtgE3YZVFhAXEyNbRc%2FgRSfd9tl1zEshIkSis8Bbc3rtR4ZnMqo548s55L2zSrJUseMb6K5IHxOseUA2%2Fskeh7aBrkQW%24n4hJrEFWIGc7xWrwk4EQBTxTwRAFPFPBEAU8U8EQBTxTwf0EBY6LpTwlPkl33gv1CC1eKFyrTT%24ncr9ncg1piZDmnxo3rL6rmCIKxs3C%2FTgPXA8PiduHOPD%244cxcfA6AagTObzSeuN15M%2FWDsTYKKh4CHczsfO%2FfwdTLtoA%24WQeQuMwrOSpb%2FCyl4PR4%3D) |
| Last Updated: | 1/23/17 |
| Refresh Method: | Manual download |


### NYS Office for People With Developmental Disabilities (NYSOPWDD)

| | |
| -- | -- |
| Dataset Name: | [Directory of Developmental Disabilities Service Provider Agencies](https://data.ny.gov/Human-Services/Directory-of-Developmental-Disabilities-Service-Pr/ieqx-cqyk) |
| Last Updated: | 12/22/15 |
| Refresh Method: | Pull from NYState Open Data |


### NYS Office of Alcoholism and Substance Abuse Services (NYSOASAS)

| | |
| -- | -- |
| Dataset Name:  | List of NYC Programs |
| Last Updated: | 1/3/17 |
| Refresh Method: | Receive scheduled email transfer from agency |


### NYS Office of Children and Family Services (NYSOCFS)

| | |
| -- | -- |
| Dataset Name: | [Facilities](http://ocfs.ny.gov/main/rehab/regionalListing1.asp) |
| Last Updated: | 7/1/16 |
| Refresh Method: | Confirm on agency's website |


### NYS Office of Mental Health (NYSOMH)

| | |
| -- | -- |
| Dataset Name: | [Local Mental Health Programs](https://data.ny.gov/Human-Services/Local-Mental-Health-Programs/6nvr-tbv8) |
| Last Updated: | 10/24/16 |
| Refresh Method: | Pull from NYState Open Data |


### NYS Office of Parks, Recreation and Historic Preservation (NYSOPRHP)

| | |
| -- | -- |
| Dataset Name: | [National Register of Historic Places](https://data.ny.gov/Recreation/National-Register-of-Historic-Places/iisn-hnyv) |
| Last Updated: | 12/18/15 |
| Refresh Method: | Pull from NYState Open Data |

| | |
| -- | -- |
| Dataset Name: | [State Park Facility Points](https://data.ny.gov/Recreation/State-Park-Facility-Points/9uuk-x7vh) |
| Last Updated: | 2/4/16 |
| Refresh Method: | Pull from NYState Open Data |


### NYS Unified Court System (NYCOURTS)

| | |
| -- | -- |
| Dataset Name: | [The Courts](http://www.nycourts.gov/courts/index.shtml) |
| Last Updated: | 7/1/16 |
| Refresh Method: | Confirm on agency's website |


### National Park Service (USNPS)

| | |
| -- | -- |
| Dataset Name: | [Administrative Boundaries of National Park System Units](https://irma.nps.gov/DataStore/Reference/Profile/2225713) |
| Last Updated: | 9/30/16 |
| Refresh Method: | Pull from USNPS |


### New York City Housing Authority (NYCHA)

| | |
| -- | -- |
| Dataset Name: | [NYCHA PSA (Police Service Areas)](https://data.cityofnewyork.us/Housing-Development/NYCHA-PSA-Police-Service-Areas-/72wx-vdjr) |
| Last Updated: | 9/5/14 |
| Refresh Method: | Pull from NYC Open Data |


### Port Authority of New York and New Jersey (PANYNJ)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### Roosevelt Island Operating Corporation (RIOC)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### Trust for Governors Island (TGI)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### US Courts (USCOURTS)

| | |
| -- | -- |
| Dataset Name: | [Court Locator Results](http://www.uscourts.gov/court-locator/city/New%20York/state/NY) |
| Last Updated: | 7/1/16 |
| Refresh Method: | Confirm on agency's website |


### US Department of Transportation (USDOT)

| | |
| -- | -- |
| Dataset Name: | [Airports](http://www.rita.dot.gov/bts/sites/rita.dot.gov.bts/files/publications/national_transportation_atlas_database/2015/point) |
| Last Updated: | 8/1/15 |
| Refresh Method: | Pull from US DOT |

| | |
| -- | -- |
| Dataset Name: | [U.S. Army Corps of Engineers Ports](http://www.rita.dot.gov/bts/sites/rita.dot.gov.bts/files/publications/national_transportation_atlas_database/2015/point) |
| Last Updated: | 8/1/15 |
| Refresh Method: | Pull from US DOT |


### Amtrak (Amtrak)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### Brooklyn Bridge Park Corporation (BBPC)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### Federal Bureau of Prisons (FBOP)

| | |
| -- | -- |
| Dataset Name: | [Our Locations](https://www.bop.gov/locations/map.jsp#) |
| Last Updated: | 7/1/16 |
| Refresh Method: | Confirm on agency's website |


### Food Bank of NYC (FBNYC)

| | |
| -- | -- |
| Dataset Name:  | FBNYC Food Pantry Soup Kitchen List 8-5-16 |
| Last Updated: | 8/5/16 |
| Refresh Method: | Request file from agency |


### Hudson River Park Trust (HRPT)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |


### Metropolitan Transportation Authority (MTA)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 3/1/15 |
| Refresh Method: | Confirm with agency |



<!-- ## Appendix I. Deduping

More details on the methodology and data structure coming soon!


**Table of Datasets with Overlapping Content:**

| Facility Subgroup | Primary Dataset | Secondary Dataset |
| -- | -- | -- |
| | | | 


## Appendix II. Full Classification Hierarchy

Interactive visualization of all 450+ facility types coming soon!

 -->
