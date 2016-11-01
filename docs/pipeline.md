# Residential Pipeline
The Residential Pipeline is a data product produced by the New York City (NYC) Department of City Planning (DCP) Capital Planning division. It aims to help City agencies understand the distribution of residential development across time and space, in order to support both capital and operational planning. 

The underlying database integrates administrative City data on both new construction and building alterations. Currently, it integrates permits and Certificates of Occupancy (CofOs) from the NYC Department of Buildings (DOB), as well as data on affordable housing projects from Housing Preservation and Development (HPD). Going forward, it will encompass new data from these sources, data gathered from DCP’s land use approval process (ULURP), and other sources if / as identified.

In the coming months, we will pair this product with a Non-Residential Pipeline that provides similar information regarding other types of development (commercial, manufacturing, recreational, etc.). Together, these products will form a comprehensive Development Pipeline. The remainder of this document will focus on the Residential Pipeline, but we welcome users' thoughts on if/how this methodology can be adapted for Non-Residential purposes.    

We are constantly seeking feedback on how to improve and make this data resource most valuable.  Please reach out to the NYC Planning Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions or comments.

## General information
| Overview |  |
| :-- | :-- |
| Name | "Residential Pipeline" |
| Description | The Residential Pipeline integrates administrative City data on both new construction and building alterations. Under current methodology, DOB permits are the core dataset around which database is built. Permits are matched with DOB CofOs to determine completion; then, HPD data is then appended (where available) to provide information on the number on City-subsidized, affordable units in each development.  |
| Format | Webmap, GeoJSON, Shapefile, CSV |
| Projection | WGS84 |
| Last updated | 10/31/16 |

### Limitations & disclaimers
There are a number of known limitations to this dataset and improvements will be made on a continual basis, based on internal reviews and user feedback. 

#### Geocoding and geospatial integration
* ~95% of DOB permits successfully geocoded using Borough-Block-Lot (BBL), DOB Building Identification number (BIN) and address 
* ~90% of HPD projects successfully matched with permit record, using BBL. We assume that all HPD projects should have a corresponding DOB permit and failure to find a matching BBL in each dataset indicates errors in BBLs. HPD projects without a match in DOB data are thus excluded, as we can assume the permit is included but with the correct BBL.  

#### Expired permits
DOB data includes permit filings from 2010 through present. Some “outstanding” permits (those without Certificate of Occupancy) may have since expired, however, this is not available in current datasets. Going forward, we will seek to identify and exclude expired permits.

#### Exclusions
The user-ready version of this dataset excludes likely duplicates and projects with no change in units, as determined by DCP.
* Duplicates: in some cases, it appeared that multiple permits were generated for a single development. For example, this could occur if an initial permit had administrative errors that were corrected by issuing a new permit. Since the data does not include permit expiration date (per above), we cannot determine if/which permits are outdated. To avoid double-counting, we identified  likely duplicates using the Building Identification Number (BIN) listed in the DOB permit. We have only retained the most recent instance of a given BIN in the database.
* Projects without change: In some cases, alteration permits are required for administrative reasons rather than actual construction. To prevent such permits from skewing analyses, we have excluded any alteration permits that are missing data about existing and/or projected number of units. 

#### Other data sources
For some analyses, it may be appropriate to include likely developments that have not yet received permits (e.g., projects where DCP has approved a land use change, or permits that have been filed but not approved). Due to the uncertainty of such developments, they are not included in this version. 

## Methodology, key terms and data dictionary
This section provides a visual overview of how input datasets are processed and integrated. A glossary of "key terms" accompanies this overview, and is intended to aid casual users in understanding the most important concepts.

In addition, there is a "Full data dictionary" which defines every field in the database. This is intended for users seeking a more detailed understanding of the data, particularly those who intend to use it for analyses. 
  
