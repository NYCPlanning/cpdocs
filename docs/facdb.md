# City Planning Facilities Database

## I. Overview

The City Planning Facilities Database aggregates more than 35,000 records from 43 different [public data sources](http://docs.capitalplanning.nyc/facdb/#vi-source-data) provided by City, State, and Federal agencies. While each source agency classifies its facilities according to their own naming systems, we have grouped all facilities and program sites into the following seven categories to help planners navigate the data more easily:

* Health and Human Services
* Education, Child Welfare, and Youth
* Parks, Gardens, and Historical Sites
* Libraries and Cultural Programs
* Public Safety, Emergency Services, and Administration of Justice
* Core Infrastructure and Transportation
* Administration of Government

Within each of these domains, each record is further categorized into a set of facility groups, subgroups, and types that are intended to make the data easy to navigate and more useful for specific planning purposes. Facility types and names appear as they do in source datasets, wherever possible. A full listing of the facility categories is provided in the [Contents and Classification Hierarchy](http://docs.capitalplanning.nyc/facdb/#ii-contents-and-classification-hierarchy) section.

This database and its [interactive map](http://capitalplanning.nyc.gov/facilities) build upon and replace City Planning’s decades-old work on the Selected Facilities and Program Sites Database. Improvements include more facility types, improved data quality, and a restructured database for easier use. We have also automated our data-update processes for the majority of sources. Please read more about the [limitations](http://docs.capitalplanning.nyc/facdb/#iii-limitations-and-disclaimers) of this data product below.

Special thanks to all the agencies who make their data available for this effort, particularly those who publish their data on a routine basis.

We are constantly looking for ways to improve and add additional value to the database. Please reach out to the NYC DCP Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions.

###  General information ###

| | |
| :------------: | ------------- |
| Dataset Name | "Facilities Database"|
| Description | The Facilities Database (FacDB) captures the locations and descriptions of public and private facilities ranging from the provision of social services, recreation, education, to solid waste management|
| Data format | [Web-map](http://capitalplanning.nyc.gov/facilities), Shapefile, CSV, GeoJSON |
| Projection | WGS84 |
| Date last updated | 10/30/18 |

## II. Contents and Classification Hierarchy

In order of increasing granularity, each record that is included in the database is classified by DCP into a **Domain > Facility Group > Facility Subgroup > Facility Type**. There are around 450 facility types. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are also cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description. The tables below describe each of the Subgroups in each of the seven Domains; however, the Facility Types within them are not listed.

#### Education, Child Welfare, and Youth Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Schools (K-12) | ----------- | K-12 and alternative equivalency programs overseen by NYC Dept. of Education and NYS Education Department |
| | Public K-12 Schools | Public elementary, middle, and high schools |
| | Charter K-12 Schools | Publicly funded charter elementary, middle, and high schools |
| | Non-Public K-12 Schools | Private elementary, middle, and high schools |
| | Special Ed and Schools for Students with Disabilities | Specialized schools and educational services for students with disabilities |
| | GED and Alternative High School Equivalency | Alternative programs for obtaining high school equivalency degree |
| Child Care and Pre-Kindergarten | ----------- | Childcare centers are overseen by NYC Administration for Children's Services and NYC Dept. of Mental Health and Hygiene |
| | DOE Universal Pre-Kindergarten | NYC DOE designated Universal Pre-K center |
| | Dual Child Care and Universal Pre-K | Center that offers both an NYC DOE designated Universal Pre-K services and other childcare services |
| | Child Care | Group and school-based child care centers for infants, toddlers, and preschoolers |
| | Preschools for Students with Disabilities | Center specialized in preschool students with disabilities |
| Child Services and Welfare | ----------- | Services overseen by NYC Administration for Children's Services and NYS Education Department and NYC Department of Education |
| | Foster Care Services and Residential Care | Foster care services and juvenile non-secure placement |
| | Preventative Care, Evaluation Services, and Respite | Preventative care and intervention services |
| | Child Nutrition | Summer and year-round child feeding centers, either based at NYC Dept of Education schools or tracked by New York State Education Department |
| Youth Services | ----------- | Services overseen by NYC Dept. of Youth and Community Development |
| | Comprehensive After School System (COMPASS) Sites | Comprehensive After School System (COMPASS) Sites |
| | Youth Centers, Literacy Programs, Job Training, and Immigrant Services | Youth Centers, Literacy Programs, Job Training, and Immigrant Services |
| Camps | ----------- | Camps overseen by NYC Dept. of Mental Health and Hygiene |
| | Camps | Preschool age and all age camps |
| Higher Education | ----------- | Public and privately operated 2 and 4-year colleges and universities |
| | Colleges or Universities | Public and privately operated 2 and 4-year colleges and universities |
| Vocational and Proprietary Schools | ----------- | ESL schools and trade colleges |
| | Proprietary Schools | ESL schools and trade colleges |


#### Parks, Gardens, and Historical Sites Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Parks and Plazas | ----------- | Properties operated by NYC Parks, NYC Dept. of Transportation, NYS Office of Parks, Recreation and Historic Preservation, NYS Dept. of Conservation, and City-State corporations and trusts |
| | Parks | Flagship parks, community parks, state parks, and City-State parks |
| | Recreation and Waterfront Sites | Playgrounds, waterfront facilities, and recreation fields and courts |
| | Streetscapes, Plazas, and Malls | Pedestrian plazas, malls, triangle plazas, and parkways |
| | Gardens | Community gardens |
| | Privately Owned Public Space | Plazas, arcades, and other open space provided for public use by a private office or residential building owner |
| | Preserves and Conservation Areas | Nature areas, preserves, wetlands, and state forests |
| | Cemeteries | Cemeteries operated by NYC Parks |
| Historical Sites | ----------- | Sites operated by NYC Parks, NYS Office of Parks, Recreation and Historic Preservation, and US National Park Service |
| | Historical Sites | Historic house parks, State historic places, national monuments, and national memorials |


#### Libraries and Cultural Programs Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Libraries | ----------- | Libraries operated by New York Public Libraries, Queens Public Libraries, and Brooklyn Public Libraries and academic institutions |
| | Public Libraries | All public libraries |
| | Academic and Special Libraries | Libraries operated by academic institutions or other specialized organizations |
| Cultural Institutions | ----------- | Institutions licensed or funded by the NYC Dept. of Cultural Affairs |
| | Museums | Publicly and privately operated museums |
| | Historical Societies | Historical societies |
| | Other Cultural Institutions | Zoos, botanical gardens, performing arts centers, and multi-disciplinary art centers |


#### Public Safety, Emergency Services, and Administration of Justice Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Emergency Services | ----------- | Services provided by Fire Dept. of New York |
| | Fire Services | Firehouses |
| | Other Emergency Services | Ambulance and Emergency Medical Stations |
| Public Safety | ----------- | Services provided by the New York Police Dept. and New York Housing Authority Police |
| | Police Services | NYPD and NYCHA police stations |
| | School-Based Safety Program | Public safety program on a school campus |
| | Other Public Safety | Other public safety-related support centers |
| Justice and Corrections | ----------- | Courts and correctional facilities operated by NYC Dept. of Correction, NYS Unified Court System, NYS Dept. of Corrections and Community Supervision, US Courts, and the Federal Bureau of Prisons |
| | Courthouses and Judicial | Courthouses, clerk offices, and court librarians |
| | Detention and Correctional | Correctional and detention centers |


#### Health and Human Services Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Health Care | ----------- | Health facilities overseen by NYC Health and Hospitals Corporation, NYC Health and Human Services, NYS Dept. of Health, NYS Office of Mental Health, and NYS Office of Alcoholism and Substance Abuse Services |
| | Hospitals and Clinics | Urgent care hospitals, diagnostic and treatment centers, and school-based health facilities |
| | Mental Health | Inpatient, outpatient, and emergency mental health services |
| | Residential Health Care | Nursing homes, hospice care, and supportive housing |
| | Chemical Dependency | Monitored support, inpatient, outpatient, and crisis services |
| | Health Promotion and Disease Prevention | Programs focused on improving health through education and disease prevention |
| | Other Health Care | Rehab, respite services, vaccination services, AIDS counseling, and home health centers |
| Human Services | ----------- | Services overseen by NYC Dept. of Homeless Services, NYC Dept. of Human Resources, NYC Mayoralty, and others |
| | Senior Services | Neighborhood senior centers, meal delivery programs, and other services for seniors |
| | Community Centers and Community School Programs | Community centers that provide multiple social services at one site |
| | Financial Assistance and Social Services | SNAP, Child Support, and Medicaid Centers operated by NYC Human Resources Administration |
| | Workforce Development | Workforce 1 Centers and other vocational services for adults |
| | Legal and Intervention Services | Early intervention, criminal defense, and mediation services |
| | Programs for People with Disabilities | Specialized child care, caregiver support, and recreational services |
| | Permanent Supportive SRO Housing | Permanent supportive SRO housing contracted by DHS |
| | Non-residential Housing and Homeless Services | Non-residential homelessness prevention services |
| | Soup Kitchens and Food Pantries | Soup kitchens and food pantries |


#### Core Infrastructure and Transportation Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Solid Waste | ----------- | Sites overseen and operated by NYC Dept. of Sanitation, NYC Business Integrity Commission, and NYS Dept. of Conservation |
| | Solid Waste Processing | Material recovery, composting, landfill gas recovery, and scrap metal processing facilities |
| | Solid Waste Transfer and Carting | Waste carter sites and transfer stations |
| Water and Wastewater | ----------- | Sites overseen and operated by NYC Dept. of Environmental Protection |
| | Wastewater and Pollution Control | Wastewater treatment plants and other sites related to wastewater conveyance and pollution control |
| | Water Supply | Sites related to water supply |
| Transportation | ----------- | Sites operated or overseen by Metropolitan Transportation Authority, Port Authority of NY and NJ, NYC Dept. of Transportation, NYC Dept. of Consumer Affairs, US Dept. of Transportation, and others |
| | Parking Lots and Garages | Publicly and commercially operated parking lots and garages |
| | Bus Depots and Terminals | School bus depots, MTA bus depots, and Port Authority bus terminals |
| | Rail Yards and Maintenance | Rail yards and maintenance facilities |
| | Ports and Ferry Landings | Ferry landings, cruise terminals, and ports |
| | Airports and Heliports | Publicly and privately operated airports, heliports, and seaplane bases |
| | Other Transportation | Uncategorized transportation-related sites |
| Telecommunications | ----------- | Sites operated or overseen by Dept. of Information Technology and Telecommunications and other City telecommunications services |
| | Telecommunications | Antennas and other telecommunications sites |
| Material Supplies and Markets | ----------- | Sites operated or overseen by Dept. of Information Technology and Telecommunications and other City telecommunications services |
| | Material Supplies | Asphalt plants and other material processing facilities |
| | Wholesale Markets | Wholesale food and commercial markets |


#### Administration of Government Domain ####

| Facility Group | Facility Subgroup | Description |
| :------ | :-- | :-- |
| Offices, Training, and Testing | ----------- | All City owned or leased offices overseen by Dept. of Citywide Administrative Services |
| | Offices | Offices used by City agencies |
| | Training and Testing | Training, and testing sites used by City agencies |
| City Agency Parking, Maintenance, and Storage | ----------- | City owned or leased properties used for City vehicle and equipment-related operations by Dept. of Citywide Administrative Services |
| | Custodial | City agency custodial sites |
| | Maintenance and Garages | City agency vehicle maintenance sites |
| | City Agency Parking | City agency parking lots |
| | Storage | City agency storage sites |
| Other Property | ----------- | City owned or leased property without a categorized use overseen by Dept. of Citywide Administrative Services |
| | Miscellaneous Use | Property without a categorized use |
| | Properties Leased or Licensed to Non-public Entities | Properties Leased or Licensed to Non-public Entities |


## III. Limitations and Disclaimers

The City Planning Facilities Database (FacDB) is only as good as the source data it aggregates, and the Department of City Planning cannot verify the accuracy of all records. Please read more about specific data and analysis limitations before using this data.

**Analysis Limitations.** As a result of the data limitations and inconsistencies listed below users should be careful in their use of this database so as to avoid developing suspect analyses. For example, a comparison of the density or accessibility of facilities across neighborhoods should recognize that some of the facilities included are organizational headquarters rather than service sites and that this database is not authoritatively comprehensive. In addition, we rely on source data from other agencies to populate the database, and some of these sources may fall out-of-date. Users can find the date of each source dataset’s latest update in the [Source Data](http://docs.capitalplanning.nyc/facdb/#vi-source-data) section.

**Missing Records.** Currently, FacDB is the most comprehensive spatial data resource available for facilities run by public and non-public entities in NYC, but it does not claim to capture every facility within the specified domains. Some facilities are deliberately excluded from the data that source agencies provide in order to protect the safety and privacy of their clients. Also, many records could not be geocoded. To learn more about how the data are processed, please review the [Methodology](http://docs.capitalplanning.nyc/facdb/#iv-methodology).
 
**Duplicates.** Please be aware that this beta version of the database includes cases of duplicate records for the same facility because several source datasets have content that overlaps with other datasets.

**Administrative Addresses.** There are known to be cases when the address provided in the source data is for a headquarters office rather than the facility site location. Unfortunately, these could not be systematically verified. For more detailed information on a specific facility reach out to the respective oversight agency.

**Public Accessibility of Sites.** DCP is unable to verify the public accessibility of all sites. For example, some playgrounds or playing fields may only be accessible to participants in certain programs.

If you have any questions about or comments on these data please contact the NYC DCP Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov).



## IV. Methodology

### Data Processing

Since the facility records are aggregated from many datasets designed for different purposes, the data will be transformed over several stages to reach its final state. The stages are described below and all the scripts used are available on the [NYC Planning GitHub page](https://github.com/NYCPlanning/db-facilities).

**Assembly.**
First, the desired columns in the source data are mapped to the columns in FacDB schema. The facilities are classified using categories or descriptions provided by the agency. In general, the final Facility Type categories in FacDB are formatted versions of the original, most granular classification provided by the agency, but there are cases where the source description was too specific and records were grouped together into broader type categories using keywords in the description.

**Geoprocessing.**
Many source datasets only provide addresses without coordinates. Records without coordinates are geocoded with the [GeoClient API](https://developer.cityofnewyork.us/api/geoclient-api) using the Address and either the Borough or ZIP Code to get the BIN, BBL, and other standardized location details. If the record can be assigned a BIN value, the BIN's centroid is used as the point geometry. Source records with only coordinates and no addresses are processed by doing a spatial join with MapPLUTO to get the BBL and other location related details like Address, Borough, ZIP Code, and BIN when there is a 1-1 BIN-BBL relationship. There are many cases where an agency provides coordinates but the coordinates they provided fall in the roadbed, and not inside a BBL boundary, due to the geocoding technique used by the source. In these cases, the geometry was replaced with the BBL centroid if a BIN could not be assigned and used for the geometry instead. Each record in the database is flagged with a code for the geoprocessing technique that was used to complete all of its information.

**Duplicate Record Removal.** Several of the source datasets have content that overlaps with other datasets. Duplicate records were identified by querying for all the records that fall within the same BIN or BBL and have the same Facility Subgroup or Type, same Facility Name, or same Oversight Agency. The values from the duplicate records were merged before dropping the duplicate records from the database.


<!-- The processing steps and assumptions used for each record are indicated in the Processing Flag (processingflag) field in the database. Each of the flags is defined in the table below.

| Data Processing Flag | Definition |
| :-- | :-- |
| address2geom_borough | Geometry, BBL, BIN, and Zip Code were generated by NYC GeoClient using address and borough provided by an agency. |
| address2geom_zipcode | Geometry, BBL, BIN, and borough were generated by NYC GeoClient using the address and zip code provided by the agency. |
| bbljoin | Geometry and address were provided by an agency but without a BBL. BBL was obtained by doing a spatial join with MapPLUTO |
| bbljoin2address | Geometry was provided by an agency but without an address or BBL. BBL and address were obtained by doing a spatial join with MapPLUTO |
| bbljoin_closest | Geometry was provided by an agency without a BBL. No spatial overlap was found with a BBL in MapPLUTO, even though the facility is of a type which should be located on a BBL lot. The closest BBL was assigned to the record. |
| bbljoin2address_closest | Geometry was provided by an agency without an address or BBL. No spatial overlap was found with a BBL in MapPLUTO, even though the facility is of a type which should be located on a BBL lot. The closest BBL was assigned to the record. |

 -->

## V. Data Dictionary

The following table lists and defines each of the fields presented in the Facilities Database as they are organized in the database from left to right.

| Field Alias | Field Name | Description |
| :------------------- | :------------------- | :-------------------- |
| Unique Identifier | uid | Universal Unique Identifier.  When a row is added to the table the uid is automatically generated, enabling database replication. |
| Geom | geom | How the feature is spatially represented. |
| Old ID | idold | Non-unique identifier generated and maintained by the former database admin that relates to old version of SFPSD. |
| Agency ID | idagency | Non-unique identifier generated and maintained by the data admin of the parent agency that relates to the record in the source dataset. |
| Facility Name | facname | The name of the facility in proper case. |
| Address Number | addressnum | The address number of where the facility is located, validated by GeoClient. If the address that is available for the site is not complete with an address number (only the street name), this field is left blank. |
| Street Name | streetname | The name of the street where the facility is located, validated by GeoClient. If the address that is available for the site is not complete with an address number (only the street name), this field is left blank. |
| Address | address | The concatenated value of AddressNumber and StreetName of where the facility is located. If there is not a valid, complete address available, any location description that was provided is included in this field. |
| City | city | The USPS preferred the name of the addressed city where the facility is located. Generated by GeoClient and spatial joins. This field contains some blanks for facilities that do not overlap with the shoreline Zip Code boundaries. |
| Borough | boro | The full name of the borough the facility is within. |
| Borough Code | borocode | The number value representing the borough the facility is within. |
| ZIP Code | zipcode | The ZIP Code the facility is within. This field contains some blanks for facilities that do not overlap with the shoreline Zip Code boundaries. |
| Latitude | latitude | The latitude of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| Longitude | longitude | The longitude of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| X Coordinate | xcoord | The X coordinate of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| Y Coordinate | ycoord | The Y coordinate of the location either calculated using the coordinates in the source data or provided by GeoClient. |
| BIN | bin | The [BIN](http://a030-goat.nyc.gov/goat/glossary.aspx#bin) values for the buildings the facility is located in. This field contains blanks because 1) some lots do not have buildings on them, and 2) some lots have multiple buildings and a single BIN could not be reliably assigned given the information provided in the source data. There may also be cases where a facility is actually comprised by multiple BINs but only one is recorded in FacDB because the others were not provided in the source data and could not be reliably assumed based on the single address provided for the facility. |
| BBL | bbl | The [BBL](http://a030-goat.nyc.gov/goat/glossary.aspx#bbl) values for the tax lots the facility is located on. This field contains blanks, because some facility categories, like pedestrian plazas, are not located on tax lots. There may also be cases where a facility is actually comprised by multiple BBLs but only one is recorded in FacDB because the others were not provided in the source data and could not be reliably assumed based on the single address provided for the facility. |
| Community Board | commboard | The Community District the facility is within. This field contains blanks because the Community District boundaries do not capture facilities beyond the shoreline. |
| Council District | council | The City Council District the facility is within |
| Census Tract | censtract | The U.S. Census Tract the facility is within |
| NTA | nta | The Neighborhood Tabulation Area (NTA) the facility is within. This field contains blanks because the NTA boundaries do not capture facilities beyond the shoreline. |
| Facility Domain | facdomain | The value representing the facility domain, the broadest category. |
| Facility Group | facgroup | The value representing the group type, the second broadest category. |
| Facility Sub-Group | facsubgrp | The value representing the subgroup type. |
| Facility Type | factype | The value representing the facility type, the most granular category of facilities. |
| Capacity | capacity | How many of capacity type/unit the facility is intended to hold. For many types of facilities, no capacity information was available. The capacity-related fields are blank when no information was provided in the source data. |
| Capacity Type | captype | The value representing the unit type of capacity, such as beds, visitors, seats, etc. |
| Utilization | util | How many of capacity type/unit are being utilized at the facility. |
| Utilization Rate | utilrate | The ratio of the of utilization over the total facility capacity. |
| Area | area | The total area of the site measured in the Area Type unit. For many types of facilities, no area information was available. The area-related fields are blank when no information was provided in the source data. |
| Area Type | areatype | The unit of measurement for Area. |
| Property Type | proptype | Indicates whether the property is owned or leased by the City. |
| Operator Type | optype | Indicates whether the operating entity is public or non-public. |
| Operator Name | opname | The name of the operating entity. |
| Operator Abbreviation | opabbrev | Abbreviation for the operating entity. |
| Oversight Agency | overagency | The name of the agency overseeing the facility. |
| Oversight Abbreviation | overabbrev | Abbreviation for the oversight agency. |
| Oversight Level | overlevel | The level of government of the oversight agency: City, State, City-State, Federal, or Non-public Oversight. |
| Date Source Data Updated | datadate | The date the source data was updated within the parent database. |
| Agency Source | datasource | The Agency whose data was used as the source for the record. |
| Source Dataset Name | dataname | The name of the dataset the record came from. |
| Link to Data | dataurl | Link to view and/or description of data. |


## VI. Source Data

The following datasets were used to populate the Facilities Database. The data sources that are published online as open data are automatically downloaded and aggregated to capture any updates provided by the source agency.


### NYC Administration for Children's Services (NYCACS)

| | |
| -- | -- |
| Dataset Name:  | Contractor Data |
| Last Updated: | 10/24/2018 |


### NYC Business Integrity Commission (NYCBIC)

| | |
| -- | -- |
| Dataset Name: | [Approved licensees and registrants for trade waste](https://data.cityofnewyork.us/Business/Approved-licensees-and-registrants-for-trade-waste/hsjb-p5ky/data) |
| Last Updated: | 10/24/18 |


### NYC Department for the Aging (NYCDFTA)

| | |
| -- | -- |
| Dataset Name: | [DFTA Contracts](https://data.cityofnewyork.us/Social-Services/DFTA-Contracts/6j6t-3ixh) |
| Last Updated: | 10/24/2018 |


### NYC Department of City Planning (NYCDCP)

| | |
| -- | -- |
| Dataset Name: | [New York City Privately Owned Public Space Database](https://nycopendata.socrata.com/Housing-Development/Privately-Owned-Public-Spaces/fum3-ejky) |
| Last Updated: | 10/24/2018 |


### NYC Department of Citywide Administrative Services (NYCDCAS)

| | |
| -- | -- |
| Dataset Name: | [City Owned and Leased Properties](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-colp.page) |
| Last Updated: | 10/25/2018 |


### NYC Department of Consumer Affairs (NYCDCA)

| | |
| -- | -- |
| Dataset Name: | [Legally Operating Businesses](https://data.cityofnewyork.us/Business/Legally-Operating-Businesses/w7w3-xahh) |
| Last Updated: | 10/24/2018 |


### NYC Department of Correction (NYCDOC)

| | |
| -- | -- |
| Dataset Name: | [Correction Facilities Locations](http://www1.nyc.gov/site/doc/about/facilities-locations.page) |
| Last Updated: | 10/25/2018 |


### NYC Department of Cultural Affairs (NYCDCLA)

| | |
| -- | -- |
| Dataset Name: | [DCLA Cultural Organizations](https://data.cityofnewyork.us/Recreation/DCLA-Cultural-Organizations/u35m-9t32) |
| Last Updated: | 10/24/2018 |


### NYC Department of Education (NYCDOE)

| | |
| -- | -- |
| Dataset Name: | Blue Book|
| Last Updated: | 12/27/2017 |


| | |
| -- | -- |
| Dataset Name: | [Universal Pre-K (UPK) School Locations](https://data.cityofnewyork.us/Education/Universal-Pre-K-UPK-School-Locations/kiyv-ks3f) |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name: | [Routes](https://data.cityofnewyork.us/Transportation/Routes/8yac-vygm) |
| Last Updated: | 10/24/2018 |


### NYC Department of Health and Mental Hygiene (NYCDOHMH)

| | |
| -- | -- |
| Dataset Name: | [DOHMH Childcare Center Inspections](https://data.cityofnewyork.us/Health/DOHMH-Childcare-Center-Inspections/dsg6-ifza) |
| Last Updated: | 10/24/2018 |


### NYC Department of Parks and Recreation (NYCDPR)

| | |
| -- | -- |
| Dataset Name: | [Parks Properties](https://data.cityofnewyork.us/City-Government/Parks-Properties/rjaj-zgq7/data) |
| Last Updated: | 10/24/2018 |


### NYC Department of Sanitation (NYCDSNY)

| | |
| -- | -- |
| Dataset Name:  | DSNY Facilities |
| Last Updated: | 10/24/2018 |


### NYC Department of Small Business Services (NYCSBS)

| | |
| -- | -- |
| Dataset Name:  | [SBS Workforce1 Career Center Locations](https://data.cityofnewyork.us/dataset/Center-Service-Locations/6smc-7mk6) |
| Last Updated: | 10/24/2018 |


### NYC Department of Transportation (NYCDOT)

| | |
| -- | -- |
| Dataset Name:  | Plaza Program |
| Last Updated: | 2/23/2017 |


| | |
| -- | -- |
| Dataset Name:  | Parking Facilities |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name:  | Manned Facilities |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name:  | Bridge Houses |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name:  | Ferry Terminals and Landings |
| Last Updated: | 10/24/2018 |


### NYC Department of Youth and Community Development (NYCDYCD)

| | |
| -- | -- |
| Dataset Name:  | [DYCD After-School Programs](https://data.cityofnewyork.us/Education/DYCD-after-school-programs/mbd7-jfnc) |
| Last Updated: | 10/24/2018 |


### NYC HHS Accelerator (NYCHHS)

| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Financials Contracts |
| Last Updated: | 7/26/2016 |


| | |
| -- | -- |
| Dataset Name:  | Financial Management System - Human Services Contracts |
| Last Updated: | 7/26/2016 |


| | |
| -- | -- |
| Dataset Name:  | HHS Accelerator - Selected Proposals |
| Last Updated: | 7/26/2016 |


### NYC Health and Hospitals Corporation (NYCHHC)

| | |
| -- | -- |
| Dataset Name: | [Health and Hospitals Corporation (HHC) Facilities](https://data.cityofnewyork.us/Health/Health-and-Hospitals-Corporation-HHC-Facilities/f7b6-v6v3) |
| Last Updated: | 10/24/2018 |


### NYC Human Resources Administration/Department of Social Services (NYCHRA/DSS)

| | |
| -- | -- |
| Dataset Name: | [HRA Locations](https://www1.nyc.gov/site/hra/locations/locations.page) |
| Last Updated: | 10/24/2018 |


### NYS Department of Correction and Community Supervision (NYSDOCCS)

| | |
| -- | -- |
| Dataset Name: | [Facility Listing](http://www.doccs.ny.gov/faclist.html) |
| Last Updated: | 10/24/2018 |


### NYS Department of Environmental Conservation (NYSDEC)

| | |
| -- | -- |
| Dataset Name: | [Solid Waste Management Facilities](https://data.ny.gov/Energy-Environment/Solid-Waste-Magement-Facilities/2fni-raj8) |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name: | [Lands - Under the Care, Custody, and Control of DEC](http://gis.ny.gov/gisdata/inventories/details.cfm?DSID=1114) |
| Last Updated: | 10/24/2018 |


### NYS Department of Health (NYSDOH)

| | |
| -- | -- |
| Dataset Name: | [Health Facility General Information](https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r) |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name: | [Nursing Home Weekly Bed Census: Last Submission](https://health.data.ny.gov/Health/Nursing-Home-Weekly-Bed-Census-Last-Submission/izta-vnpq/data) |
| Last Updated: | 10/24/2018 |


### NYS Department of Transportation (NYSDOT)

| | |
| -- | -- |
| Dataset Name: | [Selected Facilities and Program Sites Database](http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-selfac.page) |
| Last Updated: | 10/24/2018 |


### NYS Education Department (NYSED)

| | |
| -- | -- |
| Dataset Name: | [Listings - Active Institutions with GIS coordinates and OITS Accuracy Code](https://data.nysed.gov/downloads.php) |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name: | [2017-2018 Nonpublic Enrollment by Grade](http://www.p12.nysed.gov/irs/statistics/nonpublic/) |
| Last Updated: | 10/24/2018 |


### NYS Office for People With Developmental Disabilities (NYSOPWDD)

| | |
| -- | -- |
| Dataset Name: | [Directory of Developmental Disabilities Service Provider Agencies](https://data.ny.gov/Human-Services/Directory-of-Developmental-Disabilities-Service-Pr/ieqx-cqyk) |
| Last Updated: | 10/24/2018 |


### NYS Office of Alcoholism and Substance Abuse Services (NYSOASAS)

| | |
| -- | -- |
| Dataset Name: | [NYS OASAS-Certified Chemical Dependence Treatment Programs Located in NYC](https://www.oasas.ny.gov/providerDirectory/index.cfm?search_type=2) |
| Last Updated: | 10/24/2018 |
| Notes: | OASAS records are updated more frequently than may be reflected in this database. Users are encouraged to confirm program locations on the OASAS website (link above). |


### NYS Office of Children and Family Services (NYSOCFS)

| | |
| -- | -- |
| Dataset Name: | [Facilities](https://ocfs.ny.gov/main/regionaloffices_main.asp) |
| Last Updated: | 7/1/2016 |


### NYS Office of Mental Health (NYSOMH)

| | |
| -- | -- |
| Dataset Name: | [Local Mental Health Programs](https://data.ny.gov/Human-Services/Local-Mental-Health-Programs/6nvr-tbv8) |
| Last Updated: | 10/24/2018 |


### NYS Office of Parks, Recreation and Historic Preservation (NYSOPRHP)

| | |
| -- | -- |
| Dataset Name: | [National Register of Historic Places](https://data.ny.gov/Recreation/tiol-Register-of-Historic-Places/iisn-hnyv) |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name: | [State Park Facility Points](https://data.ny.gov/Recreation/State-Park-Facility-Points/9uuk-x7vh) |
| Last Updated: | 10/24/2018 |


### NYS Unified Court System (NYCOURTS)

| | |
| -- | -- |
| Dataset Name: | [The Courts](http://www.nycourts.gov/courts/index.shtml) |
| Last Updated: | 7/1/2016 |


### National Park Service (USNPS)

| | |
| -- | -- |
| Dataset Name: | [Administrative Boundaries of National Park System Units](https://irma.nps.gov/DataStore/Reference/Profile/2225713) |
| Last Updated: | 10/24/2018 |


### New York City Housing Authority (NYCHA)

| | |
| -- | -- |
| Dataset Name: | [NYCHA PSA (Police Service Areas)](https://data.cityofnewyork.us/Housing-Development/NYCHA-PSA-Police-Service-Areas-/72wx-vdjr) |
| Last Updated: | 10/24/2018 |


### Port Authority of New York and New Jersey (PANYNJ)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database |
| Last Updated: | 10/24/2018 |


### Roosevelt Island Operating Corporation (RIOC)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database |
| Last Updated: | 10/24/2018 |


### Trust for Governors Island (TGI)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database |
| Last Updated: | 10/24/2018 |


### US Courts (ESCORTS)

| | |
| -- | -- |
| Dataset Name: | [Court Locator Results](http://www.uscourts.gov/court-locator/city/New%20York/state/NY) |
| Last Updated: | 7/1/2016 |


### US Department of Transportation (USDOT)

| | |
| -- | -- |
| Dataset Name: | [U.S. Army Corps of Engineers Ports](http://osav-usdot.opendata.arcgis.com) |
| Last Updated: | 10/24/2018 |


| | |
| -- | -- |
| Dataset Name: | [Airports](http://osav-usdot.opendata.arcgis.com) |
| Last Updated: | 10/24/2018 |


### Amtrak (Amtrak)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database |
| Last Updated: | 10/24/2018 |


### Brooklyn Bridge Park Corporation (BBPC)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database|
| Last Updated: | 10/24/2018 |


### Federal Bureau of Prisons (FBOP)

| | |
| -- | -- |
| Dataset Name: | [Our Locations](https://www.bop.gov/locations/map.jsp#) |
| Last Updated: | 7/1/2016 |


### Food Bank of NYC (FBNYC)

| | |
| -- | -- |
| Dataset Name:  | FBNYC Food Pantry Soup Kitchen List 8-5-16 |
| Last Updated: | 8/5/2016 |


### Hudson River Park Trust (HRPT)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database |
| Last Updated: | 10/24/2018 |


### Metropolitan Transportation Authority (MTA)

| | |
| -- | -- |
| Dataset Name: | Selected Facilities and Program Sites Database |
| Last Updated: | 10/24/2018 |

## VII. API Instructions

The FacDB data that powers the [NYC Facilities Explorer](https://capitalplanning.nyc.gov/facilities) is hosted on Carto. Carto's API uses SQL syntax for accessing and querying data tables. The documentation for their API is [available here](https://carto.com/docs/carto-engine/sql-api/making-calls). Please refer to the [Data Dictionary](http://docs.capitalplanning.nyc/facdb/#v-data-dictionary) for the field names in the `facdb_facilities` table.