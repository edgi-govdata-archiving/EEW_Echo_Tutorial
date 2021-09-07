# Database Schema
This is a user-friendly overview of the database we have copied at Stony Brook University. It includes both spatial data (e.g. watershed boundaries) and attribute data (e.g. EPA records of Clean Water Act violations)

# Spatial Data
* "eco_level3"
  * Ecoregions (Level 3)
  * Untested, but this should be similar: https://edg.epa.gov/metadata/rest/document?id=%7B02C99043-2E25-4A4E-BBE3-6AAE81ED7FC8%7D&xsl=metadata_to_html_full
  * "US_L3NAME" = key ID e.g. Atlantic Coastal Pine Barrens
* "epa_regions"
  * EPA regions
  * Untested, but this should be similar: https://edg.epa.gov/metadata/rest/document?id=%7B03DF9C40-D75B-48AE-BF59-C2188CED8C45%7D&xsl=metadata_to_html_full
  * "eparegion" = key ID. In the form of "Region 1", "Region 2", up to "Region 10"
* "tl_2019_us_cd116"
  * Congressional Districts
  * Untested, but see: https://catalog.data.gov/dataset/tiger-line-shapefile-2019-nation-u-s-116th-congressional-district-national
  * "GEOID" = key ID. This is the combination of the state id and the CD e.g. AR-2 = 0502
* "tl_2019_us_county"
  * Counties
  * Untested, but see: https://catalog.data.gov/dataset/tiger-line-shapefile-2019-nation-u-s-current-county-and-equivalent-national-shapefile
  * "GEOID" = key ID. It is a four or five digit code corresponding to the two digit state number (e.g. 55) and 2-3 digit county code! 
* "tl_2019_us_state"
  * States
  * Untested, but see: https://catalog.data.gov/dataset/tiger-line-shapefile-2019-nation-u-s-current-state-and-equivalent-national
  * "STUSPS" = key ID e.g. MS, IA, AK
* "tl_2019_us_zcta510" 
  * 5-Digit Zip Codes
  * See: https://catalog.data.gov/dataset/tiger-line-shapefile-2019-2010-nation-u-s-2010-census-5-digit-zip-code-tabulation-area-zcta5-na
  * "zcta5ce10" = key ID e.g. 52358
* "wbdhu8"
  * HUC8 watersheds
  * "huc8" = key ID
  * See: https://www.arcgis.com/sharing/rest/content/items/a36d2b4aaa6e4aab818247fdd0b3f5a4/info/metadata/metadata.xml?format=default&output=html  
* "wbdhu10"
  * HUC10 watersheds
  * "huc10" = key ID 
  * See: https://www.arcgis.com/sharing/rest/content/items/a36d2b4aaa6e4aab818247fdd0b3f5a4/info/metadata/metadata.xml?format=default&output=html
* "wbdhu12"
  * HUC12 watersheds
  * "huc12" = key ID
  * See: https://www.arcgis.com/sharing/rest/content/items/a36d2b4aaa6e4aab818247fdd0b3f5a4/info/metadata/metadata.xml?format=default&output=html 

# Attribute Data
* "ECHO_EXPORTER" 
  * A full description of the fields in the ECHO_EXPORTER table can be found at: https://echo.epa.gov/system/files/echo_exporter_columns_07242019.xlsx Here we name some of the ones we have used:
  * "FAC_NAME" = common name of the facility recorded by EPA e.g. EXXON BATON ROUGE
  * etc......

## More details on program data available in the ECHO database...
**Inspections** or **evaluations** are usually the first phase in the enforcement pipeline, how many (but not all) violations are discovered. **Violations** happen when a facilty is found to be out of compliance with an environmental law, often by violating the terms of its permit issued under that law. **Enforcement actions** happen when the regulating agency decides to initiate a "case" against a firm for its violation of an environmental law, either by considering some administrative penalty such as a fine or by taking the violator to court. 

What's available for you to look at here:

https://github.com/edgi-govdata-archiving/ECHO-Oil-Gas/blob/main/slim_echoepa_a_schema.sql

Tables on **Hazardous and Other Waste**:
- RCRA_EVALUATIONS = Inspections under RCRA
- RCRA_VIOLATIONS = Violations of RCRA rules
- RCRA_ENFORCEMENTS = Enforcement actions taken by state agencies and the EPA

Here's where you can find definitions of terms used in the columns of RCRA data: 
https://echo.epa.gov/tools/data-downloads/rcrainfo-download-summary 

Tables on **Air**:
- ICIS-AIR_VIOLATION_HISTORY = CAA violations
- ICIS-AIR_FCES_PCES = Both state and federal CAA compliance evaluations
- ICIS-AIR_FORMAL_ACTIONS = CAA formal enforcement actions

Here's where you can find definitions of terms used in the columns of Clean Air Act data: 
https://echo.epa.gov/tools/data-downloads/icis-air-download-summary

Tables on **Air Emissions** (Combined air emissions data for stationary sources from four EPA air programs: National Emissions Inventory (NEI), Greenhouse Gas Reporting Program (GHGRP), Toxic Release Inventory (TRI), and Clean Air Markets (CAMD)):
- Greenhouse Gases via POLL_RPT_COMBINED_EMISSIONS
- Toxic Releases via POLL_RPT_COMBINED_EMISSIONS

Here's where you can find definitions of terms used in the columns of this data: https://echo.epa.gov/tools/data-downloads/air-emissions-download-summary

Tables on **Water** (National Pollutant Discharge Elimination System, or NPDES):
- NPDES_QNCR_HISTORY = CWA Quarterly Non-Compliance History
- NPDES_INSPECTIONS = CWA Inspections
- NPDES_FORMAL_ENFORCEMENT_ACTIONS = CWA Enforcements

Here's where you can find definitions of terms used in the columns of Clean Water Act data: https://echo.epa.gov/tools/data-downloads/icis-npdes-download-summary

Tables on **Drinking Water** (Safe Drinking Water Act, or SDWA):
- SDWA_PUB_WATER_SYSTEMS = Public Water Systems under Safe Drinking Water Act
- SDWA_SITE_VISITS = Safe Drinking Water Site Visits
- SDWA_VIOLATIONS = Safe Drinking Water Violations
- SDWA_SERIOUS_VIOLATORS = Safe Drinking Water Serious Violators
- SDWA_ENFORCEMENTS = Safe Drinking Water Enforcements
- SDWA_RETURN_TO_COMPLIANCE = Safe Drinking Water Return to Compliance

Here's where you can find definitions of terms used in the columns of Clean Water Act data: https://echo.epa.gov/tools/data-downloads/sdwa-download-summary
