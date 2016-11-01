# Residential Pipeline
The Development Pipeline aims to help New York City planners understand changes resulting from building activity, across both time and space. It is currently comprised of data from the Department of Buildings (DOB) and the Department of Housing Preservation and Development (HPD), and includes the most comprehensive picture of new residential development taking place across the five boroughs. DCP will be working over the months to come to add other, non-residential developments to this pipeline, and to integrate other data sources.

This product include recently-completed residential development activity (last 5+ years), as well data on developments that are at various stages in the permitting process.  Completed or “partially complete” projects have received Certificates of Occupancy for at least a portion of their permitted units. Permitted sites are those that have received building permits; although not all of these sites will necessarily be built and completed over the next few years, this category is the City’s best predictor of where new housing will be built in the near future. Sites identified in the “permit pending” category demonstrate where developers have completed applications for new building (NB) permits or major alterations (A1) permits that will change the number of residential units in a building; these sites may give a general direction of where developers are seeking to deliver new housing units, but since they have not yet received permits, the certainty of their development cannot be assured.  In addition to the information derived from permits and Certificates of Occupancy, some records are appended with HPD data regarding the number of affordable housing units.

Special thanks goes to the NYC Department of Buildings and the Department of Housing Preservation and Development who make their data available for this map. 

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
~ 95% DOB permits were successfully geocoding using BBL or address. Geocoding ‘rejects’ were researched by DCP but not every site could be verified. 

~75% of HPD records were matched with their corresponding DOB permit using the BBL listed in each dataset. We assume that all HPD projects should have a corresponding DOB permit, and manual research confirms that most un-matched HPD projects list an outdated BBL. Going forward, DCP will work with HPD to improve and integrate this data.   

#### Expired permits
These data include permit filings from 2010 through Q3 2016. Some “outstanding” permits (those without Certificate of Occupancy) may have since expired, however, this information not available in current datasets. Going forward, we will seek to identify and exclude expired permits.

#### Exclusions
The database excludes likely duplicates and projects with no change in units, as determined by DCP.

Duplicates: in some cases, it appeared that multiple permits were generated for a single development. For example, this could occur if an initial permit had administrative errors that were corrected by issuing a new permit. Since the data does not include permit expiration date (per above), we cannot determine if/which permits are outdated. To avoid double-counting, we identified  likely duplicates using the Building Identification Number (BIN) listed in the DOB permit. We have only retained the most recent instance of a given BIN in the database.

No change in units: In some cases, alteration permits are required for administrative reasons rather than actual construction. To prevent such permits from skewing analyses, we have excluded any alteration permits that are missing data about existing and/or projected number of units. 

#### Other data sources
For some analyses, it may be appropriate to include likely developments that have not yet received permits (e.g., projects where DCP has approved a land use change, or permits that have been filed but not approved). Due to the uncertainty of such developments, they are not included in this version of the Residential Pipeline.

## Methodology, key terms and data dictionary
This section provides a visual overview of how input datasets are processed and integrated. A glossary of "key terms" accompanies this overview, and is intended to aid casual users in understanding the most important concepts.

In addition, there is a "Full data dictionary" which defines every field in the database. This is intended for users seeking a more detailed understanding of the data, particularly those who intend to use it for analyses. 
  
