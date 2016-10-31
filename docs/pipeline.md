# Residential Pipeline
The Residential Pipeline is a data product produced by the New York City (NYC) Department of City Planning (DCP) Capital Planning division. It aims to help City agencies understand the distribution of residential development across time and space, in order to support both capital and operational planning. 

The underlying database integrates administrative City data on both new construction and building alterations. Currently, it integrates permits and Certificates of Occupancy (CofOs) from the NYC Department of Buildings (DOB), as well as data on affordable housing projects from Housing Preservation and Development (HPD). Going forward, it will encompass new data from these sources, data gathered from DCP’s land use approval process (ULURP), and other sources if / as identified.

In the coming months, we will pair this product with a Non-Residential Pipeline that provides similar information regarding other types of development (commercial, manufacturing, recreational, etc.). Together, these products will form a comprehensive Development Pipeline. The remainder of this document will focus on the Residential Pipeline, but we welcome users' thoughts on if/how this methodology can be adapted for Non-Residential puroposes.    

We are constantly seeking feedback on how to improve and make this data resource most valuable.  Please reach out to the NYC Planning Capital Planning team at [Capital@planning.nyc.gov](mailto:Capital@planning.nyc.gov) with any suggestions or comments.

## General information
| Overview |  |
| :-- | :-- |
| Name | "Residential Pipeline" |
| Description | The Residential Pipeline integrates administrative City data on both new construction and building alterations. Currently, it integrates permits and Certificates of Occupancy (CofOs) from the NYC Department of Buildings (DOB), as well as data on affordable housing projects from Housing Preservation and Development (HPD) |
| Format | Webmap, GeoJSON, Shapefile, CSV |
| Projection | WGS84 |
| Last updated | 10/31/16 |

## Limitations & disclaimers
There are a number of known limitations to this dataset and improvements will be made on a continual basis, based on internal reviews and user feedback. 

### Geocoding and geospatial integration
* ~99% of DOB permits successfully geocoded using Borough-Block-Lot (BBL), DOB Building Identification number (BIN) and address 
* ~90% of HPD projects successfully matched with permit using BBL
* ~90% of geocoded HPD projects successfully matched with BBL permit counterpart

### Exclusions
The user-ready version of this dataset excludes likely duplicates and projects with no change in units, as determined by DCP.
* Duplicates: in some cases, it appeared that multiple permits were generated for a single development. To avoid double-counting, we identified duplicates using the Building Identification Number (BIN) listed in the DOB permit. We have only retained the most recent instance of a given BIN in the database.
* Projects without change: for some renovations, permits are missing data about existing and/or projected number of units. These have been excluded to avoid skewing analyses. We have also excluded any renovations where the permit description included “No Work”, as these are most likely administrative changes rather than actual construction. [TBD]

### Expired permits
DOB data includes permit filings from 2010 through present. Some “outstanding” permits (those without Certificate of Occupancy) may have since expired, however, this is not available in current datasets. Going forward, we will seek to identify and exclude expired permits.

### Other data sources
For some analyses, it may be appropriate to include likely developments that have not yet received permits (e.g., projects where DCP has approved a land use change, or permits that have been filed but not approved). Due to the uncertainty of such developments, they are not included in this version. 

## Methodology & glossary
![Image of methodology] (G:\13. Community Facilities Planning\4. Housing pipeline\Methodology\residentialpipeline_methodology_1031)

