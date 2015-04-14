# Open Address Data

### Summary  

This data is every standardized address and related coordinates contained in the City of Philadelphia's Unified Land Record System (ULRS).
  
Features updated:    04/14/2015  
Attributes updated:  04/14/2015  
Metadata updated:  05/18/2014  
Update frequency:   This process will be scripted to update the data automatically every week on schedule with the ULRS.

### Description  


DATA DEVELOPMENT: This data is created from the ULRS PARCEL_ADDRESS table that contains a row of every standardized address in the system and is linked to a parcel. Each row also contains coordinates in NAD_1983_StatePlane_Pennsylvania_South_FIPS_3702_Feet (2272). The uploaded data is exported from the table after a running a SQL query against the layer to make sure none of the following fields are NULL; street_number, street_name, street_type, x_coord, and y_coord.

```sql
select DISTINCT (to_char(street_number) || NVL2(to_char(street_number_suffix),' ' || to_char(street_number_suffix), '')) "NUMBER", (NVL2(street_prefix,street_prefix || ' ','') || street_name || ' ' || street_type || NVL2(street_suffix,' ' || street_suffix, '')) STREET, to_char(UNIT), x_coord LON, y_coord LAT from parcel_address
where x_coord is not null and y_coord is not null and street_number is not null and street_name is not null and street_type is not null
```

This exported csv is loaded into ArcMap and then exported using the City of Philadelphia's [arc-open](https://github.com/CityOfPhiladelphia/arc-open/) toolbox which exports a shapefile, csv, and geojson file of the data in WGS 84.


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