### Methodology
![Image of methodology] (https://raw.githubusercontent.com/NYCPlanning/cpdocs/a0482d03d8e133cd7e23a4d4619613fe3e90c63c/docs/pipeline_methodology_diagram.jpg)
### Key terms ![Image of key terms glossary] (https://raw.githubusercontent.com/NYCPlanning/cpdocs/master/docs/pipeline_methodology_terms.jpg)

### Full data dictionary
| Source | Field name  | Field description and uses | Source name, if differs |
| :--------- | :---- | :-- | :-- |
|DCP | cartodb id | Unique identifier generated by mapping software | |
|DCP | the geom | Point location generated by DCP geocoding | |
|DCP | dcp pipeline category | Field created by DCP to capture record type (Residential new; Residentail renovation; Hotel new; Hotel renovation)  | |
|DCP | dcp pipeline status | Field created by DCP to capture statuses assigned by DCP. Complete: most recent CofO lists >80% of permit proposed units. Partial complete: most recent CofO lists <80% of permit proposed units. Permit outstanding: first permit issued but no CofOs issued. Permit pending: permit application complete but first permit not issued | |
|DCP | dcp units complete | Field created by DCP to capture incremental units completed, after all processing | |
|DCP | dcp units outstanding | Field created by DCP to capture incremental units outstanding, after all processing | |
|DCP | dcp units pending | Field created by DCP to capture incremental units pending permit issuance, after all processing | |
|DCP/DOB | dob cofo date first | Field created by DCP to capture date of earliest CofO issued since 2010 | Date Issued |
|DCP/DOB | dob cofo date last | Field created by DCP to capture date of most recent CofO issued since 2010 | Date Issued |
|DCP/DOB | dob cofo increm units | Set of fields created by DCP to capture incremental units completed in each year since 2011. In addition, there is a field to capture incremental units pre-2011 and a field to capture total incremental units completed. | |
|DOB | dob cofo type last | Specificies most recent CofO type (Temporary or Final) | CertificateType |
|DOB | dob job number | Unique identifier listed in both permits and CofO data | Job Number or Job# |
|DOB | dob permit address | Concatenation of house number and street name listed in permit data | Job Location House Number; Job Location Street Name |
|DOB | dob permit bbl | Concatenation of borough code, block number and lot number listed in permit data | Borough Digit, Block, Lot |
|DOB | dob permit bin | Building ID number listed in permit data | BIN number |
|DOB | dob permit  exist occupancy | Existing occupancy type listed in initial permit application e.g., single vs. mutli-family dwelling | ex-occ|
|DOB | dob permit exist units | Existing number of dwelling units listed in initial permit application  | ex-dwell-units|
|DCP/DOB | dob permit incremental units | Calculated different between existing and proposed units listed in permit | |
|DOB | dob permit job type | Construction type listed in permits data: new building (NB) vs. major alteration (A1) | |
|DOB | dob proposed occupancy | Proposed occupancy type listed in initial permit application e.g., single vs. mutli-family dwelling | pr-occ|
|DOB | dob permit proposed units | Proposed number of dwelling units listed in initial permit application | pr-dwell-units|
|DOB | dob permit status | Most recent permit status, listed in DOB permit data | Current Job Status Doc 01 |
|DCP/DOB | dob permit status decode | Translates DOB status code to either Permitted (status codes Q, R, X) or Permit pending (status codes (D, E, F, G, H, I, J, K, L, M, P) |  |
|DOB | dob permit status update | Date of most recent status update of job/work listed in permit data | Job Status Date Doc 01 |
|DOB | dob bbl | BBL concatenated from fields in permits data | boro, block, lot  |
|DOB | cofo units | Number of units listed in most recent DOB CofO | # of residential units  |
|HPD | hpd address | Concatenation of house number and street name listed in HPD data | House Number, Street Name |
|HPD | hpd bbl | BBL listed in HPD data |  |
|HPD | Hpd building id | Unique building identifier gereated by HPD |  |
|DCP/HPD | hpd dcp adjust | Flags records that are aggregation of multiple HPD projects at same BBL |  |
|HPD | hpd file | Name of HPD data file from which data was obtained | |
|HPD | hpd project id | Unique identifier generated by HPD   | |
|HPD | hpd project name | Unique project name generated by HPD | |
|HPD | hpd project start date | Official start date listed in HPD data (i.e., date financing is closed) | |
|HPD | hpd units supported low income 0 30 ami  | Number of HPD-supported units for households earning 0-30% of Area Median Income (AMI); Note,  for projects 2010-2013 | Extremely Low Income Units (0-30% AMI)  |
|HPD | hpd units supported low income 31 50 ami | Number of HPD-supported units for households earning 31-50% of Area Median Income (AMI); Note:  for projects 2010-2013 | Very Low Income Units (31-50% AMI) |
| HPD | hpd units supported low income 51 80 ami | Number of HPD-supported units for households earning 51-80% of Area Median Income (AMI); Note:  for projects 2010-2013 | Low Income Units (51-80% AMI)|
|DCP/HPD | hpd units supported low income total 0 80 ami | Total number of HPD-supported units for households earning 0-80% of Area Median Income (AMI); Note: field does not appear in data for projects 2014 but is calculated by DCP from prior 3 fields | Low Income (0 - 80% AMI)|
|HPD | hpd units supported moderate income 81 120 ami | Number of HPD-supported units for households earning 81-120% of Area Median Income (AMI) | Moderate Income Units (81-120% AMI)|
|HPD | hpd units supported middle income 121 165 ami 180 pre 2014 | Number of HPD-supported units for households earning 121-165% of Area Median Income (AMI); Note: upper bound is 180% for projects 2010-2013 | Middle Income Units (121-165/180% AMI)|
|HPD | hpd units supported seniors | Number of HPD-supported units for seniors (as subset of total supported units) | Senior Units|
|HPD | hpd units supported superintendent | Number of HPD-supported units dedicated for superintendents; Note:  for projects 2010-2013 | Other Units (165%+ AMI)|
|DCP/HPD | hpd units supported total | Total number of HPD-supported units across income levels, including superintendent units; Note: field does not appear in data for projects 2010-2013 but is calculated by DCP from prior 3 fields | Counted Units|
|HPD | hpd units total | Total number of units listed in HPD data, incl. supported-affordable and market-rate  | Total Units (Total Start Units for projects 2010-2013)  |

## Sources detail
| Input | Source file name  | Description | Last update | File format |
| :--------- | :---- | :-- | :-- | :-- |
DOB Permits | DOB Doc 01 database| DOB database of ‘Doc 01’s, lead/initial document in permit file |  10/28/16 |  Microsoft Excel; provided to DCP via email |
DOB Certificates of Occupancy | COs and TCOs Issued (2010-2016) | All final and temporary Certificates of Occupancy issued since 2010 | 9/30/16 | Microsoft Excel; provided to DCP via email |
HPD Projects | NHMP 2010-2013; HNY 2014-2016 | HPD records for New Construction projects (where financing has closed) | 10/11/2016 | Microsoft Excel; 2010-13 data provided to DCP via email, data since 2014 to be shared quarterly via Open Data |

## Feedback
We are constantly seeking feedback on how to improve and make this data resource most valuable.  Please reach out to the NYC Planning Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions or comments.
