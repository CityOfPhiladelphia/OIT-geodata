Metadata

Data Creation
This data is created from the City of Philadelphia's Unified Land Record System (ULRS). The PARCEL_ADDRESS table in the ULRS system contains a row of every standardized address in the system that is linked to a parcel. Each row also contains coordinates in NAD_1983_StatePlane_Pennsylvania_South_FIPS_3702_Feet (2272). The uploaded data is exported after a running a SQL query against the layer to kae sure none of the following felds are NULL; street_number, street)name, street_type, x_coord, and y_coord.

This exported csv is loaded into ArcMap and then exported using the City of Philadelphia's Arc2Open toolbox which exports a shapefile, csv, and geojson file of the data in WGS 84.