### Methodology
![Image of methodology] (https://raw.githubusercontent.com/NYCPlanning/cpdocs/master/docs/residentialpipeline_methodology_1031.png)
### Key terms ![Image of key terms glossary] (https://raw.githubusercontent.com/NYCPlanning/cpdocs/98ccb494a3501a29a7cdc83a1fedbb26753c9894/docs/residentialpipeline_methodology_glossary_1031.png)

### Full data dictionary
| Source | Field name  | Description | Name in source, if difference |
| :--------- | :---- | :-- | :-- |
|DCP | cartodb_id | Unique identifier generated by mapping software | n/a|
|DCP | the_geom | Point location generated by DCP geocoding | n/a|
|DCP | address | Address generated through DCP geocoding [TBD] | n/a|
|DCP | dcp_pipeline_category | Field created by DCP to capture record type (Residential new; Residentail renovation; Hotel new; Hotel renovation)  | n/a|
|DCP | dcp_pipeline_status | Field created by DCP to capture statuses assigned by DCp. Complete: most recent CofO lists >80% of permit proposed units. Partial complete: most recent CofO lists <80% of permit proposed units. Permit outstanding: first permit issued but no CofOs issued. Permit pending: permit application complete but first permit not issued | n/a|
|DCP | dcp_pipeline_units | Field created by DCP to determine point size for mapping. If status is Complete, set to Complete incremental units. Otherwise, set to HPD units or Permit incremental units (if HPD n/a) | n/a|
|DCP/DOB | permit_incremental_units | Calculated increment between existing and proposed units listed in permit | n/a|
|DCP/DOB | cofo_incremental_units | Calculated increment between existing units (listed in permit) and completed units (listed in CofOs) | n/a|
|DCP/DOB | complete_incremental_units | Field created by DCP to capture completed incremental units (i.e. CofO incremental units w/ adjustments as needed)  | n/a
|DCP/DOB | outstanding_incremental_units | Field created by DCP to capture incremental units where permit issued but no CofO issued OR CofO lists <80% of permit units | n/a |
|DCP/DOB | permit_pending_incremental_units | Field created by DCP to capture incremental units where permit application is complete but first permit has not been issued | n/a|
|DOB | dob_jobnumber | Unique identifier listed in both permits and CofO data | n/a|
|DOB | dob_jobtype | Construction type listed in permits data: new building (NB) vs. major alteration (A1) | n/a|
|DOB | dob_exist_occupancy | Existing occupancy type listed in initial permit application e.g., single vs. mutli-family dwelling | ex-occ|
|DOB | dob_prop_occupancy | Proposed occupancy type listed in initial permit application e.g., single vs. mutli-family dwelling | pr-occ|
|DOB | dob_exist_units | Existing number of dwelling units listed in initial permit application  | ex-dwell-units|
|DOB | dob_prop_units | Proposed number of dwelling units listed in initial permit application | pr-dwell-units|
|DOB | dob_status | Most recent permit status, listed in DOB permit data [Add status descriptions] | current job status |
|DOB | dob_status_date | Date of most recent status update of job/work listed in permit data | current job status  |
|DOB | dob_bbl | BBL concatenated from fields in permits data | boro, block, lot  |
|DOB | cofo_units | Number of units listed in most recent DOB CofO | # of residential units  |
|DCP/HPD | hpd_dcp_adjust | Flags records that are aggregation of 2 HPD projects at same BBL | n/a
|HPD | hpd_total_units | Total number of units listed in HPD data, incl. supported-affordable and market-rate  | Total Units (Total Start Units for projects 2010-2013)  |
|HPD | hpd_project_id | Unique identifier generated by HPD   | Project ID  |
|HPD | hpd_project_name | Unique project name generated by HPD | Project Name |
|HPD | hpd_project_start_date | Official start date listed in HPD data (i.e., date financing is closed) | Project Start Date |
|HPD | hpd_address | Concatenation of house number and street name listed in HPD data | House Number, Street Name |
|HPD | hpd_bbl | BBL listed in HPD data | BBL |
|HPD | Hpd_building_id | Unique building identifier gereated by HPD | Building ID |
|HPD | hpd_units_supported_low_income:0-30%ami  | Number of HPD-supported units for households earning 0-30% of Area Median Income (AMI); Note, n/a for projects 2010-2013 | Extremely Low Income Units (0-30% AMI)  |
|HPD | hpd_units_supported_low_income:31-50%ami | Number of HPD-supported units for households earning 31-50% of Area Median Income (AMI); Note: n/a for projects 2010-2013 | Very Low Income Units (31-50% AMI) |
| HPD | hpd_units_supported_low_income:51-80%ami | Number of HPD-supported units for households earning 51-80% of Area Median Income (AMI); Note: n/a for projects 2010-2013 | Low Income Units (51-80% AMI)|
|DCP/HPD | hpd_units_supported_low_income_total:0-80%ami | Total number of HPD-supported units for households earning 0-80% of Area Median Income (AMI); Note: field does not appear in data for projects 2014 but is calculated by DCP from prior 3 fields | Low Income (0 - 80% AMI)|
|HPD | hpd_units_supported_moderate_income:81-120%ami | Number of HPD-supported units for households earning 81-120% of Area Median Income (AMI) | Moderate Income Units (81-120% AMI)|
|HPD | hpd_units_supported_middle_income:121-165_ami(180%pre-2014) | Number of HPD-supported units for households earning 121-165% of Area Median Income (AMI); Note: upper bound is 180% for projects 2010-2013 | Middle Income Units (121-165/180% AMI)|
|HPD | hpd_units_supported_superintendent | Number of HPD-supported units dedicated for superintendents; Note: n/a for projects 2010-2013 | Other Units (165%+ AMI)|
|DCP/HPD | hpd_units_supported_total | Total number of HPD-supported units across income levels, including superintendent units; Note: field does not appear in data for projects 2010-2013 but is calculated by DCP from prior 3 fields | Counted Units|
|HPD | hpd_units_supported_seniors | Number of HPD-supported units for seniors (as subset of total supported units) | Senior Units|
|HPD | hpd_file | Name of HPD data file where project is listed | n/a|


## Sources detail
| Input | Source file name  | Description | Last update | File format |
| :--------- | :---- | :-- | :-- | :-- |
DOB Permits | [TBD] | DOB database of all permits, updated with most recent status |  [TBD] |  [TBD] |
DOB Certificates of Occupancy | COs and TCOs Issued (2010-2016) (8-24-16) | All final and temporary Certificates of Occupancy issued since 2010 | 8/25/2016 | Microsoft Excel, prepared for DCP by DOB |
HPD Projects | NHMP 2010-2013; HNY 2014-2016 | HPD records for New Construction projects; | 5/20/2016 | Microsoft Excel, 2010-13 data provided to DCP; data since 2014 to be shared quarterly via Open Data |

## Feedback
We are constantly seeking feedback on how to improve and make this data resource most valuable.  Please reach out to the NYC Planning Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions or comments.
