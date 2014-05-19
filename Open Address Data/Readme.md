# Open Address Data

### Summary  

This is one of the planimetric coverages developed as part of the aerial survey project of 1996 and updated using new aerial photography collected between 25 March 2004 and 23 April 2004.  
  
Features updated:    05/16/2014  
Attributes updated:  05/16/2014  
Metadata updated:  05/18/2014  
Update frequency:   As Needed

### Description  

This data is every standardized address and related coordinates.

DATA DEVELOPMENT: This data is created from the City of Philadelphia's Unified Land Record System (ULRS).  The PARCEL_ADDRESS table in the ULRS system contains a row of every standardized address in the system that is linked to a parcel. Each row also contains coordinates in NAD_1983_StatePlane_Pennsylvania_South_FIPS_3702_Feet (2272). The uploaded data is exported after a running a SQL query against the layer to kae sure none of the following felds are NULL; street_number, street)name, street_type, x_coord, and y_coord.

This exported csv is loaded into ArcMap and then exported using the City of Philadelphia's Arc2Open toolbox which exports a shapefile, csv, and geojson file of the data in WGS 84.


COORDINATE SYSTEM: GCS_WGS_1984, WKID: 4326, Decimal Degrees.

THEMATIC MAPPING: Use the LAT and LON fields for thematic mapping and the NUMBER and STREET fields for labeling.  

### Data Dictionary

| Field | Description  
| ----- | :----------:    
| NUMBER | The Street Number
| STREET | A concatenation of the Street_Name and Street_Type fields
| LAT | The Latitude coordinate of the address
| LON | The Longitude coordinate of the address

### Credits  

Brian Ivey  
Office of Innovation & Technology  
GIS Services Group  
1234 Market St., 15th Floor, Philadelphia, PA  19107  
215-686-8287

### Use Limitations  

The City of Philadelphia makes no representation about the accuracy of any specific information in this GIS data and is provided as is and without Warranty of any kind. Boundaries are self-reported. The user of this data will assume complete responsibility for any and all occurrences resulting from its use or display and will hold the City of Philadelphia harmless from any and all claims, demands, liabilities, obligations, damages, suits, judgments or settlements, including reasonable costs and attorneys' fees, that arise from use of this data.

