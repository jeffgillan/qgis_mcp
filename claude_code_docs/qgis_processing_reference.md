# QGIS Processing Algorithms Reference
Generated: 2026-01-17 20:12:59
Auto-generated from QGIS installation for use with Claude Code

## Table of Contents

- [QGIS (3D)](#3d) (1 algorithms)
- [GDAL](#gdal) (56 algorithms)
- [GRASS](#grass) (307 algorithms)
- [QGIS (native c++)](#native) (271 algorithms)
- [QGIS](#qgis) (50 algorithms)

**Total Algorithms: 685**

---

## QGIS (3D)

Provider ID: `3d`
Total algorithms: 1

### 3d:tessellate

**Display Name:** Tessellate

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Tessellated

---

## GDAL

Provider ID: `gdal`
Total algorithms: 56

### gdal:aspect

**Display Name:** Aspect

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `TRIG_ANGLE` (boolean, required, default: `False`): Return trigonometric angle instead of azimuth
- `ZERO_FLAT` (boolean, required, default: `False`): Return 0 for flat instead of -9999
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `ZEVENBERGEN` (boolean, required, default: `False`): Use Zevenbergen&Thorne formula instead of the Horn's one
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Aspect

---

### gdal:assignprojection

**Display Name:** Assign projection

**Group:** Raster projections

**Parameters:**

- `INPUT` (raster, required): Input layer
- `CRS` (crs, required): Desired CRS

---

### gdal:buffervectors

**Display Name:** Buffer vectors

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `GEOMETRY` (string, required, default: `geometry`): Geometry column name
- `DISTANCE` (distance, required, default: `10.0`): Buffer distance
- `FIELD` (field, optional): Dissolve by attribute
- `DISSOLVE` (boolean, required, default: `False`): Dissolve all results
- `EXPLODE_COLLECTIONS` (boolean, required, default: `False`): Produce one feature for each geometry in any kind of geometry collection in the source file
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Buffer

---

### gdal:buildvirtualraster

**Display Name:** Build virtual raster

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `RESOLUTION` (enum, required, default: `0`): Resolution
- `SEPARATE` (boolean, required, default: `True`): Place each input file into a separate band
- `PROJ_DIFFERENCE` (boolean, required, default: `False`): Allow projection difference
- `ADD_ALPHA` (boolean, required, default: `False`): Add alpha mask band to VRT when source raster has none
- `ASSIGN_CRS` (crs, optional): Override projection for the output file
- `RESAMPLING` (enum, required, default: `0`): Resampling algorithm
- `SRC_NODATA` (string, optional): Nodata value(s) for input bands (space separated)
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Virtual

---

### gdal:buildvirtualvector

**Display Name:** Build virtual vector

**Group:** Vector miscellaneous

**Parameters:**

- `INPUT` (multilayer, required): Input datasources
- `UNIONED` (boolean, required, default: `False`): Create "unioned" VRT
- `OUTPUT` (vectorDestination, required): Virtual vector

---

### gdal:cliprasterbyextent

**Display Name:** Clip raster by extent

**Group:** Raster extraction

**Parameters:**

- `INPUT` (raster, required): Input layer
- `PROJWIN` (extent, required): Clipping extent
- `OVERCRS` (boolean, required, default: `False`): Override the projection for the output file
- `NODATA` (number, optional): Assign a specified NoData value to output bands
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `DATA_TYPE` (enum, required, default: `0`): Output data type
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Clipped (extent)

---

### gdal:cliprasterbymasklayer

**Display Name:** Clip raster by mask layer

**Group:** Raster extraction

**Parameters:**

- `INPUT` (raster, required): Input layer
- `MASK` (source, required): Mask layer
- `SOURCE_CRS` (crs, optional): Source CRS
- `TARGET_CRS` (crs, optional): Target CRS
- `TARGET_EXTENT` (extent, optional): Target extent
- `NODATA` (number, optional): Assign a specified NoData value to output bands
- `ALPHA_BAND` (boolean, required, default: `False`): Create an output alpha band
- `CROP_TO_CUTLINE` (boolean, required, default: `True`): Match the extent of the clipped raster to the extent of the mask layer
- `KEEP_RESOLUTION` (boolean, required, default: `False`): Keep resolution of input raster
- `SET_RESOLUTION` (boolean, required, default: `False`): Set output file resolution
- `X_RESOLUTION` (number, optional): X Resolution to output bands
- `Y_RESOLUTION` (number, optional): Y Resolution to output bands
- `MULTITHREADING` (boolean, required, default: `False`): Use multithreaded warping implementation
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `DATA_TYPE` (enum, required, default: `0`): Output data type
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Clipped (mask)

---

### gdal:clipvectorbyextent

**Display Name:** Clip vector by extent

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `EXTENT` (extent, required): Clipping extent
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Clipped (extent)

---

### gdal:clipvectorbypolygon

**Display Name:** Clip vector by mask layer

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `MASK` (source, required): Mask layer
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Clipped (mask)

---

### gdal:colorrelief

**Display Name:** Color relief

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `COLOR_TABLE` (file, required): Color configuration file
- `MATCH_MODE` (enum, required, default: `2`): Matching mode
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Color relief

---

### gdal:contour

**Display Name:** Contour

**Group:** Raster extraction

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `INTERVAL` (number, required, default: `10.0`): Interval between contour lines
- `FIELD_NAME` (string, optional, default: `ELEV`): Attribute name (if not set, no elevation attribute is attached)
- `CREATE_3D` (boolean, required, default: `False`): Produce 3D vector
- `IGNORE_NODATA` (boolean, required, default: `False`): Treat all raster values as valid
- `NODATA` (number, optional): Input pixel value to treat as NoData
- `OFFSET` (number, optional, default: `0.0`): Offset from zero relative to which to interpret intervals
- `EXTRA` (string, optional): Additional command-line parameters
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Contours

---

### gdal:contour_polygon

**Display Name:** Contour Polygons

**Group:** Raster extraction

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `INTERVAL` (number, required, default: `10.0`): Interval between contour lines
- `CREATE_3D` (boolean, required, default: `False`): Produce 3D vector
- `IGNORE_NODATA` (boolean, required, default: `False`): Treat all raster values as valid
- `NODATA` (number, optional): Input pixel value to treat as NoData
- `OFFSET` (number, optional, default: `0.0`): Offset from zero relative to which to interpret intervals
- `EXTRA` (string, optional): Additional command-line parameters
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `FIELD_NAME_MIN` (string, optional, default: `ELEV_MIN`): Attribute name for minimum elevation of contour polygon
- `FIELD_NAME_MAX` (string, optional, default: `ELEV_MAX`): Attribute name for maximum elevation of contour polygon
- `OUTPUT` (vectorDestination, required): Contours

---

### gdal:convertformat

**Display Name:** Convert format

**Group:** Vector conversion

**Parameters:**

- `INPUT` (source, required): Input layer
- `CONVERT_ALL_LAYERS` (boolean, required, default: `False`): Convert all layers from dataset
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Converted

---

### gdal:dissolve

**Display Name:** Dissolve

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, optional): Dissolve field
- `GEOMETRY` (string, required, default: `geometry`): Geometry column name
- `EXPLODE_COLLECTIONS` (boolean, required, default: `False`): Produce one feature for each geometry in any kind of geometry collection in the source file
- `KEEP_ATTRIBUTES` (boolean, required, default: `False`): Keep input attributes
- `COUNT_FEATURES` (boolean, required, default: `False`): Count dissolved features
- `COMPUTE_AREA` (boolean, required, default: `False`): Compute area and perimeter of dissolved features
- `COMPUTE_STATISTICS` (boolean, required, default: `False`): Compute min/max/sum/mean for attribute
- `STATISTICS_ATTRIBUTE` (field, optional): Numeric attribute to calculate statistics on
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Dissolved

---

### gdal:executesql

**Display Name:** Execute SQL

**Group:** Vector miscellaneous

**Parameters:**

- `INPUT` (source, required): Input layer
- `SQL` (string, required, default: ``): SQL expression
- `DIALECT` (enum, required, default: `0`): SQL dialect
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): SQL result

---

### gdal:extractprojection

**Display Name:** Extract projection

**Group:** Raster projections

**Parameters:**

- `INPUT` (raster, required): Input file
- `PRJ_FILE_CREATE` (boolean, required, default: `False`): Create also .prj file

---

### gdal:fillnodata

**Display Name:** Fill NoData

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `DISTANCE` (number, required, default: `10`): Maximum distance (in pixels) to search out for values to interpolate
- `ITERATIONS` (number, required, default: `0`): Number of smoothing iterations to run after the interpolation
- `NO_MASK` (boolean, optional, default: `False`): Do not use the default validity mask for the input band
- `MASK_LAYER` (raster, optional): Validity mask
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Filled

---

### gdal:gdal2tiles

**Display Name:** gdal2tiles

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (raster, required): Input layer
- `PROFILE` (enum, required, default: `0`): Tile cutting profile
- `ZOOM` (string, optional, default: ``): Zoom levels to render
- `VIEWER` (enum, required, default: `0`): Web viewer to generate
- `TITLE` (string, optional): Title of the map
- `COPYRIGHT` (string, optional): Copyright of the map
- `RESAMPLING` (enum, required, default: `0`): Resampling method
- `SOURCE_CRS` (crs, optional): The spatial reference system used for the source input data
- `NODATA` (number, optional, default: `0`): Transparency value to assign to the input data
- `URL` (string, optional): URL address where the generated tiles are going to be published
- `GOOGLE_KEY` (string, optional): Google Maps API key (http://code.google.com/apis/maps/signup.html)
- `BING_KEY` (string, optional): Bing Maps API key (https://www.bingmapsportal.com/)
- `RESUME` (boolean, required, default: `False`): Generate only missing files
- `KML` (boolean, required, default: `False`): Generate KML for Google Earth
- `NO_KML` (boolean, required, default: `False`): Avoid automatic generation of KML files for EPSG:4326
- `OUTPUT` (folderDestination, required): Output directory

---

### gdal:gdal2xyz

**Display Name:** gdal2xyz

**Group:** Raster conversion

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `NODATA_INPUT` (number, optional): Input pixel value to treat as NoData
- `NODATA_OUTPUT` (number, optional): Assign specified NoData value to output
- `SKIP_NODATA` (boolean, required, default: `False`): Do not output NoData values
- `CSV` (boolean, required, default: `False`): Output comma-separated values
- `OUTPUT` (fileDestination, required): XYZ ASCII file

---

### gdal:gdalinfo

**Display Name:** Raster information

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (raster, required): Input layer
- `MIN_MAX` (boolean, required, default: `False`): Force computation of the actual min/max values for each band
- `STATS` (boolean, required, default: `False`): Read and display image statistics (force computation if necessary)
- `NOGCP` (boolean, required, default: `False`): Suppress GCP info
- `NO_METADATA` (boolean, required, default: `False`): Suppress metadata info
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (fileDestination, required): Layer information

---

### gdal:gridaverage

**Display Name:** Grid (Moving average)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Point layer
- `Z_FIELD` (field, optional): Z value from field
- `RADIUS_1` (number, required, default: `0.0`): The first radius of search ellipse
- `RADIUS_2` (number, required, default: `0.0`): The second radius of search ellipse
- `ANGLE` (number, required, default: `0.0`): Angle of search ellipse rotation in degrees (counter clockwise)
- `MIN_POINTS` (number, required, default: `0`): Minimum number of data points to use
- `NODATA` (number, required, default: `0.0`): NODATA marker to fill empty points
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Interpolated (moving average)

---

### gdal:griddatametrics

**Display Name:** Grid (Data metrics)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Point layer
- `Z_FIELD` (field, optional): Z value from field
- `METRIC` (enum, required, default: `0`): Data metric to use
- `RADIUS_1` (number, required, default: `0.0`): The first radius of search ellipse
- `RADIUS_2` (number, required, default: `0.0`): The second radius of search ellipse
- `ANGLE` (number, required, default: `0.0`): Angle of search ellipse rotation in degrees (counter clockwise)
- `MIN_POINTS` (number, required, default: `0`): Minimum number of data points to use
- `NODATA` (number, required, default: `0.0`): NODATA marker to fill empty points
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Interpolated (data metrics)

---

### gdal:gridinversedistance

**Display Name:** Grid (Inverse distance to a power)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Point layer
- `Z_FIELD` (field, optional): Z value from field
- `POWER` (number, required, default: `2.0`): Weighting power
- `SMOOTHING` (number, required, default: `0.0`): Smoothing
- `RADIUS_1` (number, required, default: `0.0`): The first radius of search ellipse
- `RADIUS_2` (number, required, default: `0.0`): The second radius of search ellipse
- `ANGLE` (number, required, default: `0.0`): Angle of search ellipse rotation in degrees (counter clockwise)
- `MAX_POINTS` (number, required, default: `0`): Maximum number of data points to use
- `MIN_POINTS` (number, required, default: `0`): Minimum number of data points to use
- `NODATA` (number, required, default: `0.0`): NODATA marker to fill empty points
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Interpolated (IDW)

---

### gdal:gridinversedistancenearestneighbor

**Display Name:** Grid (IDW with nearest neighbor searching)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Point layer
- `Z_FIELD` (field, optional): Z value from field
- `POWER` (number, required, default: `2.0`): Weighting power
- `SMOOTHING` (number, required, default: `0.0`): Smoothing
- `RADIUS` (number, required, default: `1.0`): The radius of the search circle
- `MAX_POINTS` (number, required, default: `12`): Maximum number of data points to use
- `MIN_POINTS` (number, required, default: `0`): Minimum number of data points to use
- `NODATA` (number, required, default: `0.0`): NODATA marker to fill empty points
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Interpolated (IDW with NN search)

---

### gdal:gridlinear

**Display Name:** Grid (Linear)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Point layer
- `Z_FIELD` (field, optional): Z value from field
- `RADIUS` (number, required, default: `-1.0`): Search distance 
- `NODATA` (number, required, default: `0.0`): NODATA marker to fill empty points
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Interpolated (Linear)

---

### gdal:gridnearestneighbor

**Display Name:** Grid (Nearest neighbor)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Point layer
- `Z_FIELD` (field, optional): Z value from field
- `RADIUS_1` (number, required, default: `0.0`): The first radius of search ellipse
- `RADIUS_2` (number, required, default: `0.0`): The second radius of search ellipse
- `ANGLE` (number, required, default: `0.0`): Angle of search ellipse rotation in degrees (counter clockwise)
- `NODATA` (number, required, default: `0.0`): NODATA marker to fill empty points
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Interpolated (Nearest neighbor)

---

### gdal:hillshade

**Display Name:** Hillshade

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `Z_FACTOR` (number, required, default: `1.0`): Z factor (vertical exaggeration)
- `SCALE` (number, required, default: `1.0`): Scale (ratio of vertical units to horizontal)
- `AZIMUTH` (number, required, default: `315.0`): Azimuth of the light
- `ALTITUDE` (number, required, default: `45.0`): Altitude of the light
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `ZEVENBERGEN` (boolean, required, default: `False`): Use Zevenbergen&Thorne formula instead of the Horn's one
- `COMBINED` (boolean, required, default: `False`): Combined shading
- `MULTIDIRECTIONAL` (boolean, required, default: `False`): Multidirectional shading
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Hillshade

---

### gdal:importvectorintopostgisdatabaseavailableconnections

**Display Name:** Export to PostgreSQL (available connections)

**Description:** Exports a vector layer to an existing PostgreSQL database connection

**Group:** Vector miscellaneous

**Parameters:**

- `DATABASE` (providerconnection, required): Database (connection name)
- `INPUT` (source, required): Input layer
- `SHAPE_ENCODING` (string, optional, default: ``): Shape encoding
- `GTYPE` (enum, required, default: `0`): Output geometry type
- `A_SRS` (crs, optional, default: ``): Assign an output CRS
- `T_SRS` (crs, optional, default: ``): Reproject to this CRS on output 
- `S_SRS` (crs, optional, default: ``): Override source CRS
- `SCHEMA` (databaseschema, optional, default: `public`): Schema (schema name)
- `TABLE` (databasetable, optional): Table to import to (leave blank to use layer name)
- `PK` (string, optional, default: `id`): Primary key (new field)
- `PRIMARY_KEY` (field, optional): Primary key (existing field, used if the above option is left empty)
- `GEOCOLUMN` (string, optional, default: `geom`): Geometry column name
- `DIM` (enum, required, default: `0`): Vector dimensions
- `SIMPLIFY` (string, optional, default: ``): Distance tolerance for simplification
- `SEGMENTIZE` (string, optional, default: ``): Maximum distance between 2 nodes (densification)
- `SPAT` (extent, optional): Select features by extent (defined in input layer CRS)
- `CLIP` (boolean, required, default: `False`): Clip the input layer using the above (rectangle) extent
- `WHERE` (string, optional, default: ``): Select features using a SQL "WHERE" statement (Ex: column='value')
- `GT` (string, optional, default: ``): Group N features per transaction (Default: 20000)
- `OVERWRITE` (boolean, required, default: `True`): Overwrite existing table
- `APPEND` (boolean, required, default: `False`): Append to existing table
- `ADDFIELDS` (boolean, required, default: `False`): Append and add new fields to existing table
- `LAUNDER` (boolean, required, default: `False`): Do not launder columns/table names
- `INDEX` (boolean, required, default: `False`): Do not create spatial index
- `SKIPFAILURES` (boolean, required, default: `False`): Continue after a failure, skipping the failed feature
- `MAKEVALID` (boolean, required, default: `False`): Validate geometries based on Simple Features specification
- `PROMOTETOMULTI` (boolean, required, default: `True`): Promote to Multipart
- `PRECISION` (boolean, required, default: `True`): Keep width and precision of input attributes
- `OPTIONS` (string, optional, default: ``): Additional creation options

---

### gdal:importvectorintopostgisdatabasenewconnection

**Display Name:** Export to PostgreSQL (new connection)

**Description:** Exports a vector layer to a new PostgreSQL database connection

**Group:** Vector miscellaneous

**Parameters:**

- `INPUT` (source, required): Input layer
- `SHAPE_ENCODING` (string, optional, default: ``): Shape encoding
- `GTYPE` (enum, required, default: `0`): Output geometry type
- `A_SRS` (crs, optional, default: ``): Assign an output CRS
- `T_SRS` (crs, optional, default: ``): Reproject to this CRS on output 
- `S_SRS` (crs, optional, default: ``): Override source CRS
- `HOST` (string, optional, default: `localhost`): Host
- `PORT` (string, optional, default: `5432`): Port
- `USER` (string, optional, default: ``): Username
- `DBNAME` (string, optional, default: ``): Database name
- `PASSWORD` (string, optional, default: ``): Password
- `SCHEMA` (string, optional, default: `public`): Schema name
- `TABLE` (string, optional, default: ``): Table name, leave blank to use input name
- `PK` (string, optional, default: `id`): Primary key (new field)
- `PRIMARY_KEY` (field, optional): Primary key (existing field, used if the above option is left empty)
- `GEOCOLUMN` (string, optional, default: `geom`): Geometry column name
- `DIM` (enum, required, default: `0`): Vector dimensions
- `SIMPLIFY` (string, optional, default: ``): Distance tolerance for simplification
- `SEGMENTIZE` (string, optional, default: ``): Maximum distance between 2 nodes (densification)
- `SPAT` (extent, optional): Select features by extent (defined in input layer CRS)
- `CLIP` (boolean, required, default: `False`): Clip the input layer using the above (rectangle) extent
- `FIELDS` (field, optional): Fields to include (leave empty to use all fields)
- `WHERE` (string, optional, default: ``): Select features using a SQL "WHERE" statement (Ex: column='value')
- `GT` (string, optional, default: ``): Group N features per transaction (Default: 20000)
- `OVERWRITE` (boolean, required, default: `True`): Overwrite existing table
- `APPEND` (boolean, required, default: `False`): Append to existing table
- `ADDFIELDS` (boolean, required, default: `False`): Append and add new fields to existing table
- `LAUNDER` (boolean, required, default: `False`): Do not launder columns/table names
- `INDEX` (boolean, required, default: `False`): Do not create spatial index
- `SKIPFAILURES` (boolean, required, default: `False`): Continue after a failure, skipping the failed feature
- `MAKEVALID` (boolean, required, default: `False`): Validate geometries based on Simple Features specification
- `PROMOTETOMULTI` (boolean, required, default: `True`): Promote to Multipart
- `PRECISION` (boolean, required, default: `True`): Keep width and precision of input attributes
- `OPTIONS` (string, optional, default: ``): Additional creation options

---

### gdal:merge

**Display Name:** Merge

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `PCT` (boolean, required, default: `False`): Grab pseudocolor table from first layer
- `SEPARATE` (boolean, required, default: `False`): Place each input file into a separate band
- `NODATA_INPUT` (number, optional): Input pixel value to treat as NoData
- `NODATA_OUTPUT` (number, optional): Assign specified NoData value to output
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Merged

---

### gdal:nearblack

**Display Name:** Near black

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `NEAR` (number, required, default: `15`): How far from black (white)
- `WHITE` (boolean, required, default: `False`): Search for nearly white pixels instead of nearly black
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Nearblack

---

### gdal:offsetcurve

**Display Name:** Offset curve

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `GEOMETRY` (string, required, default: `geometry`): Geometry column name
- `DISTANCE` (distance, required, default: `10`): Offset distance (left-sided: positive, right-sided: negative)
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Offset curve

---

### gdal:ogrinfo

**Display Name:** Vector information

**Group:** Vector miscellaneous

**Parameters:**

- `INPUT` (vector, required): Input layer
- `ALL_LAYERS` (boolean, required, default: `False`): Enable listing of all layers in the dataset
- `SUMMARY_ONLY` (boolean, required, default: `True`): Summary output only
- `NO_METADATA` (boolean, required, default: `False`): Suppress metadata info
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (fileDestination, required): Layer information

---

### gdal:onesidebuffer

**Display Name:** One side buffer

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `GEOMETRY` (string, required, default: `geometry`): Geometry column name
- `DISTANCE` (distance, required, default: `10`): Buffer distance
- `BUFFER_SIDE` (enum, required, default: `0`): Buffer side
- `FIELD` (field, optional): Dissolve by attribute
- `DISSOLVE` (boolean, required, default: `False`): Dissolve all results
- `EXPLODE_COLLECTIONS` (boolean, required, default: `False`): Produce one feature for each geometry in any kind of geometry collection in the source file
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): One-sided buffer

---

### gdal:overviews

**Display Name:** Build overviews (pyramids)

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (raster, required): Input layer
- `CLEAN` (boolean, required, default: `False`): Remove all existing overviews
- `LEVELS` (string, optional): Overview levels (e.g. 2 4 8 16)
- `RESAMPLING` (enum, optional): Resampling method
- `FORMAT` (enum, optional, default: `0`): Overviews format
- `EXTRA` (string, optional): Additional command-line parameters

---

### gdal:pansharp

**Display Name:** Pansharpening

**Group:** Raster miscellaneous

**Parameters:**

- `SPECTRAL` (raster, required): Spectral dataset
- `PANCHROMATIC` (raster, required): Panchromatic dataset
- `RESAMPLING` (enum, required, default: `2`): Resampling algorithm
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Output

---

### gdal:pcttorgb

**Display Name:** PCT to RGB

**Group:** Raster conversion

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `RGBA` (boolean, required, default: `False`): Generate a RGBA file
- `OUTPUT` (rasterDestination, required): PCT to RGB

---

### gdal:pointsalonglines

**Display Name:** Points along lines

**Group:** Vector geoprocessing

**Parameters:**

- `INPUT` (source, required): Input layer
- `GEOMETRY` (string, required, default: `geometry`): Geometry column name
- `DISTANCE` (number, required, default: `0.5`): Distance from line start represented as fraction of line length
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (vectorDestination, required): Points along lines

---

### gdal:polygonize

**Display Name:** Polygonize (raster to vector)

**Group:** Raster conversion

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `FIELD` (string, required, default: `DN`): Name of the field to create
- `EIGHT_CONNECTEDNESS` (boolean, required, default: `False`): Use 8-connectedness
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (vectorDestination, required): Vectorized

---

### gdal:proximity

**Display Name:** Proximity (raster distance)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `VALUES` (string, optional): A list of pixel values in the source image to be considered target pixels
- `UNITS` (enum, required, default: `1`): Distance units
- `MAX_DISTANCE` (number, optional, default: `0.0`): The maximum distance to be generated
- `REPLACE` (number, optional, default: `0.0`): Value to be applied to all pixels that are within the -maxdist of target pixels
- `NODATA` (number, optional, default: `0.0`): Nodata value to use for the destination proximity raster
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `OUTPUT` (rasterDestination, required): Proximity map

---

### gdal:rastercalculator

**Display Name:** Raster calculator

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT_A` (raster, required): Input layer A
- `BAND_A` (band, required): Number of raster band for A
- `INPUT_B` (raster, optional): Input layer B
- `BAND_B` (band, optional): Number of raster band for B
- `INPUT_C` (raster, optional): Input layer C
- `BAND_C` (band, optional): Number of raster band for C
- `INPUT_D` (raster, optional): Input layer D
- `BAND_D` (band, optional): Number of raster band for D
- `INPUT_E` (raster, optional): Input layer E
- `BAND_E` (band, optional): Number of raster band for E
- `INPUT_F` (raster, optional): Input layer F
- `BAND_F` (band, optional): Number of raster band for F
- `FORMULA` (string, required, default: `A*2`): Calculation in gdalnumeric syntax using +-/* or any numpy array functions (i.e. logical_and())
- `NO_DATA` (number, optional): Set output NoData value
- `EXTENT_OPT` (enum, required, default: `0`): Handling of extent differences
- `PROJWIN` (extent, optional): Output extent
- `RTYPE` (enum, required, default: `5`): Output raster type
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Calculated

---

### gdal:rasterize

**Display Name:** Rasterize (vector to raster)

**Group:** Vector conversion

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, optional): Field to use for a burn-in value
- `BURN` (number, optional, default: `0.0`): A fixed value to burn
- `USE_Z` (boolean, optional, default: `False`): Burn value extracted from the "Z" values of the feature
- `UNITS` (enum, required): Output raster size units
- `WIDTH` (number, required, default: `0.0`): Width/Horizontal resolution
- `HEIGHT` (number, required, default: `0.0`): Height/Vertical resolution
- `EXTENT` (extent, optional): Output extent
- `NODATA` (number, optional): Assign a specified NoData value to output bands
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `INIT` (number, optional): Pre-initialize the output image with value
- `INVERT` (boolean, required, default: `False`): Invert rasterization
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Rasterized

---

### gdal:rasterize_over

**Display Name:** Rasterize (overwrite with attribute)

**Group:** Vector conversion

**Parameters:**

- `INPUT` (source, required): Input vector layer
- `INPUT_RASTER` (raster, required): Input raster layer
- `FIELD` (field, required): Field to use for burn in value
- `ADD` (boolean, required, default: `False`): Add burn in values to existing raster values
- `EXTRA` (string, optional): Additional command-line parameters

---

### gdal:rasterize_over_fixed_value

**Display Name:** Rasterize (overwrite with fixed value)

**Group:** Vector conversion

**Parameters:**

- `INPUT` (source, required): Input vector layer
- `INPUT_RASTER` (raster, required): Input raster layer
- `BURN` (number, required, default: `0.0`): A fixed value to burn
- `ADD` (boolean, required, default: `False`): Add burn in values to existing raster values
- `EXTRA` (string, optional): Additional command-line parameters

---

### gdal:rearrange_bands

**Display Name:** Rearrange bands

**Group:** Raster conversion

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BANDS` (band, required): Selected band(s)
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `DATA_TYPE` (enum, required, default: `0`): Output data type
- `OUTPUT` (rasterDestination, required): Converted

---

### gdal:retile

**Display Name:** Retile

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (multilayer, required): Input files
- `TILE_SIZE_X` (number, required, default: `256`): Tile width
- `TILE_SIZE_Y` (number, required, default: `256`): Tile height
- `OVERLAP` (number, required, default: `0`): Overlap in pixels between consecutive tiles
- `LEVELS` (number, required, default: `1`): Number of pyramids levels to build
- `SOURCE_CRS` (crs, optional): Source coordinate reference system
- `RESAMPLING` (enum, required, default: `0`): Resampling method
- `DELIMITER` (string, optional, default: `;`): Column delimiter used in the CSV file
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `ONLY_PYRAMIDS` (boolean, required, default: `False`): Build only the pyramids
- `DIR_FOR_ROW` (boolean, required, default: `False`): Use separate directory for each tiles row
- `OUTPUT` (folderDestination, required): Output directory
- `OUTPUT_CSV` (fileDestination, optional): CSV file containing the tile(s) georeferencing information

---

### gdal:rgbtopct

**Display Name:** RGB to PCT

**Group:** Raster conversion

**Parameters:**

- `INPUT` (raster, required): Input layer
- `NCOLORS` (number, required, default: `2`): Number of colors
- `OUTPUT` (rasterDestination, required): RGB to PCT

---

### gdal:roughness

**Display Name:** Roughness

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (rasterDestination, required): Roughness

---

### gdal:sieve

**Display Name:** Sieve

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `THRESHOLD` (number, required, default: `10`): Threshold
- `EIGHT_CONNECTEDNESS` (boolean, required, default: `False`): Use 8-connectedness
- `NO_MASK` (boolean, required, default: `False`): Do not use the default validity mask for the input band
- `MASK_LAYER` (raster, optional): Validity mask
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Sieved

---

### gdal:slope

**Display Name:** Slope

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `SCALE` (number, required, default: `1.0`): Ratio of vertical units to horizontal
- `AS_PERCENT` (boolean, required, default: `False`): Slope expressed as percent instead of degrees
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `ZEVENBERGEN` (boolean, required, default: `False`): Use Zevenbergen&Thorne formula instead of the Horn's one
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Slope

---

### gdal:tileindex

**Display Name:** Tile index

**Group:** Raster miscellaneous

**Parameters:**

- `LAYERS` (multilayer, required): Input files
- `PATH_FIELD_NAME` (string, required, default: `location`): Field name to hold the file path to the indexed rasters
- `ABSOLUTE_PATH` (boolean, required, default: `False`): Store absolute path to the indexed rasters
- `PROJ_DIFFERENCE` (boolean, required, default: `False`): Skip files with different projection reference
- `TARGET_CRS` (crs, optional): Transform geometries to the given CRS
- `CRS_FIELD_NAME` (string, optional): The name of the field to store the SRS of each tile
- `CRS_FORMAT` (enum, required, default: `0`): The format in which the CRS of each tile must be written
- `OUTPUT` (vectorDestination, required): Tile index

---

### gdal:tpitopographicpositionindex

**Display Name:** Topographic Position Index (TPI)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (rasterDestination, required): Topographic Position Index

---

### gdal:translate

**Display Name:** Translate (convert format)

**Group:** Raster conversion

**Parameters:**

- `INPUT` (raster, required): Input layer
- `TARGET_CRS` (crs, optional): Override the projection for the output file
- `NODATA` (number, optional): Assign a specified NoData value to output bands
- `COPY_SUBDATASETS` (boolean, required, default: `False`): Copy all subdatasets of this file to individual output files
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `DATA_TYPE` (enum, required, default: `0`): Output data type
- `OUTPUT` (rasterDestination, required): Converted

---

### gdal:triterrainruggednessindex

**Display Name:** Terrain Ruggedness Index (TRI)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `COMPUTE_EDGES` (boolean, required, default: `False`): Compute edges
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `OUTPUT` (rasterDestination, required): Terrain Ruggedness Index

---

### gdal:viewshed

**Display Name:** Viewshed

**Group:** Raster miscellaneous

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `OBSERVER` (point, required): Observer location
- `OBSERVER_HEIGHT` (number, required, default: `1.0`): Observer height, DEM units
- `TARGET_HEIGHT` (number, required, default: `1.0`): Target height, DEM units
- `MAX_DISTANCE` (distance, required, default: `100.0`): Maximum distance from observer to compute visibility
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Output

---

### gdal:warpreproject

**Display Name:** Warp (reproject)

**Group:** Raster projections

**Parameters:**

- `INPUT` (raster, required): Input layer
- `SOURCE_CRS` (crs, optional): Source CRS
- `TARGET_CRS` (crs, optional): Target CRS
- `RESAMPLING` (enum, required, default: `0`): Resampling method to use
- `NODATA` (number, optional): Nodata value for output bands
- `TARGET_RESOLUTION` (number, optional): Output file resolution in target georeferenced units
- `OPTIONS` (string, optional, default: ``): Additional creation options
- `DATA_TYPE` (enum, required, default: `0`): Output data type
- `TARGET_EXTENT` (extent, optional): Georeferenced extents of output file to be created
- `TARGET_EXTENT_CRS` (crs, optional): CRS of the target raster extent
- `MULTITHREADING` (boolean, required, default: `False`): Use multithreaded warping implementation
- `EXTRA` (string, optional): Additional command-line parameters
- `OUTPUT` (rasterDestination, required): Reprojected

---

## GRASS

Provider ID: `grass`
Total algorithms: 307

### grass:g.extension.list

**Display Name:** g.extension.list

**Description:** g.extension.list - List GRASS addons.

**Group:** General (g.*)

**Parameters:**

- `list` (enum, required, default: `0`): List
- `html` (fileDestination, optional, default: `addons_list.html`): List of addons
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:g.extension.manage

**Display Name:** g.extension.manage

**Description:** g.extension.manage - Install or uninstall GRASS addons.

**Group:** General (g.*)

**Parameters:**

- `extension` (string, required): Name of Extension
- `operation` (enum, required): Operation
- `-f` (boolean, required, default: `False`): Force (required for removal)
- `-t` (boolean, required, default: `False`): Operate on toolboxes instead of single modules (experimental)
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:g.version

**Display Name:** g.version

**Description:** g.version - Display GRASS GIS version info. <p>Prints only version if run with no options checked.

**Group:** General (g.*)

**Parameters:**

- `-c` (boolean, required, default: `False`): Print copyright message
- `-x` (boolean, required, default: `False`): Print citation options
- `-b` (boolean, required, default: `False`): Print build information
- `-r` (boolean, required, default: `True`): Print GIS library revision number and date
- `-e` (boolean, required, default: `True`): Print info for additional libraries
- `-g` (boolean, required, default: `False`): Print in shell script style (with Git commit reference)
- `--verbose` (boolean, required, default: `False`): Print verbose output
- `html` (fileDestination, optional, default: `grass_version_info.html`): Output file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:i.albedo

**Display Name:** i.albedo

**Description:** Computes broad band albedo from surface reflectance.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Name of input raster maps
- `-m` (boolean, required, default: `False`): MODIS (7 input bands:1,2,3,4,5,6,7)
- `-n` (boolean, required, default: `False`): NOAA AVHRR (2 input bands:1,2)
- `-l` (boolean, required, default: `False`): Landsat 5+7 (6 input bands:1,2,3,4,5,7)
- `-8` (boolean, required, default: `False`): Landsat 8 (7 input bands:1,2,3,4,5,6,7)
- `-a` (boolean, required, default: `False`): ASTER (6 input bands:1,3,5,6,8,9)
- `-c` (boolean, required, default: `False`): Aggressive mode (Landsat)
- `-d` (boolean, required, default: `False`): Soft mode (MODIS)
- `output` (rasterDestination, required): Albedo
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.aster.toar

**Display Name:** i.aster.toar

**Description:** Calculates Top of Atmosphere Radiance/Reflectance/Brightness Temperature from ASTER DN.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Names of ASTER DN layers (15 layers)
- `dayofyear` (number, required, default: `0.0`): Day of Year of satellite overpass [0-366]
- `sun_elevation` (number, required): Sun elevation angle (degrees, < 90.0)
- `-r` (boolean, required, default: `False`): Output is radiance (W/m2)
- `-a` (boolean, required, default: `False`): VNIR is High Gain
- `-b` (boolean, required, default: `False`): SWIR is High Gain
- `-c` (boolean, required, default: `False`): VNIR is Low Gain 1
- `-d` (boolean, required, default: `False`): SWIR is Low Gain 1
- `-e` (boolean, required, default: `False`): SWIR is Low Gain 2
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.atcorr

**Display Name:** i.atcorr

**Description:** Performs atmospheric correction using the 6S algorithm.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `range` (range, optional, default: `0,255`): Input imagery range [0,255]
- `elevation` (raster, optional): Input altitude raster map in m (optional)
- `visibility` (raster, optional): Input visibility raster map in km (optional)
- `parameters` (file, required): Name of input text file
- `rescale` (range, optional, default: `0,255`): Rescale output raster map [0,255]
- `output` (rasterDestination, required): Atmospheric correction
- `-i` (boolean, required, default: `False`): Output raster map as integer
- `-r` (boolean, required, default: `False`): Input raster map converted to reflectance (default is radiance)
- `-a` (boolean, required, default: `False`): Input from ETM+ image taken after July 1, 2000
- `-b` (boolean, required, default: `False`): Input from ETM+ image taken before July 1, 2000
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.biomass

**Display Name:** i.biomass

**Description:** Computes biomass growth, precursor of crop yield calculation.

**Group:** Imagery (i.*)

**Parameters:**

- `fpar` (raster, required): Name of fPAR raster map
- `lightuse_efficiency` (raster, required): Name of light use efficiency raster map (UZB:cotton=1.9)
- `latitude` (raster, required): Name of degree latitude raster map [dd.ddd]
- `dayofyear` (raster, required): Name of Day of Year raster map [1-366]
- `transmissivity_singleway` (raster, required): Name of single-way transmissivity raster map [0.0-1.0]
- `water_availability` (raster, required): Value of water availability raster map [0.0-1.0]
- `output` (rasterDestination, required): Biomass
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.cca

**Display Name:** i.cca

**Description:** Canonical components analysis (CCA) program for image processing.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters (2 to 8)
- `signature` (file, required): File containing spectral signatures
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.cluster

**Display Name:** i.cluster

**Description:** Generates spectral signatures for land cover types in an image using a clustering algorithm.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters
- `classes` (number, required): Initial number of classes (1-255)
- `seed` (file, optional): Name of file containing initial signatures
- `sample` (string, optional): Sampling intervals (by row and col)
- `iterations` (number, optional, default: `30.0`): Maximum number of iterations
- `convergence` (number, optional, default: `98.0`): Percent convergence
- `separation` (number, optional, default: `0.0`): Cluster separation
- `min_size` (number, optional, default: `17.0`): Minimum number of pixels in a class
- `signaturefile` (fileDestination, required): Signature File
- `reportfile` (fileDestination, optional): Final Report File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.colors.enhance

**Display Name:** i.colors.enhance

**Description:** Performs auto-balancing of colors for RGB images.

**Group:** Imagery (i.*)

**Parameters:**

- `red` (raster, required): Name of red channel
- `green` (raster, required): Name of green channel
- `blue` (raster, required): Name of blue channel
- `strength` (number, optional, default: `98.0`): Cropping intensity (upper brightness level)
- `-f` (boolean, required, default: `False`): Extend colors to full range of data on each channel
- `-p` (boolean, required, default: `False`): Preserve relative colors, adjust brightness only
- `-r` (boolean, required, default: `False`): Reset to standard color range
- `-s` (boolean, required, default: `False`): Process bands serially (default: run in parallel)
- `redoutput` (rasterDestination, required): Enhanced Red
- `greenoutput` (rasterDestination, required): Enhanced Green
- `blueoutput` (rasterDestination, required): Enhanced Blue
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.eb.eta

**Display Name:** i.eb.eta

**Description:** Actual evapotranspiration for diurnal period (Bastiaanssen, 1995).

**Group:** Imagery (i.*)

**Parameters:**

- `netradiationdiurnal` (raster, required): Name of the diurnal net radiation map [W/m2]
- `evaporativefraction` (raster, required): Name of the evaporative fraction map
- `temperature` (raster, required): Name of the surface skin temperature [K]
- `output` (rasterDestination, required): Evapotranspiration
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.eb.evapfr

**Display Name:** i.eb.evapfr

**Description:** Computes evaporative fraction (Bastiaanssen, 1995) and root zone soil moisture (Makin, Molden and Bastiaanssen, 2001).

**Group:** Imagery (i.*)

**Parameters:**

- `netradiation` (raster, required): Name of Net Radiation raster map [W/m2]
- `soilheatflux` (raster, required): Name of soil heat flux raster map [W/m2]
- `sensibleheatflux` (raster, required): Name of sensible heat flux raster map [W/m2]
- `evaporativefraction` (rasterDestination, required): Evaporative Fraction
- `soilmoisture` (rasterDestination, optional): Root Zone Soil Moisture
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.eb.hsebal01.coords

**Display Name:** i.eb.hsebal01.coords

**Description:** i.eb.hsebal01.coords - Computes sensible heat flux iteration SEBAL 01. Inline coordinates

**Group:** Imagery (i.*)

**Parameters:**

- `netradiation` (raster, required): Name of instantaneous net radiation raster map [W/m2]
- `soilheatflux` (raster, required): Name of instantaneous soil heat flux raster map [W/m2]
- `aerodynresistance` (raster, required): Name of aerodynamic resistance to heat momentum raster map [s/m]
- `temperaturemeansealevel` (raster, required): Name of altitude corrected surface temperature raster map [K]
- `frictionvelocitystar` (number, required, default: `0.32407`): Value of the height independent friction velocity (u*) [m/s]
- `vapourpressureactual` (raster, required): Name of the actual vapour pressure (e_act) map [KPa]
- `row_wet_pixel` (number, optional): Row value of the wet pixel
- `column_wet_pixel` (number, optional): Column value of the wet pixel
- `row_dry_pixel` (number, optional): Row value of the dry pixel
- `column_dry_pixel` (number, optional): Column value of the dry pixel
- `-a` (boolean, required, default: `False`): Automatic wet/dry pixel (careful!)
- `-c` (boolean, required, default: `False`): Dry/Wet pixels coordinates are in image projection, not row/col
- `output` (rasterDestination, required): Sensible Heat Flux
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.eb.netrad

**Display Name:** i.eb.netrad

**Description:** Net radiation approximation (Bastiaanssen, 1995).

**Group:** Imagery (i.*)

**Parameters:**

- `albedo` (raster, required): Name of albedo raster map [0.0;1.0]
- `ndvi` (raster, required): Name of NDVI raster map [-1.0;+1.0]
- `temperature` (raster, required): Name of surface temperature raster map [K]
- `localutctime` (raster, required): Name of time of satellite overpass raster map [local time in UTC]
- `temperaturedifference2m` (raster, required): Name of the difference map of temperature from surface skin to about 2 m height [K]
- `emissivity` (raster, required): Name of the emissivity map [-]
- `transmissivity_singleway` (raster, required): Name of the single-way atmospheric transmissivitymap [-]
- `dayofyear` (raster, required): Name of the Day Of Year (DOY) map [-]
- `sunzenithangle` (raster, required): Name of the sun zenith angle map [degrees]
- `output` (rasterDestination, required): Net Radiation
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.eb.soilheatflux

**Display Name:** i.eb.soilheatflux

**Description:** Soil heat flux approximation (Bastiaanssen, 1995).

**Group:** Imagery (i.*)

**Parameters:**

- `albedo` (raster, required): Name of albedo raster map [0.0;1.0]
- `ndvi` (raster, required): Name of NDVI raster map [-1.0;+1.0]
- `temperature` (raster, required): Name of Surface temperature raster map [K]
- `netradiation` (raster, required): Name of Net Radiation raster map [W/m2]
- `localutctime` (raster, required): Name of time of satellite overpass raster map [local time in UTC]
- `-r` (boolean, required, default: `False`): HAPEX-Sahel empirical correction (Roerink, 1995)
- `output` (rasterDestination, required): Soil Heat Flux
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.emissivity

**Display Name:** i.emissivity

**Description:** Computes emissivity from NDVI, generic method for sparse land.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (raster, required): Name of NDVI raster map [-]
- `output` (rasterDestination, required): Emissivity
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.evapo.mh

**Display Name:** i.evapo.mh

**Description:** Computes evapotranspiration calculation modified or original Hargreaves formulation, 2001.

**Group:** Imagery (i.*)

**Parameters:**

- `netradiation_diurnal` (raster, required): Name of input diurnal net radiation raster map [W/m2/d]
- `average_temperature` (raster, required): Name of input average air temperature raster map [C]
- `minimum_temperature` (raster, required): Name of input minimum air temperature raster map [C]
- `maximum_temperature` (raster, required): Name of input maximum air temperature raster map [C]
- `precipitation` (raster, optional): Name of precipitation raster map [mm/month]
- `-z` (boolean, required, default: `False`): Set negative ETa to zero
- `-h` (boolean, required, default: `False`): Use original Hargreaves (1985)
- `-s` (boolean, required, default: `False`): Use Hargreaves-Samani (1985)
- `output` (rasterDestination, required): Evapotranspiration
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.evapo.pm

**Display Name:** i.evapo.pm

**Description:** Computes potential evapotranspiration calculation with hourly Penman-Monteith.

**Group:** Imagery (i.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map [m a.s.l.]
- `temperature` (raster, required): Name of input temperature raster map [C]
- `relativehumidity` (raster, required): Name of input relative humidity raster map [%]
- `windspeed` (raster, required): Name of input wind speed raster map [m/s]
- `netradiation` (raster, required): Name of input net solar radiation raster map [MJ/m2/h]
- `cropheight` (raster, required): Name of input crop height raster map [m]
- `-z` (boolean, required, default: `False`): Set negative ETa to zero
- `-n` (boolean, required, default: `False`): Use Night-time
- `output` (rasterDestination, required): Evapotranspiration
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.evapo.pt

**Display Name:** i.evapo.pt

**Description:** Computes evapotranspiration calculation Priestley and Taylor formulation, 1972.

**Group:** Imagery (i.*)

**Parameters:**

- `net_radiation` (raster, required): Name of input net radiation raster map [W/m2]
- `soil_heatflux` (raster, required): Name of input soil heat flux raster map [W/m2]
- `air_temperature` (raster, required): Name of input air temperature raster map [K]
- `atmospheric_pressure` (raster, required): Name of input atmospheric pressure raster map [millibars]
- `priestley_taylor_coeff` (number, required, default: `1.26`): Priestley-Taylor coefficient
- `-z` (boolean, required, default: `False`): Set negative ETa to zero
- `output` (rasterDestination, required): Evapotranspiration
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.evapo.time

**Display Name:** i.evapo.time

**Description:** Computes temporal integration of satellite ET actual (ETa) following the daily ET reference (ETo) from meteorological station(s).

**Group:** Imagery (i.*)

**Parameters:**

- `eta` (multilayer, required): Names of satellite ETa raster maps [mm/d or cm/d]
- `eta_doy` (multilayer, required): Names of satellite ETa Day of Year (DOY) raster maps [0-400] [-]
- `eto` (multilayer, required): Names of meteorological station ETo raster maps [0-400] [mm/d or cm/d]
- `eto_doy_min` (number, required, default: `1.0`): Value of DOY for ETo first day
- `start_period` (number, required, default: `1.0`): Value of DOY for the first day of the period studied
- `end_period` (number, required, default: `1.0`): Value of DOY for the last day of the period studied
- `output` (rasterDestination, required): Temporal integration
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.fft

**Display Name:** i.fft

**Description:** Fast Fourier Transform (FFT) for image processing.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `real` (rasterDestination, required): Real part arrays
- `imaginary` (rasterDestination, required): Imaginary part arrays
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.gensig

**Display Name:** i.gensig

**Description:** Generates statistics for i.maxlik from raster map.

**Group:** Imagery (i.*)

**Parameters:**

- `trainingmap` (raster, required): Ground truth training map
- `input` (multilayer, required): Input rasters
- `signaturefile` (fileDestination, required): Signature File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.gensigset

**Display Name:** i.gensigset

**Description:** Generates statistics for i.smap from raster map.

**Group:** Imagery (i.*)

**Parameters:**

- `trainingmap` (raster, required): Ground truth training map
- `input` (multilayer, required): Input rasters
- `maxsig` (number, optional, default: `5.0`): Maximum number of sub-signatures in any class
- `signaturefile` (fileDestination, required): Signature File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.group

**Display Name:** i.group

**Description:** Regroup multiple mono-band rasters into a single multiband raster.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters
- `group` (rasterDestination, required): Multiband raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.his.rgb

**Display Name:** i.his.rgb

**Description:** Transforms raster maps from HIS (Hue-Intensity-Saturation) color space to RGB (Red-Green-Blue) color space.

**Group:** Imagery (i.*)

**Parameters:**

- `hue` (raster, required): Name of input raster map (hue)
- `intensity` (raster, required): Name of input raster map (intensity)
- `saturation` (raster, required): Name of input raster map (saturation)
- `red` (rasterDestination, required): Red
- `green` (rasterDestination, required): Green
- `blue` (rasterDestination, required): Blue
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.ifft

**Display Name:** i.ifft

**Description:** Inverse Fast Fourier Transform (IFFT) for image processing.

**Group:** Imagery (i.*)

**Parameters:**

- `real` (raster, required): Name of input raster map (image fft, real part)
- `imaginary` (raster, required): Name of input raster map (image fft, imaginary part)
- `output` (rasterDestination, required): Inverse Fast Fourier Transform
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.image.mosaic

**Display Name:** i.image.mosaic

**Description:** Mosaics several images and extends colormap.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters
- `output` (rasterDestination, required): Mosaic Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.in.spotvgt

**Display Name:** i.in.spotvgt

**Description:** Imports SPOT VGT NDVI data into a raster map.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (file, required): Name of input SPOT VGT NDVI HDF file
- `-a` (boolean, required, default: `False`): Also import quality map (SM status map layer) and filter NDVI map
- `output` (rasterDestination, required): SPOT NDVI Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.landsat.acca

**Display Name:** i.landsat.acca

**Description:** Performs Landsat TM/ETM+ Automatic Cloud Cover Assessment (ACCA).

**Group:** Imagery (i.*)

**Parameters:**

- `rasters` (multilayer, required): Landsat input rasters
- `b56composite` (number, optional, default: `225.0`): B56composite (step 6)
- `b45ratio` (number, optional, default: `1.0`): B45ratio: Desert detection (step 10)
- `histogram` (number, optional, default: `100.0`): Number of classes in the cloud temperature histogram
- `-5` (boolean, required, default: `False`): Data is Landsat-5 TM
- `-f` (boolean, required, default: `False`): Apply post-processing filter to remove small holes
- `-x` (boolean, required, default: `False`): Always use cloud signature (step 14)
- `-2` (boolean, required, default: `False`): Bypass second-pass processing, and merge warm (not ambiguous) and cold clouds
- `-s` (boolean, required, default: `False`): Include a category for cloud shadows
- `output` (rasterDestination, required): ACCA Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.landsat.toar

**Display Name:** i.landsat.toar

**Description:** Calculates top-of-atmosphere radiance or reflectance and temperature for Landsat MSS/TM/ETM+/OLI

**Group:** Imagery (i.*)

**Parameters:**

- `rasters` (multilayer, required): Landsat input rasters
- `metfile` (file, optional): Name of Landsat metadata file (.met or MTL.txt)
- `sensor` (enum, optional, default: `7`): Spacecraft sensor
- `method` (enum, optional, default: `0`): Atmospheric correction method
- `date` (string, optional): Image acquisition date (yyyy-mm-dd)
- `sun_elevation` (number, optional): Sun elevation in degrees
- `product_date` (string, optional): Image creation date (yyyy-mm-dd)
- `gain` (string, optional): Gain (H/L) of all Landsat ETM+ bands (1-5,61,62,7,8)
- `percent` (number, optional, default: `0.01`): Percent of solar radiance in path radiance
- `pixel` (number, optional, default: `1000.0`): Minimum pixels to consider digital number as dark object
- `rayleigh` (number, optional, default: `0.0`): Rayleigh atmosphere (diffuse sky irradiance)
- `scale` (number, optional, default: `1.0`): Scale factor for output
- `-r` (boolean, required, default: `False`): Output at-sensor radiance instead of reflectance for all bands
- `-n` (boolean, required, default: `False`): Input raster maps use as extension the number of the band instead the code
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.maxlik

**Display Name:** i.maxlik

**Description:** Classifies the cell spectral reflectances in imagery data.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters
- `signaturefile` (file, required): Name of input file containing signatures
- `output` (rasterDestination, required): Classification
- `reject` (rasterDestination, optional): Reject Threshold
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.modis.qc

**Display Name:** i.modis.qc

**Description:** Extracts quality control parameters from MODIS QC layers.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (raster, required): Name of input surface reflectance QC layer [bit array]
- `productname` (enum, required, default: `8`): Name of MODIS product type
- `qcname` (enum, required, default: `5`): Name of QC type to extract
- `band` (enum, optional, default: `[0, 1]`): Band number of MODIS product (mod09Q1=[1,2],mod09A1=[1-7],m[o/y]d09CMG=[1-7], mcd43B2q=[1-7])
- `output` (rasterDestination, required): QC Classification
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.oif

**Display Name:** i.oif

**Description:** Calculates Optimum-Index-Factor table for spectral bands

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Name of input raster map(s)
- `-g` (boolean, required, default: `False`): Print in shell script style
- `-s` (boolean, required, default: `False`): Process bands serially (default: run in parallel)
- `output` (fileDestination, required): OIF File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.pansharpen

**Display Name:** i.pansharpen

**Description:** Image fusion algorithms to sharpen multispectral with high-res panchromatic channels

**Group:** Imagery (i.*)

**Parameters:**

- `red` (raster, required): Name of red channel
- `green` (raster, required): Name of green channel
- `blue` (raster, required): Name of blue channel
- `pan` (raster, required): Name of raster map to be used for high resolution panchromatic channel
- `method` (enum, required, default: `1`): Method
- `-l` (boolean, required, default: `False`): Rebalance blue channel for LANDSAT
- `-s` (boolean, required, default: `False`): Process bands serially (default: run in parallel)
- `redoutput` (rasterDestination, required): Enhanced Red
- `greenoutput` (rasterDestination, required): Enhanced Green
- `blueoutput` (rasterDestination, required): Enhanced Blue
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.pca

**Display Name:** i.pca

**Description:** Principal components analysis (PCA) for image processing.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Name of two or more input raster maps
- `rescale` (range, optional, default: `0,255`): Rescaling range for output maps. For no rescaling use 0,0
- `percent` (number, optional, default: `99.0`): Cumulative percent importance for filtering
- `-n` (boolean, required, default: `False`): Normalize (center and scale) input maps
- `-f` (boolean, required, default: `False`): Output will be filtered input bands
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.rgb.his

**Display Name:** i.rgb.his

**Description:** Transforms raster maps from RGB (Red-Green-Blue) color space to HIS (Hue-Intensity-Saturation) color space.

**Group:** Imagery (i.*)

**Parameters:**

- `red` (raster, optional): Name for input raster map (red)
- `green` (raster, optional): Name for input raster map (green)
- `blue` (raster, optional): Name for input raster map (blue)
- `hue` (rasterDestination, required, default: `False`): Hue
- `intensity` (rasterDestination, required, default: `False`): Intensity
- `saturation` (rasterDestination, required, default: `False`): Saturation
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.segment

**Display Name:** i.segment

**Description:** Identifies segments (objects) from imagery data.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters
- `threshold` (number, required, default: `0.5`): Difference threshold between 0 and 1
- `method` (enum, optional, default: `0`): Segmentation method
- `similarity` (enum, optional, default: `0`): Similarity calculation method
- `minsize` (number, optional, default: `1.0`): Minimum number of cells in a segment
- `memory` (number, optional, default: `300.0`): Amount of memory to use in MB
- `iterations` (number, optional, default: `20.0`): Maximum number of iterations
- `seeds` (raster, optional): Name for input raster map with starting seeds
- `bounds` (raster, optional): Name of input bounding/constraining raster map
- `-d` (boolean, required, default: `False`): Use 8 neighbors (3x3 neighborhood) instead of the default 4 neighbors for each pixel
- `-w` (boolean, required, default: `False`): Weighted input, do not perform the default scaling of input raster maps
- `output` (rasterDestination, required): Segmented Raster
- `goodness` (rasterDestination, optional): Goodness Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.smap

**Display Name:** i.smap

**Description:** Performs contextual image classification using sequential maximum a posteriori (SMAP) estimation.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters
- `signaturefile` (file, required): Name of input file containing signatures
- `blocksize` (number, optional, default: `1024.0`): Size of submatrix to process at one time
- `-m` (boolean, required, default: `False`): Use maximum likelihood estimation (instead of smap)
- `output` (rasterDestination, required): Classification
- `goodness` (rasterDestination, optional): Goodness_of_fit
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.tasscap

**Display Name:** i.tasscap

**Description:** Performs Tasseled Cap (Kauth Thomas) transformation.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Input rasters. Landsat4-7: bands 1,2,3,4,5,7; Landsat8: bands 2,3,4,5,6,7; MODIS: bands 1,2,3,4,5,6,7
- `sensor` (enum, required, default: `0`): Satellite sensor
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.topo.coor.ill

**Display Name:** i.topo.coor.ill

**Description:** i.topo.coor.ill - Creates illumination model for topographic correction of reflectance.

**Group:** Imagery (i.*)

**Parameters:**

- `basemap` (raster, required): Name of elevation raster map
- `zenith` (number, required, default: `0.0`): Solar zenith in degrees
- `azimuth` (number, optional, default: `0.0`): Solar azimuth in degrees
- `output` (rasterDestination, required): Illumination Model
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.topo.corr

**Display Name:** i.topo.corr

**Description:** Computes topographic correction of reflectance.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (multilayer, required): Name of reflectance raster maps to be corrected topographically
- `basemap` (raster, required): Name of illumination input base raster map
- `zenith` (number, required, default: `0.0`): Solar zenith in degrees
- `method` (enum, optional, default: `0`): Topographic correction method
- `-s` (boolean, required, default: `False`): Scale output to input and copy color rules
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:i.vi

**Display Name:** i.vi

**Description:** Calculates different types of vegetation indices.

**Group:** Imagery (i.*)

**Parameters:**

- `red` (raster, optional): Name of input red channel surface reflectance map [0.0-1.0]
- `viname` (enum, required, default: `10`): Type of vegetation index
- `nir` (raster, optional): Name of input nir channel surface reflectance map [0.0-1.0]
- `green` (raster, optional): Name of input green channel surface reflectance map [0.0-1.0]
- `blue` (raster, optional): Name of input blue channel surface reflectance map [0.0-1.0]
- `band5` (raster, optional): Name of input 5th channel surface reflectance map [0.0-1.0]
- `band7` (raster, optional): Name of input 7th channel surface reflectance map [0.0-1.0]
- `soil_line_slope` (number, optional): Value of the slope of the soil line (MSAVI2 only)
- `soil_line_intercept` (number, optional): Value of the factor of reduction of soil noise (MSAVI2 only)
- `soil_noise_reduction` (number, optional): Value of the slope of the soil line (MSAVI2 only)
- `storage_bit` (enum, optional, default: `1`): Maximum bits for digital numbers
- `output` (rasterDestination, required): Vegetation Index
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:i.zc

**Display Name:** i.zc

**Description:** Zero-crossing "edge detection" raster function for image processing.

**Group:** Imagery (i.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `width` (number, optional, default: `9.0`): x-y extent of the Gaussian filter
- `threshold` (number, optional, default: `10.0`): Sensitivity of Gaussian filter
- `orientations` (number, optional, default: `1.0`): Number of azimuth directions categorized
- `output` (rasterDestination, required): Zero crossing
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:m.cogo

**Display Name:** m.cogo

**Description:** A simple utility for converting bearing and distance measurements to coordinates and vice versa. It assumes a Cartesian coordinate system

**Group:** Miscellaneous (m.*)

**Parameters:**

- `input` (file, required): Name of input file
- `output` (fileDestination, required): Output text file
- `coordinates` (point, required, default: `0.0,0.0`): Starting coordinate pair
- `-l` (boolean, required, default: `False`): Lines are labelled
- `-q` (boolean, required, default: `False`): Suppress warnings
- `-r` (boolean, required, default: `False`): Convert from coordinates to bearing and distance
- `-c` (boolean, required, default: `False`): Repeat the starting coordinate at the end to close a loop
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:nviz

**Display Name:** nviz

**Description:** Visualization and animation tool for GRASS data.

**Group:** Visualization(NVIZ)

**Parameters:**

- `elevation` (multilayer, required): Name of elevation raster map
- `color` (multilayer, required): Name of raster map(s) for Color
- `vector` (multilayer, required): Name of vector lines/areas overlay map(s)
- `point` (multilayer, optional): Name of vector points overlay file(s)
- `volume` (multilayer, optional): Name of existing 3d raster map
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:r.basins.fill

**Display Name:** r.basins.fill

**Description:** Generates watershed subbasins raster map.

**Group:** Raster (r.*)

**Parameters:**

- `cnetwork` (raster, required): Input coded stream network raster layer
- `tnetwork` (raster, required): Input thinned ridge network raster layer
- `number` (number, required, default: `1.0`): Number of passes through the dataset
- `output` (rasterDestination, required): Watersheds
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.blend.combine

**Display Name:** r.blend.combine

**Description:** r.blend.combine - Blends color components of two raster maps by a given ratio and export into a unique raster.

**Group:** Raster (r.*)

**Parameters:**

- `first` (raster, required): Name of first raster map for blending
- `second` (raster, required): Name of second raster map for blending
- `percent` (number, optional, default: `50.0`): Percentage weight of first map for color blending
- `output` (rasterDestination, required): Blended
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.blend.rgb

**Display Name:** r.blend.rgb

**Description:** r.blend.rgb - Blends color components of two raster maps by a given ratio and exports into three rasters.

**Group:** Raster (r.*)

**Parameters:**

- `first` (raster, required): Name of first raster map for blending
- `second` (raster, required): Name of second raster map for blending
- `percent` (number, optional, default: `50.0`): Percentage weight of first map for color blending
- `output_red` (rasterDestination, required): Blended Red
- `output_green` (rasterDestination, required): Blended Green
- `output_blue` (rasterDestination, required): Blended Blue
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.buffer

**Display Name:** r.buffer

**Description:** Creates a raster map layer showing buffer zones surrounding cells that contain non-NULL category values.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `distances` (string, required): Distance zone(s) (e.g. 100,200,300)
- `units` (enum, required, default: `0`): Units of distance
- `-z` (boolean, required, default: `False`): Ignore zero (0) data cells instead of NULL cells
- `output` (rasterDestination, required): Buffer
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.buffer.lowmem

**Display Name:** r.buffer.lowmem

**Description:** Creates a raster map layer showing buffer zones surrounding cells that contain non-NULL category values (low-memory alternative).

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `distances` (string, required): Distance zone(s) (e.g. 100,200,300)
- `units` (enum, required, default: `0`): Units of distance
- `-z` (boolean, required, default: `False`): Ignore zero (0) data cells instead of NULL cells
- `output` (rasterDestination, required): Buffer
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.carve

**Display Name:** r.carve

**Description:** Takes vector stream data, transforms it to raster and subtracts depth from the output DEM.

**Group:** Raster (r.*)

**Parameters:**

- `raster` (raster, required): Elevation
- `vector` (source, required): Vector layer containing stream(s)
- `width` (number, optional): Stream width (in meters). Default is raster cell width
- `depth` (number, optional): Additional stream depth (in meters)
- `-n` (boolean, required, default: `False`): No flat areas allowed in flow direction
- `output` (rasterDestination, required): Modified elevation
- `points` (vectorDestination, required): Adjusted stream points
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.category

**Display Name:** r.category

**Description:** Manages category values and labels associated with user-specified raster map layers.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map
- `separator` (string, optional, default: `tab`): Field separator (Special characters: pipe, comma, space, tab, newline)
- `rules` (file, optional): File containing category label rules
- `txtrules` (string, optional): Inline category label rules
- `raster` (raster, optional): Raster map from which to copy category table
- `format` (string, optional): Default label or format string for dynamic labeling. Used when no explicit label exists for the category
- `coefficients` (string, optional): Dynamic label coefficients. Two pairs of category multiplier and offsets, for $1 and $2
- `output` (rasterDestination, required): Category
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.category.out

**Display Name:** r.category.out

**Description:** r.category.out - Exports category values and labels associated with user-specified raster map layers.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map
- `cats` (string, optional): Category values (for Integer rasters). Example: 1,3,7-9,13
- `values` (string, optional): Comma separated value list (for float rasters). Example: 1.4,3.8,13
- `separator` (string, optional, default: `tab`): Field separator (Special characters: pipe, comma, space, tab, newline)
- `html` (fileDestination, required): Category
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.circle

**Display Name:** r.circle

**Description:** Creates a raster map containing concentric rings around a given point.

**Group:** Raster (r.*)

**Parameters:**

- `coordinates` (point, required, default: `0,0`): The coordinate of the center (east,north)
- `min` (number, optional): Minimum radius for ring/circle map (in meters)
- `max` (number, optional): Maximum radius for ring/circle map (in meters)
- `multiplier` (number, optional): Data value multiplier
- `-b` (boolean, required, default: `False`): Generate binary raster map
- `output` (rasterDestination, required): Circles
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.clump

**Display Name:** r.clump

**Description:** Recategorizes data in a raster map by grouping cells that form physically discrete areas into unique categories.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input layer
- `title` (string, required): Title for output raster map
- `-d` (boolean, required, default: `False`): Clump also diagonal cells
- `output` (rasterDestination, required): Clumps
- `threshold` (number, required, default: `0.0`): Threshold to identify similar cells
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.coin

**Display Name:** r.coin

**Description:** Tabulates the mutual occurrence (coincidence) of categories for two raster map layers.

**Group:** Raster (r.*)

**Parameters:**

- `first` (raster, required): Name of first raster map
- `second` (raster, required): Name of second raster map
- `units` (enum, required): Unit of measure
- `-w` (boolean, required, default: `False`): Wide report, 132 columns (default: 80)
- `html` (fileDestination, required, default: `report.html`): Coincidence report
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.colors

**Display Name:** r.colors

**Description:** Creates/modifies the color table associated with a raster map.

**Group:** Raster (r.*)

**Parameters:**

- `map` (multilayer, required): Name of raster maps(s)
- `color` (enum, optional, default: `0`): Name of color table
- `rules_txt` (string, optional): Color rules
- `rules` (file, optional): Color rules file
- `raster` (raster, optional): Raster map from which to copy color table
- `-r` (boolean, required, default: `False`): Remove existing color table
- `-w` (boolean, required, default: `False`): Only write new color table if it does not already exist
- `-n` (boolean, required, default: `False`): Invert colors
- `-g` (boolean, required, default: `False`): Logarithmic scaling
- `-a` (boolean, required, default: `False`): Logarithmic-absolute scaling
- `-e` (boolean, required, default: `False`): Histogram equalization
- `output_dir` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.colors.out

**Display Name:** r.colors.out

**Description:** Exports the color table associated with a raster map.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map
- `-p` (boolean, optional, default: `False`): Output values as percentages
- `rules` (fileDestination, required): Color Table
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.colors.stddev

**Display Name:** r.colors.stddev

**Description:** Sets color rules based on stddev from a raster map's mean value.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map
- `-b` (boolean, required, default: `False`): Color using standard deviation bands
- `-z` (boolean, required, default: `False`): Force center at zero
- `output` (rasterDestination, required): Stddev Colors
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.composite

**Display Name:** r.composite

**Description:** Combines red, green and blue raster maps into a single composite raster map.

**Group:** Raster (r.*)

**Parameters:**

- `red` (raster, required): Red
- `green` (raster, required): Green
- `blue` (raster, required): Blue
- `levels` (number, optional, default: `32.0`): Number of levels to be used for each component
- `level_red` (number, optional): Number of levels to be used for <red>
- `level_green` (number, optional): Number of levels to be used for <green>
- `level_blue` (number, optional): Number of levels to be used for <blue>
- `-d` (boolean, required, default: `False`): Dither
- `-c` (boolean, required, default: `False`): Use closest color
- `output` (rasterDestination, required): Composite
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.contour

**Display Name:** r.contour

**Description:** Produces a vector map of specified contours from a raster map.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster
- `step` (number, optional): Increment between contour levels
- `levels` (string, optional): List of contour levels
- `minlevel` (number, optional): Minimum contour level
- `maxlevel` (number, optional): Maximum contour level
- `cut` (number, optional, default: `0.0`): Minimum number of points for a contour line (0 -> no limit)
- `output` (vectorDestination, required): Contours
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.cost

**Display Name:** r.cost

**Description:** Creates a raster layer of cumulative cost of moving across a raster layer whose cell values represent cost.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Unit cost layer
- `start_coordinates` (point, optional, default: ``): Coordinates of starting point(s) (E,N)
- `stop_coordinates` (point, optional, default: ``): Coordinates of stopping point(s) (E,N)
- `-k` (boolean, required, default: `False`): Use the 'Knight's move'; slower, but more accurate
- `-n` (boolean, required, default: `True`): Keep null values in output raster layer
- `start_points` (source, optional): Start points
- `stop_points` (source, optional): Stop points
- `start_raster` (raster, optional): Name of starting raster points map
- `max_cost` (number, optional, default: `0.0`): Maximum cumulative cost
- `null_cost` (number, optional): Cost assigned to null cells. By default, null cells are excluded
- `memory` (number, optional, default: `300.0`): Maximum memory to be used in MB
- `output` (rasterDestination, optional): Cumulative cost
- `nearest` (rasterDestination, optional): Cost allocation map
- `outdir` (rasterDestination, optional): Movement directions
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:r.covar

**Display Name:** r.covar

**Description:** Outputs a covariance/correlation matrix for user-specified raster layer(s).

**Group:** Raster (r.*)

**Parameters:**

- `map` (multilayer, required): Input layers
- `-r` (boolean, required, default: `True`): Print correlation matrix
- `html` (fileDestination, required, default: `report.html`): Covariance report
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.cross

**Display Name:** r.cross

**Description:** Creates a cross product of the category values from multiple raster map layers.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Input raster layers
- `-z` (boolean, required, default: `False`): Non-zero data only
- `output` (rasterDestination, required): Cross product
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.describe

**Display Name:** r.describe

**Description:** Prints terse list of category values found in a raster layer.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): input raster layer
- `null_value` (string, optional, default: `*`): String representing NULL value
- `nsteps` (number, optional, default: `255.0`): Number of quantization steps
- `-r` (boolean, required, default: `False`): Only print the range of the data
- `-n` (boolean, required, default: `False`): Suppress reporting of any NULLs
- `-d` (boolean, required, default: `False`): Use the current region
- `-i` (boolean, required, default: `False`): Read floating-point map as integer
- `html` (fileDestination, required, default: `report.html`): Categories
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.distance

**Display Name:** r.distance

**Description:** Locates the closest points between objects in two raster maps.

**Group:** Raster (r.*)

**Parameters:**

- `map` (multilayer, required): Name of two input raster for computing inter-class distances
- `separator` (string, optional, default: `:`): Field separator (Special characters: pipe, comma, space, tab, newline)
- `sort` (enum, required, default: `0`): Sort output by distance
- `-l` (boolean, optional, default: `False`): Include category labels in the output
- `-o` (boolean, optional, default: `False`): Report zero distance if rasters are overlapping
- `-n` (boolean, optional, default: `False`): Report null objects as *
- `html` (fileDestination, required): Distance
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.drain

**Display Name:** r.drain

**Description:** Traces a flow through an elevation model on a raster map.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Elevation
- `direction` (raster, optional): Name of input movement direction map associated with the cost surface
- `start_coordinates` (point, optional): Map coordinates of starting point(s) (E,N)
- `start_points` (source, optional): Vector layer containing starting point(s)
- `-c` (boolean, required, default: `False`): Copy input cell values on output
- `-a` (boolean, required, default: `False`): Accumulate input values along the path
- `-n` (boolean, required, default: `False`): Count cell numbers along the path
- `-d` (boolean, required, default: `False`): The input raster map is a cost surface (direction surface must also be specified)
- `output` (rasterDestination, required): Least cost path
- `drain` (vectorDestination, required): Drain
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.fill.dir

**Display Name:** r.fill.dir

**Description:** Filters and generates a depressionless elevation layer and a flow direction layer from a given elevation raster layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Elevation
- `format` (enum, optional, default: `0`): Output aspect direction format
- `-f` (boolean, required, default: `False`): Find unresolved areas only
- `output` (rasterDestination, required): Depressionless DEM
- `direction` (rasterDestination, required): Flow direction
- `areas` (rasterDestination, required): Problem areas
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.fill.stats

**Display Name:** r.fill.stats

**Description:** Rapidly fills 'no data' cells (NULLs) of a raster map with interpolated values (IDW).

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer with data gaps to fill
- `-k` (boolean, required, default: `False`): Preserve original cell values (By default original values are smoothed)
- `mode` (enum, required, default: `0`): Statistic for interpolated cell values
- `-m` (boolean, required, default: `False`): Interpret distance as map units, not number of cells (Do not select with geodetic coordinates)
- `distance` (number, optional, default: `3.0`): Distance threshold (default: in cells) for interpolation
- `minimum` (number, optional): Minimum input data value to include in interpolation
- `maximum` (number, optional): Maximum input data value to include in interpolation
- `power` (number, optional, default: `2.0`): Power coefficient for IDW interpolation
- `cells` (number, optional, default: `8.0`): Minimum number of data cells within search radius
- `output` (rasterDestination, required): Output Map
- `uncertainty` (rasterDestination, optional): Uncertainty Map
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.fillnulls

**Display Name:** r.fillnulls

**Description:** Fills no-data areas in raster maps using spline interpolation.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer to fill
- `method` (enum, required, default: `2`): Interpolation method to use
- `tension` (number, optional, default: `40.0`): Spline tension parameter
- `smooth` (number, optional, default: `0.1`): Spline smoothing parameter
- `edge` (number, optional, default: `3.0`): Width of hole edge used for interpolation (in cells)
- `npmin` (number, optional, default: `600.0`): Minimum number of points for approximation in a segment (>segmax)
- `segmax` (number, optional, default: `300.0`): Maximum number of points in a segment
- `lambda` (number, optional, default: `0.01`): Tykhonov regularization parameter (affects smoothing)
- `output` (rasterDestination, required): Filled
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.flow

**Display Name:** r.flow

**Description:** Construction of flowlines, flowpath lengths, and flowaccumulation (contributing areas) from a raster digital elevation model (DEM).

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation
- `aspect` (raster, optional): Aspect
- `barrier` (raster, optional): Barrier
- `skip` (number, optional): Number of cells between flowlines
- `bound` (number, optional): Maximum number of segments per flowline
- `-u` (boolean, required, default: `False`): Compute upslope flowlines instead of default downhill flowlines
- `-3` (boolean, required, default: `False`): 3-D lengths instead of 2-D
- `-m` (boolean, required, default: `False`): Use less memory, at a performance penalty
- `flowline` (vectorDestination, optional): Flow line
- `flowlength` (rasterDestination, required): Flow path length
- `flowaccumulation` (rasterDestination, required): Flow accumulation
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.geomorphon

**Display Name:** r.geomorphon

**Description:** Calculates geomorphons (terrain forms) and associated geometry using machine vision approach.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map
- `search` (number, optional, default: `3.0`): Outer search radius
- `skip` (number, optional, default: `0.0`): Inner search radius
- `flat` (number, optional, default: `1.0`): Flatness threshold (degrees)
- `dist` (number, optional, default: `0.0`): Flatness distance, zero for none
- `forms` (rasterDestination, required): Most common geomorphic forms
- `-m` (boolean, required, default: `False`): Use meters to define search units (default is cells)
- `-e` (boolean, required, default: `False`): Use extended form correction
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.grow

**Display Name:** r.grow

**Description:** Generates a raster layer with contiguous areas grown by one cell.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): input raster layer
- `radius` (number, optional, default: `1.01`): Radius of buffer in raster cells
- `metric` (enum, optional, default: `0`): Metric
- `old` (number, optional): Value to write for input cells which are non-NULL (-1 => NULL)
- `new` (number, optional): Value to write for "grown" cells
- `-m` (boolean, required, default: `False`): Radius is in map units rather than cells
- `output` (rasterDestination, required): Expanded
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.grow.distance

**Display Name:** r.grow.distance

**Description:** Generates a raster layer of distance to features in input layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input input raster layer
- `metric` (enum, optional, default: `0`): Metric
- `-m` (boolean, required, default: `False`): Output distances in meters instead of map units
- `-n` (boolean, required, default: `False`): Calculate distance to nearest NULL cell
- `distance` (rasterDestination, required): Distance
- `value` (rasterDestination, required): Value of nearest cell
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.gwflow

**Display Name:** r.gwflow

**Description:** Numerical calculation program for transient, confined and unconfined groundwater flow in two dimensions.

**Group:** Raster (r.*)

**Parameters:**

- `phead` (raster, required): The initial piezometric head in [m]
- `status` (raster, required): Boundary condition status, 0-inactive, 1-active, 2-dirichlet
- `hc_x` (raster, required): X-part of the hydraulic conductivity tensor in [m/s]
- `hc_y` (raster, required): Y-part of the hydraulic conductivity tensor in [m/s]
- `q` (raster, optional): Water sources and sinks in [m^3/s]
- `s` (raster, required): Specific yield in [1/m]
- `recharge` (raster, optional): Recharge map e.g: 6*10^-9 per cell in [m^3/s*m^2]
- `top` (raster, required): Top surface of the aquifer in [m]
- `bottom` (raster, required): Bottom surface of the aquifer in [m]
- `type` (enum, required, default: `0`): The type of groundwater flow
- `river_bed` (raster, optional): The height of the river bed in [m]
- `river_head` (raster, optional): Water level (head) of the river with leakage connection in [m]
- `river_leak` (raster, optional): The leakage coefficient of the river bed in [1/s]
- `drain_bed` (raster, optional): The height of the drainage bed in [m]
- `drain_leak` (raster, optional): The leakage coefficient of the drainage bed in [1/s]
- `dtime` (number, required, default: `86400.0`): The calculation time in seconds
- `maxit` (number, optional, default: `100000.0`): Maximum number of iteration used to solver the linear equation system
- `error` (number, optional, default: `1e-06`): Error break criteria for iterative solvers (jacobi, sor, cg or bicgstab)
- `solver` (enum, optional, default: `0`): The type of solver which should solve the symmetric linear equation system
- `relax` (string, required, default: `1`): The relaxation parameter used by the jacobi and sor solver for speedup or stabilizing
- `-f` (boolean, required, default: `False`): Allocate a full quadratic linear equation system, default is a sparse linear equation system
- `output` (rasterDestination, required): Groundwater flow
- `vx` (rasterDestination, required): Groundwater filter velocity vector part in x direction [m/s]
- `vy` (rasterDestination, required): Groundwater filter velocity vector part in y direction [m/s]
- `budget` (rasterDestination, required): Groundwater budget for each cell [m^3/s]
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.his

**Display Name:** r.his

**Description:** Generates red, green and blue raster layers combining hue, intensity and saturation (HIS) values from user-specified input raster layers.

**Group:** Raster (r.*)

**Parameters:**

- `hue` (raster, required): Hue
- `intensity` (raster, required): Intensity
- `saturation` (raster, required): Saturation
- `bgcolor` (string, optional): Color to use instead of NULL values. Either a standard color name, R:G:B triplet, or "none"
- `-c` (boolean, required, default: `False`): Use colors from color tables for NULL values
- `red` (rasterDestination, required): Red
- `green` (rasterDestination, required): Green
- `blue` (rasterDestination, required): Blue
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.horizon

**Display Name:** r.horizon

**Description:** Horizon angle computation from a digital elevation model.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map
- `direction` (number, optional): Direction in which you want to know the horizon height
- `step` (number, optional): Angle step size for multidirectional horizon
- `start` (number, optional, default: `0.0`): Start angle for multidirectional horizon
- `end` (number, optional, default: `360.0`): End angle for multidirectional horizon
- `bufferzone` (number, optional): For horizon rasters, read from the DEM an extra buffer around the present region
- `e_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer eastward the present region
- `w_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer westward the present region
- `n_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer northward the present region
- `s_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer southward the present region
- `maxdistance` (number, optional): The maximum distance to consider when finding the horizon height
- `distance` (number, optional, default: `1.0`): Sampling distance step coefficient
- `-d` (boolean, required, default: `False`): Write output in degrees (default is radians)
- `-c` (boolean, required, default: `False`): Write output in compass orientation (default is CCW, East=0)
- `output` (folderDestination, required): Folder to get horizon rasters
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.horizon.height

**Display Name:** r.horizon.height

**Description:** r.horizon.height - Horizon angle computation from a digital elevation model.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map
- `coordinates` (point, required, default: `0,0`): Coordinate for which you want to calculate the horizon
- `direction` (number, optional): Direction in which you want to know the horizon height
- `step` (number, optional): Angle step size for multidirectional horizon
- `start` (number, optional, default: `0.0`): Start angle for multidirectional horizon
- `end` (number, optional, default: `360.0`): End angle for multidirectional horizon
- `bufferzone` (number, optional): For horizon rasters, read from the DEM an extra buffer around the present region
- `e_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer eastward the present region
- `w_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer westward the present region
- `n_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer northward the present region
- `s_buff` (number, optional): For horizon rasters, read from the DEM an extra buffer southward the present region
- `maxdistance` (number, optional): The maximum distance to consider when finding the horizon height
- `distance` (number, optional, default: `1.0`): Sampling distance step coefficient
- `-d` (boolean, required, default: `False`): Write output in degrees (default is radians)
- `-c` (boolean, required, default: `False`): Write output in compass orientation (default is CCW, East=0)
- `html` (fileDestination, required, default: `report.html`): Horizon
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.in.lidar

**Display Name:** r.in.lidar

**Description:** Creates a raster map from LAS LiDAR points using univariate statistics.

**Group:** Raster (r.*)

**Parameters:**

- `input` (file, required): LAS input file
- `method` (enum, optional, default: `5`): Statistic to use for raster values
- `type` (enum, optional, default: `1`): Storage type for resultant raster map
- `base_raster` (raster, optional): Subtract raster values from the Z coordinates
- `zrange` (range, optional): Filter range for z data (min, max)
- `zscale` (number, optional, default: `1.0`): Scale to apply to z data
- `intensity_range` (range, optional): Filter range for intensity values (min, max)
- `intensity_scale` (number, optional, default: `1.0`): Scale to apply to intensity values
- `percent` (number, optional, default: `100.0`): Percent of map to keep in memory
- `pth` (number, optional): pth percentile of the values (between 1 and 100)
- `trim` (number, optional): Discard <trim> percent of the smallest and <trim> percent of the largest observations (0-50)
- `resolution` (number, optional): Output raster resolution
- `return_filter` (string, optional): Only import points of selected return type Options: first, last, mid
- `class_filter` (string, optional): Only import points of selected class(es) (comma separated integers)
- `-e` (boolean, required, default: `False`): Use the extent of the input for the raster extent
- `-n` (boolean, required, default: `False`): Set computation region to match the new raster map
- `-o` (boolean, required, default: `False`): Override projection check (use current location's projection)
- `-i` (boolean, required, default: `False`): Use intensity values rather than Z values
- `-j` (boolean, required, default: `False`): Use Z values for filtering, but intensity values for statistics
- `-d` (boolean, required, default: `False`): Use base raster resolution instead of computational region
- `-v` (boolean, required, default: `False`): Use only valid points
- `output` (rasterDestination, required): Lidar Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.in.lidar.info

**Display Name:** r.in.lidar.info

**Description:** r.in.lidar.info - Extract information from LAS file

**Group:** Raster (r.*)

**Parameters:**

- `input` (file, required): LAS input file
- `html` (fileDestination, required, default: `report.html`): LAS information
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:r.info

**Display Name:** r.info

**Description:** Output basic information about a raster layer.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Raster layer
- `-r` (boolean, required, default: `False`): Print range only
- `-g` (boolean, required, default: `False`): Print raster array information in shell script style
- `-h` (boolean, required, default: `False`): Print raster history instead of info
- `-e` (boolean, required, default: `False`): Print extended metadata information in shell script style
- `html` (fileDestination, required, default: `report.html`): Basic information
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.kappa

**Display Name:** r.kappa

**Description:** Calculate error matrix and kappa parameter for accuracy assessment of classification result.

**Group:** Raster (r.*)

**Parameters:**

- `classification` (raster, required): Raster layer containing classification result
- `reference` (raster, required): Raster layer containing reference classes
- `title` (string, required, default: `ACCURACY ASSESSMENT`): Title for error matrix and kappa
- `-h` (boolean, required, default: `False`): No header in the report
- `-w` (boolean, required, default: `False`): Wide report (132 columns)
- `output` (fileDestination, required): Error matrix and kappa
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.lake

**Display Name:** r.lake

**Description:** Fills lake at given point to given level.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation
- `water_level` (number, required): Water level
- `coordinates` (point, optional, default: ``): Seed point coordinates
- `seed` (raster, optional): Raster layer with starting point(s) (at least 1 cell > 0)
- `-n` (boolean, required, default: `False`): Use negative depth values for lake raster layer
- `lake` (rasterDestination, required): Lake
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.latlong

**Display Name:** r.latlong

**Description:** Creates a latitude/longitude raster map.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `-l` (boolean, optional, default: `False`): Longitude output
- `output` (rasterDestination, required): LatLong
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.cwed

**Display Name:** r.li.cwed

**Description:** Calculates contrast weighted edge density index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `path` (file, required): Name of file that contains the weight to calculate the index
- `output` (rasterDestination, required): CWED
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.cwed.ascii

**Display Name:** r.li.cwed.ascii

**Description:** r.li.cwed.ascii - Calculates contrast weighted edge density index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `path` (file, required): Name of file that contains the weight to calculate the index
- `output_txt` (fileDestination, required): CWED
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.dominance

**Display Name:** r.li.dominance

**Description:** Calculates dominance's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Dominance
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.dominance.ascii

**Display Name:** r.li.dominance.ascii

**Description:** r.li.dominance.ascii - Calculates dominance's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Dominance
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.edgedensity

**Display Name:** r.li.edgedensity

**Description:** Calculates edge density index on a raster map, using a 4 neighbour algorithm

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `patch_type` (string, optional): The value of the patch type
- `-b` (boolean, required, default: `False`): Exclude border edges
- `output` (rasterDestination, required): Edge Density
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.edgedensity.ascii

**Display Name:** r.li.edgedensity.ascii

**Description:** r.li.edgedensity.ascii - Calculates edge density index on a raster map, using a 4 neighbour algorithm

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `patch_type` (string, optional): The value of the patch type
- `-b` (boolean, required, default: `False`): Exclude border edges
- `output_txt` (fileDestination, required): Edge Density
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.mpa

**Display Name:** r.li.mpa

**Description:** Calculates mean pixel attribute index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Mean Pixel Attribute
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.mpa.ascii

**Display Name:** r.li.mpa.ascii

**Description:** r.li.mpa.ascii - Calculates mean pixel attribute index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Mean Pixel Attribute
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.mps

**Display Name:** r.li.mps

**Description:** Calculates mean patch size index on a raster map, using a 4 neighbour algorithm

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Mean Patch Size
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.mps.ascii

**Display Name:** r.li.mps.ascii

**Description:** r.li.mps.ascii - Calculates mean patch size index on a raster map, using a 4 neighbour algorithm

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, required): Landscape structure configuration file
- `output_txt` (fileDestination, required): Mean Patch Size
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.padcv

**Display Name:** r.li.padcv

**Description:** Calculates coefficient of variation of patch area on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): PADCV
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.padcv.ascii

**Display Name:** r.li.padcv.ascii

**Description:** r.li.padcv.ascii - Calculates coefficient of variation of patch area on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): PADCV
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.padrange

**Display Name:** r.li.padrange

**Description:** Calculates range of patch area size on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Pad Range
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.padrange.ascii

**Display Name:** r.li.padrange.ascii

**Description:** r.li.padrange.ascii - Calculates range of patch area size on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Pad Range
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.padsd

**Display Name:** r.li.padsd

**Description:** Calculates standard deviation of patch area a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Patch Area SD
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.padsd.ascii

**Display Name:** r.li.padsd.ascii

**Description:** r.li.padsd.ascii - Calculates standard deviation of patch area a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Patch Area SD
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.patchdensity

**Display Name:** r.li.patchdensity

**Description:** Calculates patch density index on a raster map, using a 4 neighbour algorithm

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Patch Density
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.patchdensity.ascii

**Display Name:** r.li.patchdensity.ascii

**Description:** r.li.patchdensity.ascii - Calculates patch density index on a raster map, using a 4 neighbour algorithm

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Patch Density
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.patchnum

**Display Name:** r.li.patchnum

**Description:** Calculates patch number index on a raster map, using a 4 neighbour algorithm.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Patch Number
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.patchnum.ascii

**Display Name:** r.li.patchnum.ascii

**Description:** r.li.patchnum.ascii - Calculates patch number index on a raster map, using a 4 neighbour algorithm.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Patch Number
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.pielou

**Display Name:** r.li.pielou

**Description:** Calculates Pielou's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Pielou
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.pielou.ascii

**Display Name:** r.li.pielou.ascii

**Description:** r.li.pielou.ascii - Calculates Pielou's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Pielou
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.renyi

**Display Name:** r.li.renyi

**Description:** Calculates Renyi's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `alpha` (string, required): Alpha value is the order of the generalized entropy
- `output` (rasterDestination, required): Renyi
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.renyi.ascii

**Display Name:** r.li.renyi.ascii

**Description:** r.li.renyi.ascii - Calculates Renyi's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `alpha` (string, required): Alpha value is the order of the generalized entropy
- `output_txt` (fileDestination, required): Renyi
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.richness

**Display Name:** r.li.richness

**Description:** Calculates richness index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Richness
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.richness.ascii

**Display Name:** r.li.richness.ascii

**Description:** r.li.richness.ascii - Calculates richness index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Richness
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.shannon

**Display Name:** r.li.shannon

**Description:** Calculates Shannon's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Shannon
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.shannon.ascii

**Display Name:** r.li.shannon.ascii

**Description:** r.li.shannon.ascii - Calculates Shannon's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Shannon
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.shape

**Display Name:** r.li.shape

**Description:** Calculates shape index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Shape
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.shape.ascii

**Display Name:** r.li.shape.ascii

**Description:** r.li.shape.ascii - Calculates shape index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Shape
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.li.simpson

**Display Name:** r.li.simpson

**Description:** Calculates Simpson's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output` (rasterDestination, required): Simpson
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.li.simpson.ascii

**Display Name:** r.li.simpson.ascii

**Description:** r.li.simpson.ascii - Calculates Simpson's diversity index on a raster map

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `config_txt` (string, optional): Landscape structure configuration
- `config` (file, optional): Landscape structure configuration file
- `output_txt` (fileDestination, required): Simpson
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.mapcalc.simple

**Display Name:** r.mapcalc.simple

**Description:** Calculate new raster map from a r.mapcalc expression.

**Group:** Raster (r.*)

**Parameters:**

- `a` (raster, required): Raster layer A
- `b` (raster, optional): Raster layer B
- `c` (raster, optional): Raster layer C
- `d` (raster, optional): Raster layer D
- `e` (raster, optional): Raster layer E
- `f` (raster, optional): Raster layer F
- `expression` (string, required, default: `A*2`): Formula
- `output` (rasterDestination, required): Calculated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.mask.rast

**Display Name:** r.mask.rast

**Description:** r.mask.rast - Creates a MASK for limiting raster operation.

**Group:** Raster (r.*)

**Parameters:**

- `raster` (raster, required): Name of raster map to use as mask
- `input` (raster, required): Name of raster map to which apply the mask
- `maskcats` (string, optional, default: `*`): Raster values to use for mask. Format: 1 2 3 thru 7 *
- `-i` (boolean, optional, default: `False`): Create inverse mask
- `output` (rasterDestination, required): Masked
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.mask.vect

**Display Name:** r.mask.vect

**Description:** r.mask.vect - Creates a MASK for limiting raster operation with a vector layer.

**Group:** Raster (r.*)

**Parameters:**

- `vector` (source, required): Name of vector map to use as mask
- `input` (raster, required): Name of raster map to which apply the mask
- `cats` (string, optional): Category values. Example: 1,3,7-9,13
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `-i` (boolean, optional, default: `False`): Create inverse mask
- `output` (rasterDestination, required): Masked
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:r.mfilter

**Display Name:** r.mfilter

**Description:** Performs raster map matrix filter.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input layer
- `filter` (file, required): Filter file
- `repeat` (number, optional, default: `1.0`): Number of times to repeat the filter
- `-z` (boolean, required, default: `False`): Apply filter only to zero data values
- `output` (rasterDestination, required): Filtered
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.mode

**Display Name:** r.mode

**Description:** Finds the mode of values in a cover layer within areas assigned the same category value in a user-specified base layer.

**Group:** Raster (r.*)

**Parameters:**

- `base` (raster, required): Base layer to be reclassified
- `cover` (raster, required): Categories layer
- `output` (rasterDestination, required): Mode
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.neighbors

**Display Name:** r.neighbors

**Description:** Makes each cell category value a function of the category values assigned to the cells around it

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `selection` (raster, optional): Raster layer to select the cells which should be processed
- `method` (enum, optional, default: `0`): Neighborhood operation
- `size` (number, optional, default: `3.0`): Neighborhood size (must be odd)
- `gauss` (number, optional): Sigma (in cells) for Gaussian filter
- `quantile` (string, optional): Quantile to calculate for method=quantile
- `-c` (boolean, required, default: `False`): Use circular neighborhood
- `-a` (boolean, required, default: `False`): Do not align output with the input
- `weight` (file, optional): File containing weights
- `output` (rasterDestination, required): Neighbors
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.null

**Display Name:** r.null

**Description:** Manages NULL-values of given raster map.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map for which to edit null values
- `setnull` (string, optional): List of cell values to be set to NULL
- `null` (number, optional): The value to replace the null value by
- `-f` (boolean, optional, default: `False`): Only do the work if the map is floating-point
- `-i` (boolean, optional, default: `False`): Only do the work if the map is integer
- `-n` (boolean, optional, default: `False`): Only do the work if the map doesn't have a NULL-value bitmap file
- `-c` (boolean, optional, default: `False`): Create NULL-value bitmap file validating all data cells
- `-r` (boolean, optional, default: `False`): Remove NULL-value bitmap file
- `output` (rasterDestination, required): NullRaster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.out.ascii

**Display Name:** r.out.ascii

**Description:** Export a raster layer into a GRASS ASCII text file

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster
- `precision` (number, optional): Number of significant digits
- `width` (number, optional): Number of values printed before wrapping a line (only SURFER or MODFLOW format)
- `null_value` (string, optional, default: `*`): String to represent null cell (GRASS grid only)
- `-s` (boolean, optional, default: `False`): Write SURFER (Golden Software) ASCII grid
- `-m` (boolean, optional, default: `False`): Write MODFLOW (USGS) ASCII array
- `-i` (boolean, optional, default: `False`): Force output of integer values
- `output` (fileDestination, required): GRASS Ascii
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.gridatb

**Display Name:** r.out.gridatb

**Description:** Exports GRASS raster map to GRIDATB.FOR map file (TOPMODEL)

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `output` (fileDestination, required): GRIDATB
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.mat

**Display Name:** r.out.mat

**Description:** Exports a GRASS raster to a binary MAT-File

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster
- `output` (fileDestination, required): MAT File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.mpeg

**Display Name:** r.out.mpeg

**Description:** Converts raster map series to MPEG movie

**Group:** Raster (r.*)

**Parameters:**

- `view1` (multilayer, required): Name of input raster map(s) for view no.1
- `view2` (multilayer, optional): Name of input raster map(s) for view no.2
- `view3` (multilayer, optional): Name of input raster map(s) for view no.3
- `view4` (multilayer, optional): Name of input raster map(s) for view no.4
- `quality` (number, optional, default: `3.0`): Quality factor (1 = highest quality, lowest compression)
- `output` (fileDestination, required): MPEG file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.png

**Display Name:** r.out.png

**Description:** Export a GRASS raster map as a non-georeferenced PNG image

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster
- `compression` (number, optional, default: `6.0`): Compression level of PNG file (0 = none, 1 = fastest, 9 = best)
- `-t` (boolean, optional, default: `False`): Make NULL cells transparent
- `-w` (boolean, optional, default: `False`): Output world file
- `output` (fileDestination, required): PNG File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.pov

**Display Name:** r.out.pov

**Description:** Converts a raster map layer into a height-field file for POV-Ray

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster
- `hftype` (number, optional, default: `0.0`): Height-field type (0=actual heights 1=normalized)
- `bias` (number, optional): Elevation bias
- `scale` (number, optional): Vertical scaling factor
- `output` (fileDestination, required): Name of output povray file (TGA height field file)
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.ppm

**Display Name:** r.out.ppm

**Description:** Converts a raster layer to a PPM image file at the pixel resolution of the currently defined region.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `-g` (boolean, required, default: `True`): Output greyscale instead of color
- `output` (fileDestination, required): PPM
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.ppm3

**Display Name:** r.out.ppm3

**Description:** Converts 3 GRASS raster layers (R,G,B) to a PPM image file

**Group:** Raster (r.*)

**Parameters:**

- `red` (raster, required): Name of raster map to be used for <red>
- `green` (raster, required): Name of raster map to be used for <green>
- `blue` (raster, required): Name of raster map to be used for <blue>
- `-c` (boolean, optional, default: `False`): Add comments to describe the region
- `output` (fileDestination, required): Name for new PPM file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.vrml

**Display Name:** r.out.vrml

**Description:** Export a raster layer to the Virtual Reality Modeling Language (VRML)

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation layer
- `color` (raster, required): Color layer
- `exaggeration` (number, optional, default: `1.0`): Vertical exaggeration
- `output` (fileDestination, required): VRML
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.vtk

**Display Name:** r.out.vtk

**Description:** Converts raster maps into the VTK-ASCII format

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Input raster
- `elevation` (raster, optional): Input elevation raster map
- `null` (number, optional, default: `-99999.99`): Value to represent no data cell
- `z` (number, optional, default: `0.0`): Constant elevation (if no elevation map is specified)
- `rgbmaps` (multilayer, optional): Three (r,g,b) raster maps to create RGB values
- `vectormaps` (multilayer, optional): Three (x,y,z) raster maps to create vector values
- `zscale` (number, optional, default: `1.0`): Scale factor for elevation
- `precision` (number, optional, default: `12.0`): Number of significant digits
- `-p` (boolean, optional, default: `False`): Create VTK point data instead of VTK cell data
- `-s` (boolean, optional, default: `False`): Use structured grid for elevation (not recommended)
- `-t` (boolean, optional, default: `False`): Use polydata-trianglestrips for elevation grid creation
- `-v` (boolean, optional, default: `False`): Use polydata-vertices for elevation grid creation
- `-o` (boolean, optional, default: `False`): Scale factor affects the origin (if no elevation map is given)
- `-c` (boolean, optional, default: `False`): Correct the coordinates to match the VTK-OpenGL precision
- `output` (fileDestination, required): VTK File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.out.xyz

**Display Name:** r.out.xyz

**Description:** Exports a raster map to a text file as x,y,z values based on cell centers

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Input raster(s)
- `separator` (string, optional, default: `pipe`): Field separator
- `-i` (boolean, optional, default: `False`): Include no data values
- `output` (fileDestination, required): XYZ File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.param.scale

**Display Name:** r.param.scale

**Description:** Extracts terrain parameters from a DEM.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `slope_tolerance` (number, optional, default: `1.0`): Slope tolerance that defines a 'flat' surface (degrees)
- `curvature_tolerance` (number, optional, default: `0.0001`): Curvature tolerance that defines 'planar' surface
- `size` (number, optional, default: `3.0`): Size of processing window (odd number only, max: 499)
- `method` (enum, optional, default: `0`): Morphometric parameter in 'size' window to calculate
- `exponent` (number, optional, default: `0.0`): Exponent for distance weighting (0.0-4.0)
- `zscale` (number, optional, default: `1.0`): Vertical scaling factor
- `-c` (boolean, required, default: `False`): Constrain model through central window cell
- `output` (rasterDestination, required): Morphometric parameter
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.patch

**Display Name:** r.patch

**Description:** Creates a composite raster layer by using one (or more) layer(s) to fill in areas of "no data" in another map layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Raster layers to be patched together
- `-z` (boolean, required, default: `False`): Use zero (0) for transparency instead of NULL
- `output` (rasterDestination, required): Patched
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.path

**Display Name:** r.path

**Description:** Traces paths from starting points following input directions.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input direction
- `format` (enum, required, default: `0`): Format of the input direction map
- `values` (raster, optional): Name of input raster values to be used for output
- `raster_path` (rasterDestination, required): Name for output raster path map
- `vector_path` (vectorDestination, required): Name for output vector path map
- `start_points` (source, required): Vector layer containing starting point(s)
- `-c` (boolean, required, default: `False`): Copy input cell values on output
- `-a` (boolean, required, default: `False`): Accumulate input values along the path
- `-n` (boolean, required, default: `False`): Count cell numbers along the path
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.path.coordinate.txt

**Display Name:** r.path.coordinate.txt

**Description:** r.path.coordinate.txt - Traces paths from starting points following input directions.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input direction
- `format` (enum, required, default: `0`): Format of the input direction map
- `values` (raster, optional): Name of input raster values to be used for output
- `raster_path` (rasterDestination, required): Name for output raster path map
- `vector_path` (vectorDestination, required): Name for output vector path map
- `start_coordinates` (point, required): Map coordinate of starting point (E,N)
- `-c` (boolean, required, default: `False`): Copy input cell values on output
- `-a` (boolean, required, default: `False`): Accumulate input values along the path
- `-n` (boolean, required, default: `False`): Count cell numbers along the path
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.plane

**Display Name:** r.plane

**Description:** Creates raster plane layer given dip (inclination), aspect (azimuth) and one point.

**Group:** Raster (r.*)

**Parameters:**

- `dip` (number, required, default: `0.0`): Dip of plane
- `azimuth` (number, required, default: `0.0`): Azimuth of the plane
- `easting` (number, required): Easting coordinate of a point on the plane
- `northing` (number, required): Northing coordinate of a point on the plane
- `elevation` (number, required): Elevation coordinate of a point on the plane
- `type` (enum, optional, default: `1`): Data type of resulting layer
- `output` (rasterDestination, required): Plane
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.profile

**Display Name:** r.profile

**Description:** Outputs the raster layer values lying on user-defined line(s).

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `coordinates` (string, optional, default: `0,0,1,1`): Profile coordinate pairs
- `resolution` (number, optional): Resolution along profile
- `null_value` (string, optional, default: `*`): Character to represent no data cell
- `file` (file, optional): Name of input file containing coordinate pairs
- `-g` (boolean, required, default: `False`): Output easting and northing in first two columns of four column output
- `-c` (boolean, required, default: `False`): Output RRR:GGG:BBB color values for each profile point
- `output` (fileDestination, required): Profile
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.proj

**Display Name:** r.proj

**Description:** Re-projects a raster layer to another coordinate reference system

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster to reproject
- `crs` (crs, required): New coordinate reference system
- `method` (enum, optional, default: `0`): Interpolation method to use
- `memory` (number, optional, default: `300.0`): Maximum memory to be used (in MB)
- `resolution` (number, optional): Resolution of output raster map
- `-n` (boolean, optional, default: `False`): Do not perform region cropping optimization
- `output` (rasterDestination, required): Reprojected raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.quant

**Display Name:** r.quant

**Description:** Produces the quantization file for a floating-point map.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Raster layer(s) to be quantized
- `basemap` (raster, optional): Base layer to take quant rules from
- `fprange` (range, optional): Floating point range: dmin,dmax
- `range` (range, optional): Integer range: min,max
- `-t` (boolean, required, default: `False`): Truncate floating point data
- `-r` (boolean, required, default: `False`): Round floating point data
- `output` (folderDestination, required): Quantized raster(s)
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:r.quantile

**Display Name:** r.quantile

**Description:** Compute quantiles using two passes.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `quantiles` (number, optional, default: `4.0`): Number of quantiles
- `percentiles` (string, optional): List of percentiles
- `bins` (number, optional, default: `1000000.0`): Number of bins to use
- `-r` (boolean, required, default: `False`): Generate recode rules based on quantile-defined intervals
- `file` (fileDestination, required, default: `report.html`): Quantiles
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.quantile.plain

**Display Name:** r.quantile.plain

**Description:** r.quantile.plain - Compute quantiles using two passes and save them as plain text.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `quantiles` (number, optional, default: `4.0`): Number of quantiles
- `percentiles` (string, optional): List of percentiles
- `bins` (number, optional, default: `1000000.0`): Number of bins to use
- `-r` (boolean, required, default: `False`): Generate recode rules based on quantile-defined intervals
- `file` (fileDestination, required, default: `report.txt`): Quantiles
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.random

**Display Name:** r.random

**Description:** Creates a raster layer and vector point map containing randomly located points.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `cover` (raster, required): Input cover raster layer
- `npoints` (number, required): The number of points to allocate
- `-z` (boolean, required, default: `False`): Generate points also for NULL category
- `-d` (boolean, required, default: `False`): Generate vector points as 3D points
- `-b` (boolean, required, default: `False`): Do not build topology
- `raster` (rasterDestination, required): Random raster
- `vector` (vectorDestination, required): Random vector
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.random.cells

**Display Name:** r.random.cells

**Description:** Generates random cell values with spatial dependence.

**Group:** Raster (r.*)

**Parameters:**

- `distance` (number, required, default: `0.0`): Maximum distance of spatial correlation (value(s) >= 0.0)
- `ncells` (number, optional): Maximum number of cells to be created
- `seed` (number, optional): Random seed (SEED_MIN >= value >= SEED_MAX) (default [random])
- `output` (rasterDestination, required): Random
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.random.surface

**Display Name:** r.random.surface

**Description:** Generates random surface(s) with spatial dependence.

**Group:** Raster (r.*)

**Parameters:**

- `distance` (number, optional, default: `0.0`): Maximum distance of spatial correlation
- `exponent` (number, optional, default: `1.0`): Distance decay exponent
- `flat` (number, optional, default: `0.0`): Distance filter remains flat before beginning exponent
- `seed` (number, optional): Random seed (SEED_MIN >= value >= SEED_MAX)
- `high` (number, optional, default: `255.0`): Maximum cell value of distribution
- `-u` (boolean, optional, default: `False`): Uniformly distributed cell values
- `output` (rasterDestination, required): Random_Surface
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.reclass

**Display Name:** r.reclass

**Description:** Creates a new map layer whose category values are based upon a reclassification of the categories in an existing raster map layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `rules` (file, optional): File containing reclass rules
- `txtrules` (string, optional): Reclass rules text (if rule file not used)
- `output` (rasterDestination, required): Reclassified
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.reclass.area

**Display Name:** r.reclass.area

**Description:** Reclassifies a raster layer, greater or less than user specified area size (in hectares)

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `value` (number, required, default: `1.0`): Value option that sets the area size limit [hectares]
- `mode` (enum, required, default: `0`): Lesser or greater than specified value
- `method` (enum, optional, default: `0`): Method used for reclassification
- `-c` (boolean, required, default: `False`): Input map is clumped
- `-d` (boolean, required, default: `False`): Clumps including diagonal neighbors
- `output` (rasterDestination, required): Reclassified
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.recode

**Display Name:** r.recode

**Description:** Recodes categorical raster maps.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input layer
- `rules` (file, required, default: `NoneFalse`): File containing recode rules
- `-d` (boolean, required, default: `False`): Force output to 'double' raster map type (DCELL)
- `-a` (boolean, required, default: `False`): Align the current region to the input raster map
- `output` (rasterDestination, required): Recoded
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.regression.line

**Display Name:** r.regression.line

**Description:** Calculates linear regression from two raster layers : y = a + b*x.

**Group:** Raster (r.*)

**Parameters:**

- `mapx` (raster, required): Layer for x coefficient
- `mapy` (raster, required): Layer for y coefficient
- `html` (fileDestination, required, default: `report.html`): Regression coefficients
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.regression.multi

**Display Name:** r.regression.multi

**Description:** Calculates multiple linear regression from raster maps.

**Group:** Raster (r.*)

**Parameters:**

- `mapx` (multilayer, required): Map(s) for x coefficient
- `mapy` (raster, required): Map for y coefficient
- `residuals` (rasterDestination, required): Residual Map
- `estimates` (rasterDestination, required): Estimates Map
- `html` (fileDestination, required, default: `report.html`): Regression coefficients
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.relief

**Display Name:** r.relief

**Description:** Creates shaded relief from an elevation layer (DEM).

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input elevation layer
- `altitude` (number, optional, default: `30.0`): Altitude of the sun in degrees above the horizon
- `azimuth` (number, optional, default: `270.0`): Azimuth of the sun in degrees to the east of north
- `zscale` (number, optional, default: `1.0`): Factor for exaggerating relief
- `scale` (number, optional, default: `1.0`): Scale factor for converting horizontal units to elevation units
- `units` (enum, optional, default: `0`): Elevation units (overrides scale factor)
- `output` (rasterDestination, required): Output shaded relief layer
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.relief.scaling

**Display Name:** r.relief.scaling

**Description:** r.relief.scaling - Creates shaded relief from an elevation layer (DEM).

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input elevation layer
- `altitude` (number, required, default: `30.0`): Altitude of the sun in degrees above the horizon
- `azimuth` (number, required, default: `270.0`): Azimuth of the sun in degrees to the east of north
- `zscale` (number, required, default: `1.0`): Factor for exaggerating relief
- `scale` (number, required, default: `1.0`): Scale factor for converting horizontal units to elevation units
- `units` (enum, required): Elevation units (overrides scale factor)
- `output` (rasterDestination, required): Output shaded relief layer
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.report

**Display Name:** r.report

**Description:** Reports statistics for raster layers.

**Group:** Raster (r.*)

**Parameters:**

- `map` (multilayer, required): Raster layer(s) to report on
- `units` (enum, optional, default: `1`): Units
- `null_value` (string, optional, default: `*`): Character representing no data cell value
- `page_length` (number, optional, default: `0.0`): Page length
- `page_width` (number, optional, default: `79.0`): Page width
- `nsteps` (number, optional, default: `255.0`): Number of fp subranges to collect stats from
- `sort` (enum, optional, default: `0`): Sort output statistics by cell counts
- `-h` (boolean, optional, default: `False`): Suppress page headers
- `-f` (boolean, optional, default: `False`): Use formfeeds between pages
- `-e` (boolean, optional, default: `False`): Scientific format
- `-n` (boolean, optional, default: `False`): Do not report no data cells
- `-a` (boolean, optional, default: `False`): Do not report cells where all maps have no data
- `-c` (boolean, optional, default: `False`): Report for cats floating-point ranges (floating-point maps only)
- `-i` (boolean, optional, default: `False`): Read floating-point map as integer (use map's quant rules)
- `output` (fileDestination, optional): Name for output file to hold the report
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.resamp.bspline

**Display Name:** r.resamp.bspline

**Description:** Performs bilinear or bicubic spline interpolation with Tykhonov regularization.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `mask` (raster, optional): Name of raster map to use for masking. Only cells that are not NULL and not zero are interpolated
- `method` (enum, required, default: `1`): Sampling interpolation method
- `ew_step` (number, optional): Length (float) of each spline step in the east-west direction
- `ns_step` (number, optional): Length (float) of each spline step in the north-south direction
- `lambda` (number, optional, default: `0.01`): Tykhonov regularization parameter (affects smoothing)
- `memory` (number, optional, default: `300.0`): Maximum memory to be used (in MB). Cache size for raster rows
- `-n` (boolean, optional, default: `False`): Only interpolate null cells in input raster map
- `-c` (boolean, optional, default: `False`): Find the best Tykhonov regularizing parameter using a "leave-one-out" cross validation method
- `output` (rasterDestination, required): Resampled BSpline
- `grid` (vectorDestination, required): Interpolation Grid
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.resamp.filter

**Display Name:** r.resamp.filter

**Description:** Resamples raster map layers using an analytic kernel.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `filter` (enum, required, default: `[0]`): Filter kernel(s)
- `radius` (string, optional): Filter radius for each filter (comma separated list of float if multiple)
- `x_radius` (string, optional): Filter radius (horizontal) for each filter (comma separated list of float if multiple)
- `y_radius` (string, optional): Filter radius (vertical) for each filter (comma separated list of float if multiple)
- `-n` (boolean, optional, default: `False`): Propagate NULLs
- `output` (rasterDestination, required): Resampled Filter
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.resamp.interp

**Display Name:** r.resamp.interp

**Description:** Resamples raster map to a finer grid using interpolation.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `method` (enum, optional, default: `1`): Sampling interpolation method
- `output` (rasterDestination, required): Resampled interpolated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.resamp.rst

**Display Name:** r.resamp.rst

**Description:** Reinterpolates using regularized spline with tension and smoothing.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Raster layer
- `smooth` (raster, optional): Input raster map containing smoothing
- `maskmap` (raster, optional): Input raster map to be used as mask
- `ew_res` (number, required): Desired east-west resolution
- `ns_res` (number, required): Desired north-south resolution
- `overlap` (number, optional, default: `3.0`): Rows/columns overlap for segmentation
- `zscale` (number, optional, default: `1.0`): Multiplier for z-values
- `tension` (number, optional, default: `40.0`): Spline tension value
- `theta` (number, optional): Anisotropy angle (in degrees counterclockwise from East)
- `scalex` (number, optional): Anisotropy scaling factor
- `-t` (boolean, required, default: `False`): Use dnorm independent tension
- `-d` (boolean, required, default: `False`): Output partial derivatives instead of topographic parameters
- `elevation` (rasterDestination, required): Resampled RST
- `slope` (rasterDestination, required): Slope raster
- `aspect` (rasterDestination, required): Aspect raster
- `pcurvature` (rasterDestination, required): Profile curvature raster
- `tcurvature` (rasterDestination, required): Tangential curvature raster
- `mcurvature` (rasterDestination, required): Mean curvature raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.resamp.stats

**Display Name:** r.resamp.stats

**Description:** Resamples raster layers to a coarser grid using aggregation.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `method` (enum, optional, default: `0`): Aggregation method
- `quantile` (number, optional, default: `0.5`): Quantile to calculate for method=quantile
- `-n` (boolean, required, default: `False`): Propagate NULLs
- `-w` (boolean, required, default: `False`): Weight according to area (slower)
- `output` (rasterDestination, required): Resampled aggregated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.resample

**Display Name:** r.resample

**Description:** GRASS raster map layer data resampling capability using nearest neighbors.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer 
- `output` (rasterDestination, required): Resampled NN
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.rescale

**Display Name:** r.rescale

**Description:** Rescales the range of category values in a raster layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `from` (range, optional): The input data range to be rescaled
- `to` (range, required): The output data range
- `output` (rasterDestination, required): Rescaled
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.rescale.eq

**Display Name:** r.rescale.eq

**Description:** Rescales histogram equalized the range of category values in a raster  layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `from` (range, optional): The input data range to be rescaled
- `to` (range, required): The output data range
- `output` (rasterDestination, required): Rescaled equalized
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.rgb

**Display Name:** r.rgb

**Description:** Splits a raster map into red, green and blue maps.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `red` (rasterDestination, required): Red
- `green` (rasterDestination, required): Green
- `blue` (rasterDestination, required): Blue
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.ros

**Display Name:** r.ros

**Description:** Generates rate of spread raster maps.

**Group:** Raster (r.*)

**Parameters:**

- `model` (raster, required): Raster map containing fuel models
- `moisture_1h` (raster, optional): Raster map containing the 1-hour fuel moisture (%)
- `moisture_10h` (raster, optional): Raster map containing the 10-hour fuel moisture (%)
- `moisture_100h` (raster, optional): Raster map containing the 100-hour fuel moisture (%)
- `moisture_live` (raster, required): Raster map containing live fuel moisture (%)
- `velocity` (raster, optional): Raster map containing midflame wind velocities (ft/min)
- `direction` (raster, optional): Name of raster map containing wind directions (degree)
- `slope` (raster, optional): Name of raster map containing slope (degree)
- `aspect` (raster, optional): Raster map containing aspect (degree, CCW from E)
- `elevation` (raster, optional): Raster map containing elevation (m, required for spotting)
- `base_ros` (rasterDestination, required): Base ROS
- `max_ros` (rasterDestination, required): Max ROS
- `direction_ros` (rasterDestination, required): Direction ROS
- `spotting_distance` (rasterDestination, required): Spotting Distance
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.series

**Display Name:** r.series

**Description:** Makes each output cell value a function of the values assigned to the corresponding cells in the input raster layers. Input rasters layers/bands must be separated in different data sources.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Input raster layer(s)
- `-n` (boolean, required, default: `False`): Propagate NULLs
- `method` (enum, optional, default: `[0]`): Aggregate operation
- `quantile` (string, optional): Quantile to calculate for method=quantile
- `weights` (string, optional): Weighting factor for each input map, default value is 1.0
- `range` (range, optional): Ignore values outside this range (lo,hi)
- `output` (rasterDestination, required): Aggregated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.series.accumulate

**Display Name:** r.series.accumulate

**Description:** Makes each output cell value an accumulation function of the values assigned to the corresponding cells in the input raster map layers.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Input raster layer(s)
- `lower` (raster, optional): Raster map specifying the lower accumulation limit
- `upper` (raster, optional): Raster map specifying the upper accumulation limit
- `method` (enum, required, default: `0`): This method will be applied to compute the accumulative values from the input maps
- `scale` (number, optional, default: `1.0`): Scale factor for input
- `shift` (number, optional, default: `0.0`): Shift factor for input
- `range` (range, optional): Ignore values outside this range (min,max)
- `limits` (range, optional, default: `10,30`): Lower and upper accumulation limits (lower,upper)
- `-n` (boolean, required, default: `False`): Propagate NULLs
- `-f` (boolean, required, default: `False`): Create a FCELL map (floating point single precision) as output
- `output` (rasterDestination, required): Accumulated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.series.interp

**Display Name:** r.series.interp

**Description:** Interpolates raster maps located (temporal or spatial) in between input raster maps at specific sampling positions.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Input raster layer(s)
- `datapos` (string, optional): Data point position for each input map
- `infile` (file, optional): Input file with one input raster map name and data point position per line, field separator between name and sample point is 'pipe'
- `output` (string, optional): Name for output raster map (comma separated list if multiple)
- `samplingpos` (string, optional): Sampling point position for each output map (comma separated list)
- `outfile` (file, optional): Input file with one output raster map name and sample point position per line, field separator between name and sample point is 'pipe'
- `method` (enum, optional, default: `0`): Interpolation method, currently only linear interpolation is supported
- `output_dir` (folderDestination, required): Interpolated rasters
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.shade

**Display Name:** r.shade

**Description:** Drapes a color raster over an shaded relief or aspect map.

**Group:** Raster (r.*)

**Parameters:**

- `shade` (raster, required): Name of shaded relief or aspect raster map
- `color` (raster, required): Name of raster to drape over relief raster map
- `brighten` (number, optional, default: `0.0`): Percent to brighten
- `bgcolor` (string, optional): Color to use instead of NULL values. Either a standard color name, R:G:B triplet, or "none"
- `-c` (boolean, required, default: `False`): Use colors from color tables for NULL values
- `output` (rasterDestination, required): Shaded
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.sim.sediment

**Display Name:** r.sim.sediment

**Description:** Sediment transport and erosion/deposition simulation using path sampling method (SIMWE).

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of the elevation raster map [m]
- `water_depth` (raster, required): Name of the water depth raster map [m]
- `dx` (raster, required): Name of the x-derivatives raster map [m/m]
- `dy` (raster, required): Name of the y-derivatives raster map [m/m]
- `detachment_coeff` (raster, required): Name of the detachment capacity coefficient raster map [s/m]
- `transport_coeff` (raster, required): Name of the transport capacity coefficient raster map [s]
- `shear_stress` (raster, required): Name of the critical shear stress raster map [Pa]
- `man` (raster, optional): Name of the Mannings n raster map
- `man_value` (number, optional, default: `0.1`): Name of the Mannings n value
- `observation` (source, optional): Sampling locations vector points
- `nwalkers` (number, optional): Number of walkers
- `niterations` (number, optional, default: `10.0`): Time used for iterations [minutes]
- `output_step` (number, optional, default: `2.0`): Time interval for creating output maps [minutes]
- `diffusion_coeff` (number, optional, default: `0.8`): Water diffusion constant
- `transport_capacity` (rasterDestination, required): Transport capacity [kg/ms]
- `tlimit_erosion_deposition` (rasterDestination, required): Transport limited erosion-deposition [kg/m2s]
- `sediment_concentration` (rasterDestination, required): Sediment concentration [particle/m3]
- `sediment_flux` (rasterDestination, required): Sediment flux [kg/ms]
- `erosion_deposition` (rasterDestination, required): Erosion-deposition [kg/m2s]
- `walkers_output` (vectorDestination, optional): Name of the output walkers vector points layer
- `logfile` (fileDestination, optional): Name for sampling points output text file.
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.sim.water

**Display Name:** r.sim.water

**Description:** Overland flow hydrologic simulation using path sampling method (SIMWE).

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of the elevation raster map [m]
- `dx` (raster, required): Name of the x-derivatives raster map [m/m]
- `dy` (raster, required): Name of the y-derivatives raster map [m/m]
- `rain` (raster, optional): Name of the rainfall excess rate (rain-infilt) raster map [mm/hr]
- `rain_value` (number, optional, default: `50.0`): Rainfall excess rate unique value [mm/hr]
- `infil` (raster, optional): Name of the runoff infiltration rate raster map [mm/hr]
- `infil_value` (number, optional, default: `0.0`): Runoff infiltration rate unique value [mm/hr]
- `man` (raster, optional): Name of the Mannings n raster map
- `man_value` (number, optional, default: `0.1`): Manning's n unique value
- `flow_control` (raster, optional): Name of the flow controls raster map (permeability ratio 0-1)
- `observation` (source, optional): Sampling locations vector points
- `nwalkers` (number, optional): Number of walkers, default is twice the number of cells
- `niterations` (number, optional, default: `10.0`): Time used for iterations [minutes]
- `output_step` (number, optional, default: `2.0`): Time interval for creating output maps [minutes]
- `diffusion_coeff` (number, optional, default: `0.8`): Water diffusion constant
- `hmax` (number, optional, default: `4.0`): Threshold water depth [m]
- `halpha` (number, optional, default: `4.0`): Diffusion increase constant
- `hbeta` (number, optional, default: `0.5`): Weighting factor for water flow velocity vector
- `-t` (boolean, required, default: `False`): Time-series output
- `depth` (rasterDestination, required): Water depth [m]
- `discharge` (rasterDestination, required): Water discharge [m3/s]
- `error` (rasterDestination, required): Simulation error [m]
- `walkers_output` (vectorDestination, optional): Name of the output walkers vector points layer
- `logfile` (fileDestination, optional): Name for sampling points output text file.
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.slope.aspect

**Display Name:** r.slope.aspect

**Description:** Generates raster layers of slope, aspect, curvatures and partial derivatives from a elevation raster layer.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation
- `format` (enum, optional, default: `0`): Format for reporting the slope
- `precision` (enum, optional, default: `0`): Type of output aspect and slope layer
- `-a` (boolean, required, default: `True`): Do not align the current region to the elevation layer
- `-e` (boolean, required, default: `False`): Compute output at edges and near NULL values
- `-n` (boolean, required, default: `False`): Create aspect as degrees clockwise from North (azimuth), with flat = -9999
- `zscale` (number, optional, default: `1.0`): Multiplicative factor to convert elevation units to meters
- `min_slope` (number, optional, default: `0.0`): Minimum slope val. (in percent) for which aspect is computed
- `slope` (rasterDestination, optional): Slope
- `aspect` (rasterDestination, optional): Aspect
- `pcurvature` (rasterDestination, optional): Profile curvature
- `tcurvature` (rasterDestination, optional): Tangential curvature
- `dx` (rasterDestination, optional): First order partial derivative dx (E-W slope)
- `dy` (rasterDestination, optional): First order partial derivative dy (N-S slope)
- `dxx` (rasterDestination, optional): Second order partial derivative dxx
- `dyy` (rasterDestination, optional): Second order partial derivative dyy
- `dxy` (rasterDestination, optional): Second order partial derivative dxy
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.solute.transport

**Display Name:** r.solute.transport

**Description:** Numerical calculation program for transient, confined and unconfined solute transport in two dimensions

**Group:** Raster (r.*)

**Parameters:**

- `c` (raster, required): The initial concentration in [kg/m^3]
- `phead` (raster, required): The piezometric head in [m]
- `hc_x` (raster, required): The x-part of the hydraulic conductivity tensor in [m/s]
- `hc_y` (raster, required): The y-part of the hydraulic conductivity tensor in [m/s]
- `status` (raster, required): The status for each cell, = 0 - inactive cell, 1 - active cell, 2 - dirichlet- and 3 - transfer boundary condition
- `diff_x` (raster, required): The x-part of the diffusion tensor in [m^2/s]
- `diff_y` (raster, required): The y-part of the diffusion tensor in [m^2/s]
- `q` (raster, optional): Groundwater sources and sinks in [m^3/s]
- `cin` (raster, optional): Concentration sources and sinks bounded to a water source or sink in [kg/s]
- `cs` (raster, required): Concentration of inner sources and inner sinks in [kg/s] (i.e. a chemical reaction)
- `rd` (raster, required): Retardation factor [-]
- `nf` (raster, required): Effective porosity [-]
- `top` (raster, required): Top surface of the aquifer in [m]
- `bottom` (raster, required): Bottom surface of the aquifer in [m]
- `dtime` (number, required, default: `86400.0`): Calculation time (in seconds)
- `maxit` (number, optional, default: `10000.0`): Maximum number of iteration used to solve the linear equation system
- `error` (number, optional, default: `1e-06`): Error break criteria for iterative solver
- `solver` (enum, required, default: `4`): The type of solver which should solve the linear equation system
- `relax` (number, optional, default: `1.0`): The relaxation parameter used by the jacobi and sor solver for speedup or stabilizing
- `al` (number, optional, default: `0.0`): The longitudinal dispersivity length. [m]
- `at` (number, optional, default: `0.0`): The transversal dispersivity length. [m]
- `loops` (number, optional, default: `1.0`): Use this number of time loops if the CFL flag is off. The timestep will become dt/loops.
- `stab` (enum, optional, default: `0`): Set the flow stabilizing scheme (full or exponential upwinding).
- `-c` (boolean, required, default: `False`): Use the Courant-Friedrichs-Lewy criteria for time step calculation
- `-f` (boolean, required, default: `False`): Use a full filled quadratic linear equation system, default is a sparse linear equation system.
- `output` (rasterDestination, required): Solute Transport
- `vx` (rasterDestination, optional): Calculate and store the groundwater filter velocity vector part in x direction [m/s]
- `vy` (rasterDestination, optional): Calculate and store the groundwater filter velocity vector part in y direction [m/s]
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.spread

**Display Name:** r.spread

**Description:** Simulates elliptically anisotropic spread.

**Group:** Raster (r.*)

**Parameters:**

- `base_ros` (raster, required): Raster map containing base ROS (cm/min)
- `max_ros` (raster, required): Raster map containing maximal ROS (cm/min)
- `direction_ros` (raster, required): Raster map containing directions of maximal ROS (degree)
- `start` (raster, required): Raster map containing starting sources
- `spotting_distance` (raster, optional): Raster map containing maximal spotting distance (m, required with -s)
- `wind_speed` (raster, optional): Raster map containing midflame wind speed (ft/min, required with -s)
- `fuel_moisture` (raster, optional): Raster map containing fine fuel moisture of the cell receiving a spotting firebrand (%, required with -s)
- `backdrop` (raster, optional): Name of raster map as a display backdrop
- `least_size` (enum, optional, default: `0`): Basic sampling window size needed to meet certain accuracy (3)
- `comp_dens` (number, optional, default: `0.5`): Sampling density for additional computing (range: 0.0 - 1.0 (0.5))
- `init_time` (number, optional, default: `0.0`): Initial time for current simulation (0) (min)
- `lag` (number, optional): Simulating time duration LAG (fill the region) (min)
- `-s` (boolean, required, default: `False`): Consider spotting effect (for wildfires)
- `-i` (boolean, required, default: `False`): Use start raster map values in output spread time raster map
- `output` (rasterDestination, required): Spread Time
- `x_output` (rasterDestination, required): X Back Coordinates
- `y_output` (rasterDestination, required): Y Back Coordinates
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.spreadpath

**Display Name:** r.spreadpath

**Description:** Recursively traces the least cost path backwards to cells from which the cumulative cost was determined.

**Group:** Raster (r.*)

**Parameters:**

- `x_input` (raster, required): x_input
- `y_input` (raster, required): y_input
- `coordinates` (point, optional, default: `0,0`): coordinate
- `output` (rasterDestination, required): Backward least cost
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.statistics

**Display Name:** r.statistics

**Description:** Calculates category or object oriented statistics.

**Group:** Raster (r.*)

**Parameters:**

- `base` (raster, required): Base raster layer
- `cover` (raster, required): Cover raster layer
- `method` (enum, optional, default: `0`): method
- `-c` (boolean, required, default: `False`): Cover values extracted from the category labels of the cover map
- `routput` (rasterDestination, required): Statistics
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.stats

**Display Name:** r.stats

**Description:** Generates area statistics for raster layers.

**Group:** Raster (r.*)

**Parameters:**

- `input` (multilayer, required): Name of input raster map
- `separator` (string, optional, default: `space`): Output field separator
- `null_value` (string, optional, default: `*`): String representing no data cell value
- `nsteps` (number, optional, default: `255.0`): Number of floating-point subranges to collect stats from
- `sort` (enum, required, default: `0`): Sort output statistics by cell counts
- `-1` (boolean, required, default: `True`): One cell (range) per line
- `-A` (boolean, required, default: `False`): Print averaged values instead of intervals
- `-a` (boolean, required, default: `False`): Print area totals
- `-c` (boolean, required, default: `False`): Print cell counts
- `-p` (boolean, required, default: `False`): Print APPROXIMATE percents (total percent may not be 100%)
- `-l` (boolean, required, default: `False`): Print category labels
- `-g` (boolean, required, default: `False`): Print grid coordinates (east and north)
- `-x` (boolean, required, default: `False`): Print x and y (column and row)
- `-r` (boolean, required, default: `False`): Print raw indexes of fp ranges (fp maps only)
- `-n` (boolean, required, default: `False`): Suppress reporting of any NULLs
- `-N` (boolean, required, default: `False`): Suppress reporting of NULLs when all values are NULL
- `-C` (boolean, required, default: `False`): Report for cats fp ranges (fp maps only)
- `-i` (boolean, required, default: `False`): Read fp map as integer (use map's quant rules)
- `html` (fileDestination, required, default: `report.html`): Statistics
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.stats.quantile.out

**Display Name:** r.stats.quantile.out

**Description:** r.stats.quantile.out - Compute category quantiles using two passes and output statistics

**Group:** Raster (r.*)

**Parameters:**

- `base` (raster, required): Name of base raster map
- `cover` (raster, required): Name of cover raster map
- `quantiles` (number, optional): Number of quantiles
- `percentiles` (string, optional): List of percentiles
- `bins` (number, optional, default: `1000.0`): Number of bins to use
- `-r` (boolean, required, default: `False`): Create reclass map with statistics as category labels
- `file` (fileDestination, required): Statistics File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.stats.quantile.rast

**Display Name:** r.stats.quantile.rast

**Description:** r.stats.quantile.rast - Compute category quantiles using two passes and output rasters.

**Group:** Raster (r.*)

**Parameters:**

- `base` (raster, required): Name of base raster map
- `cover` (raster, required): Name of cover raster map
- `quantiles` (number, optional): Number of quantiles
- `percentiles` (string, optional): List of percentiles
- `bins` (number, optional, default: `1000.0`): Number of bins to use
- `-r` (boolean, required, default: `False`): Create reclass map with statistics as category labels
- `output` (folderDestination, required): Output Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.stats.zonal

**Display Name:** r.stats.zonal

**Description:** Calculates category or object oriented statistics (accumulator-based statistics)

**Group:** Raster (r.*)

**Parameters:**

- `base` (raster, required): Base raster
- `cover` (raster, required): Cover raster
- `method` (enum, required, default: `0`): Method of object-based statistic
- `-c` (boolean, optional, default: `False`): Cover values extracted from the category labels of the cover map
- `-r` (boolean, optional, default: `False`): Create reclass map with statistics as category labels
- `output` (rasterDestination, required): Resultant raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.stream.extract

**Display Name:** r.stream.extract

**Description:** Stream network extraction

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Input map: elevation map
- `accumulation` (raster, optional): Input map: accumulation map
- `depression` (raster, optional): Input map: map with real depressions
- `threshold` (number, required, default: `1.0`): Minimum flow accumulation for streams
- `mexp` (number, optional, default: `0.0`): Montgomery exponent for slope
- `stream_length` (number, optional, default: `0.0`): Delete stream segments shorter than cells
- `d8cut` (number, optional): Use SFD above this threshold
- `memory` (number, optional, default: `300.0`): Maximum memory to be used (in MB)
- `stream_raster` (rasterDestination, optional): Unique stream ids (rast)
- `stream_vector` (vectorDestination, optional): Unique stream ids (vect)
- `direction` (rasterDestination, optional): Flow direction
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.sun.incidout

**Display Name:** r.sun.incidout

**Description:** r.sun.incidout - Solar irradiance and irradiation model ( for the set local time).

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation layer [meters]
- `aspect` (raster, required): Aspect layer [decimal degrees]
- `aspect_value` (number, optional, default: `270.0`): A single value of the orientation (aspect), 270 is south
- `slope` (raster, required): Name of the input slope raster map (terrain slope or solar panel inclination) [decimal degrees]
- `slope_value` (number, optional, default: `0.0`): A single value of inclination (slope)
- `linke` (raster, optional): Name of the Linke atmospheric turbidity coefficient input raster map
- `albedo` (raster, optional): Name of the ground albedo coefficient input raster map
- `albedo_value` (number, optional, default: `0.2`): A single value of the ground albedo coefficient
- `lat` (raster, optional): Name of input raster map containing latitudes [decimal degrees]
- `long` (raster, optional): Name of input raster map containing longitudes [decimal degrees]
- `coeff_bh` (raster, optional): Name of real-sky beam radiation coefficient input raster map
- `coeff_dh` (raster, optional): Name of real-sky diffuse radiation coefficient input raster map
- `horizon_basemap` (raster, optional): The horizon information input map basename
- `horizon_step` (number, optional): Angle step size for multidirectional horizon [degrees]
- `day` (number, required, default: `1.0`): No. of day of the year (1-365)
- `step` (number, optional, default: `0.5`): Time step when computing all-day radiation sums [decimal hours]
- `declination` (number, optional): Declination value (overriding the internally computed value) [radians]
- `distance_step` (number, optional, default: `1.0`): Sampling distance step coefficient (0.5-1.5)
- `npartitions` (number, optional, default: `1.0`): Read the input files in this number of chunks
- `civil_time` (number, optional): Civil time zone value, if none, the time will be local solar time
- `time` (number, required): Local (solar) time (decimal hours)
- `-p` (boolean, required, default: `False`): Do not incorporate the shadowing effect of terrain
- `-m` (boolean, required, default: `False`): Use the low-memory version of the program
- `incidout` (rasterDestination, optional): incidence angle raster map
- `beam_rad` (rasterDestination, optional): Beam irradiance [W.m-2]
- `diff_rad` (rasterDestination, optional): Diffuse irradiance [W.m-2]
- `refl_rad` (rasterDestination, optional): Ground reflected irradiance [W.m-2]
- `glob_rad` (rasterDestination, optional): Global (total) irradiance/irradiation [W.m-2]
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.sun.insoltime

**Display Name:** r.sun.insoltime

**Description:** r.sun.insoltime - Solar irradiance and irradiation model (daily sums).

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation layer [meters]
- `aspect` (raster, required): Aspect layer [decimal degrees]
- `aspect_value` (number, optional, default: `270.0`): A single value of the orientation (aspect), 270 is south
- `slope` (raster, required): Name of the input slope raster map (terrain slope or solar panel inclination) [decimal degrees]
- `slope_value` (number, optional, default: `0.0`): A single value of inclination (slope)
- `linke` (raster, optional): Name of the Linke atmospheric turbidity coefficient input raster map
- `albedo` (raster, optional): Name of the ground albedo coefficient input raster map
- `albedo_value` (number, optional, default: `0.2`): A single value of the ground albedo coefficient
- `lat` (raster, optional): Name of input raster map containing latitudes [decimal degrees]
- `long` (raster, optional): Name of input raster map containing longitudes [decimal degrees]
- `coeff_bh` (raster, optional): Name of real-sky beam radiation coefficient input raster map
- `coeff_dh` (raster, optional): Name of real-sky diffuse radiation coefficient input raster map
- `horizon_basemap` (raster, optional): The horizon information input map basename
- `horizon_step` (number, optional): Angle step size for multidirectional horizon [degrees]
- `day` (number, required, default: `1.0`): No. of day of the year (1-365)
- `step` (number, optional, default: `0.5`): Time step when computing all-day radiation sums [decimal hours]
- `declination` (number, optional): Declination value (overriding the internally computed value) [radians]
- `distance_step` (number, optional, default: `1.0`): Sampling distance step coefficient (0.5-1.5)
- `npartitions` (number, optional, default: `1.0`): Read the input files in this number of chunks
- `civil_time` (number, optional): Civil time zone value, if none, the time will be local solar time
- `-p` (boolean, required, default: `False`): Do not incorporate the shadowing effect of terrain
- `-m` (boolean, required, default: `False`): Use the low-memory version of the program
- `insol_time` (rasterDestination, optional): Insolation time [h] 
- `beam_rad` (rasterDestination, optional): Irradiation raster map [Wh.m-2.day-1]
- `diff_rad` (rasterDestination, optional): Irradiation raster map [Wh.m-2.day-1]
- `refl_rad` (rasterDestination, optional): Irradiation raster map [Wh.m-2.day-1]
- `glob_rad` (rasterDestination, optional): Irradiance/irradiation raster map [Wh.m-2.day-1]
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.sunhours

**Display Name:** r.sunhours

**Description:** Calculates solar elevation, solar azimuth, and sun hours.

**Group:** Raster (r.*)

**Parameters:**

- `year` (number, required, default: `2017.0`): Year
- `month` (number, optional, default: `1.0`): Month
- `day` (number, required, default: `1.0`): Day
- `hour` (number, optional, default: `12.0`): Hour
- `minute` (number, optional, default: `0.0`): Minutes
- `second` (number, optional, default: `0.0`): Seconds
- `-t` (boolean, required, default: `False`): Time is local sidereal time, not Greenwich standard time
- `-s` (boolean, required, default: `False`): Do not use SOLPOS algorithm of NREL
- `elevation` (rasterDestination, required): Solar Elevation Angle
- `azimuth` (rasterDestination, required): Solar Azimuth Angle
- `sunhour` (rasterDestination, required): Sunshine Hours
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.sunmask.datetime

**Display Name:** r.sunmask.datetime

**Description:** r.sunmask.datetime - Calculates cast shadow areas from sun position and elevation raster map.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation raster layer [meters]
- `year` (number, optional, default: `2000.0`): year
- `month` (number, optional, default: `1.0`): month
- `day` (number, optional, default: `1.0`): day
- `hour` (number, optional, default: `1.0`): hour
- `minute` (number, optional, default: `0.0`): minute
- `second` (number, optional, default: `0.0`): second
- `timezone` (number, optional, default: `0.0`): East positive, offset from GMT
- `east` (string, required, default: ``): Easting coordinate (point of interest)
- `north` (string, required, default: ``): Northing coordinate (point of interest)
- `-z` (boolean, required, default: `True`): Do not ignore zero elevation
- `-s` (boolean, required, default: `False`): Calculate sun position only and exit
- `output` (rasterDestination, required): Shadows
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.sunmask.position

**Display Name:** r.sunmask.position

**Description:** r.sunmask.position - Calculates cast shadow areas from sun position and elevation raster map.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation raster layer [meters]
- `altitude` (number, optional): Altitude of the sun in degrees above the horizon
- `azimuth` (number, optional): Azimuth of the sun in degrees from north
- `east` (string, required, default: `False`): Easting coordinate (point of interest)
- `north` (string, required, default: `False`): Northing coordinate (point of interest)
- `-z` (boolean, required, default: `True`): Do not ignore zero elevation
- `-s` (boolean, required, default: `False`): Calculate sun position only and exit
- `output` (rasterDestination, required): Shadows
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.surf.area

**Display Name:** r.surf.area

**Description:** Surface area estimation for rasters.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Input layer
- `vscale` (number, optional, default: `1.0`): Vertical scale
- `units` (enum, optional, default: `1`): Units
- `html` (fileDestination, required, default: `report.html`): Area
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.surf.contour

**Display Name:** r.surf.contour

**Description:** Surface generation program from rasterized contours.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Raster layer with rasterized contours
- `output` (rasterDestination, required): DTM from contours
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.surf.fractal

**Display Name:** r.surf.fractal

**Description:** Creates a fractal surface of a given fractal dimension.

**Group:** Raster (r.*)

**Parameters:**

- `dimension` (number, optional, default: `2.05`): Fractal dimension of surface (2 < D < 3)
- `number` (number, optional, default: `0.0`): Number of intermediate images to produce
- `output` (rasterDestination, required): Fractal Surface
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.surf.gauss

**Display Name:** r.surf.gauss

**Description:** Creates a raster layer of Gaussian deviates.

**Group:** Raster (r.*)

**Parameters:**

- `mean` (number, optional, default: `0.0`): Distribution mean
- `sigma` (number, optional, default: `1.0`): Standard deviation
- `output` (rasterDestination, required): Gaussian deviates
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.surf.idw

**Display Name:** r.surf.idw

**Description:** Surface interpolation utility for raster layers.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster layer
- `npoints` (number, optional, default: `12.0`): Number of interpolation points
- `-e` (boolean, required, default: `False`): Output is the interpolation error
- `output` (rasterDestination, required): Interpolated IDW
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.surf.random

**Display Name:** r.surf.random

**Description:** Produces a raster layer of uniform random deviates whose range can be expressed by the user.

**Group:** Raster (r.*)

**Parameters:**

- `min` (number, optional, default: `0.0`): Minimum random value
- `max` (number, optional, default: `100.0`): Maximum random value
- `-i` (boolean, required, default: `False`): Create an integer raster layer
- `output` (rasterDestination, required): Random
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.terraflow

**Display Name:** r.terraflow

**Description:** Flow computation for massive grids.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of elevation raster map
- `-s` (boolean, required, default: `False`): SFD (D8) flow (default is MFD)
- `d8cut` (number, optional): Routing using SFD (D8) direction
- `memory` (number, optional, default: `300.0`): Maximum memory to be used (in MB)
- `filled` (rasterDestination, required): Filled (flooded) elevation
- `direction` (rasterDestination, required): Flow direction
- `swatershed` (rasterDestination, required): Sink-watershed
- `accumulation` (rasterDestination, required): Flow accumulation
- `tci` (rasterDestination, required): Topographic convergence index (tci)
- `stats` (fileDestination, required): Runtime statistics
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.texture

**Display Name:** r.texture

**Description:** Generate images with textural features from a raster map.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `method` (enum, optional, default: `[0]`): Textural measurement method(s)
- `size` (number, optional, default: `3.0`): The size of moving window (odd and >= 3)
- `distance` (number, optional, default: `1.0`): The distance between two samples (>= 1)
- `-s` (boolean, required, default: `False`): Separate output for each angle (0, 45, 90, 135)
- `-a` (boolean, required, default: `False`): Calculate all textural measurements
- `output` (folderDestination, required): Texture files directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.thin

**Display Name:** r.thin

**Description:** Thins non-zero cells that denote linear features in a raster layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer to thin
- `iterations` (number, optional, default: `200.0`): Maximum number of iterations
- `output` (rasterDestination, required): Thinned
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.tile

**Display Name:** r.tile

**Description:** Splits a raster map into tiles

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map
- `width` (number, required, default: `1024.0`): Width of tiles (columns)
- `height` (number, required, default: `1024.0`): Height of tiles (rows)
- `overlap` (number, optional): Overlap of tiles
- `output` (folderDestination, required): Tiles Directory
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.tileset

**Display Name:** r.tileset

**Description:** Produces tilings of the source projection for use in the destination region and projection.

**Group:** Raster (r.*)

**Parameters:**

- `sourceproj` (crs, required): Source projection
- `sourcescale` (number, optional, default: `1.0`): Conversion factor from units to meters in source projection
- `destproj` (crs, optional): Destination projection
- `destscale` (number, optional, default: `1.0`): Conversion factor from units to meters in destination projection
- `maxcols` (number, optional, default: `1024.0`): Maximum number of columns for a tile in the source projection
- `maxrows` (number, optional, default: `1024.0`): Maximum number of rows for a tile in the source projection
- `overlap` (number, optional, default: `0.0`): Number of cells tiles should overlap in each direction
- `separator` (string, optional, default: `pipe`): Output field separator
- `-g` (boolean, required, default: `False`): Produces shell script output
- `-w` (boolean, required, default: `False`): Produces web map server query string output
- `html` (fileDestination, required): Tileset
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:r.to.vect

**Display Name:** r.to.vect

**Description:** Converts a raster into a vector layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input raster layer
- `type` (enum, required, default: `2`): Feature type
- `column` (string, optional, default: `value`): Name of attribute column to store value
- `-s` (boolean, required, default: `False`): Smooth corners of area features
- `-v` (boolean, required, default: `False`): Use raster values as categories instead of unique sequence
- `-z` (boolean, required, default: `False`): Write raster values as z coordinate
- `-b` (boolean, required, default: `False`): Do not build vector topology
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `output` (vectorDestination, required): Vectorized
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.topidx

**Display Name:** r.topidx

**Description:** Creates topographic index layer from elevation raster layer

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Input elevation layer
- `output` (rasterDestination, required): Topographic index
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.topmodel

**Display Name:** r.topmodel

**Description:** Simulates TOPMODEL which is a physically based hydrologic model.

**Group:** Raster (r.*)

**Parameters:**

- `parameters` (file, required): Name of TOPMODEL parameters file
- `topidxstats` (file, required): Name of topographic index statistics file
- `input` (file, required): Name of rainfall and potential evapotranspiration data file
- `timestep` (number, optional): Time step. Generate output for this time step
- `topidxclass` (number, optional): Topographic index class. Generate output for this topographic index class
- `output` (fileDestination, required): TOPMODEL output
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent

---

### grass:r.topmodel.topidxstats

**Display Name:** r.topmodel.topidxstats

**Description:** r.topmodel.topidxstats - Builds a TOPMODEL topographic index statistics file.

**Group:** Raster (r.*)

**Parameters:**

- `topidx` (raster, required): Name of input topographic index raster map
- `ntopidxclasses` (number, optional, default: `30.0`): Number of topographic index classes
- `outtopidxstats` (fileDestination, required): TOPMODEL topographic index statistics file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.transect

**Display Name:** r.transect

**Description:** Outputs raster map layer values lying along user defined transect line(s).

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Raster map to be queried
- `line` (string, required): Transect definition: east,north,azimuth,distance[,east,north,azimuth,distance,...]
- `null_value` (string, optional, default: `*`): String representing NULL value
- `-g` (boolean, required, default: `False`): Output easting and northing in first two columns of four column output
- `html` (fileDestination, required): Transect file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.univar

**Display Name:** r.univar

**Description:** Calculates univariate statistics from the non-null cells of a raster map.

**Group:** Raster (r.*)

**Parameters:**

- `map` (multilayer, required): Name of raster map(s)
- `zones` (raster, optional): Raster map used for zoning, must be of type CELL
- `percentile` (string, optional): Percentile to calculate (comma separated list if multiple) (requires extended statistics flag)
- `separator` (string, optional, default: `pipe`): Field separator. Special characters: pipe, comma, space, tab, newline
- `-e` (boolean, required, default: `False`): Calculate extended statistics
- `output` (fileDestination, required): Univariate results
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.uslek

**Display Name:** r.uslek

**Description:** Computes USLE Soil Erodibility Factor (K).

**Group:** Raster (r.*)

**Parameters:**

- `psand` (raster, required): Name of soil sand fraction raster map [0.0-1.0]
- `pclay` (raster, required): Name of soil clay fraction raster map [0.0-1.0]
- `psilt` (raster, required): Name of soil silt fraction raster map [0.0-1.0]
- `pomat` (raster, required): Name of soil organic matter raster map [0.0-1.0]
- `output` (rasterDestination, required): USLE R Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.usler

**Display Name:** r.usler

**Description:** Computes USLE R factor, Rainfall erosivity index.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of annual precipitation raster map [mm/year]
- `method` (enum, required, default: `0`): Name of USLE R equation
- `output` (rasterDestination, required): USLE R Raster
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.viewshed

**Display Name:** r.viewshed

**Description:** Computes the viewshed of a point on an elevation raster map.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Elevation
- `coordinates` (point, required, default: `0.0,0.0`): Coordinate identifying the viewing position
- `observer_elevation` (number, optional, default: `1.75`): Viewing elevation above the ground
- `target_elevation` (number, optional, default: `0.0`): Offset for target elevation above the ground
- `max_distance` (number, optional, default: `-1.0`): Maximum visibility radius. By default infinity (-1)
- `refraction_coeff` (number, optional, default: `0.14286`): Refraction coefficient
- `memory` (number, optional, default: `500.0`): Amount of memory to use in MB
- `-c` (boolean, required, default: `False`): Consider earth curvature (current ellipsoid)
- `-r` (boolean, required, default: `False`): Consider the effect of atmospheric refraction
- `-b` (boolean, required, default: `False`): Output format is invisible = 0, visible = 1
- `-e` (boolean, required, default: `False`): Output format is invisible = NULL, else current elev - viewpoint_elev
- `output` (rasterDestination, required): Intervisibility
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.volume

**Display Name:** r.volume

**Description:** Calculates the volume of data "clumps".

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Name of input raster map representing data that will be summed within clumps
- `clump` (raster, required): Clumps layer (preferably the output of r.clump)
- `-f` (boolean, required, default: `False`): Generate unformatted report
- `centroids` (vectorDestination, required): Centroids
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:r.walk.coords

**Display Name:** r.walk.coords

**Description:** r.walk.coords - Creates a raster map showing the anisotropic cumulative cost of moving between different geographic locations on an input raster map whose cell category values represent cost from a list of coordinates.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map
- `friction` (raster, required): Name of input raster map containing friction costs
- `start_coordinates` (string, required): Coordinates of starting point(s) (a list of E,N)
- `stop_coordinates` (string, optional): Coordinates of stopping point(s) (a list of E,N)
- `walk_coeff` (string, optional, default: `0.72,6.0,1.9998,-1.9998`): Coefficients for walking energy formula parameters a,b,c,d
- `lambda` (number, optional, default: `1.0`): Lambda coefficients for combining walking energy and friction cost
- `slope_factor` (number, optional, default: `-0.2125`): Slope factor determines travel energy cost per height step
- `max_cost` (number, optional, default: `0.0`): Maximum cumulative cost
- `null_cost` (number, optional): Cost assigned to null cells. By default, null cells are excluded
- `memory` (number, optional, default: `300.0`): Maximum memory to be used in MB
- `-k` (boolean, required, default: `False`): Use the 'Knight's move'; slower, but more accurate
- `-n` (boolean, required, default: `False`): Keep null values in output raster layer
- `output` (rasterDestination, required): Cumulative cost
- `outdir` (rasterDestination, required): Movement Directions
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.walk.points

**Display Name:** r.walk.points

**Description:** r.walk.points - Creates a raster map showing the anisotropic cumulative cost of moving between different geographic locations on an input raster map whose cell category values represent cost from point vector layers.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map
- `friction` (raster, required): Name of input raster map containing friction costs
- `start_points` (source, required): Start points
- `stop_points` (source, optional): Stop points
- `walk_coeff` (string, optional, default: `0.72,6.0,1.9998,-1.9998`): Coefficients for walking energy formula parameters a,b,c,d
- `lambda` (number, optional, default: `1.0`): Lambda coefficients for combining walking energy and friction cost
- `slope_factor` (number, optional, default: `-0.2125`): Slope factor determines travel energy cost per height step
- `max_cost` (number, optional, default: `0.0`): Maximum cumulative cost
- `null_cost` (number, optional): Cost assigned to null cells. By default, null cells are excluded
- `memory` (number, optional, default: `300.0`): Maximum memory to be used in MB
- `-k` (boolean, required, default: `False`): Use the 'Knight's move'; slower, but more accurate
- `-n` (boolean, required, default: `False`): Keep null values in output raster layer
- `output` (rasterDestination, required): Cumulative cost
- `outdir` (rasterDestination, required): Movement Directions
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:r.walk.rast

**Display Name:** r.walk.rast

**Description:** r.walk.rast - Creates a raster map showing the anisotropic cumulative cost of moving between different geographic locations on an input raster map whose cell category values represent cost from a raster.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Name of input elevation raster map
- `friction` (raster, required): Name of input raster map containing friction costs
- `start_raster` (raster, required): Name of starting raster points map (all non-NULL cells are starting points)
- `walk_coeff` (string, optional, default: `0.72,6.0,1.9998,-1.9998`): Coefficients for walking energy formula parameters a,b,c,d
- `lambda` (number, optional, default: `1.0`): Lambda coefficients for combining walking energy and friction cost
- `slope_factor` (number, optional, default: `-0.2125`): Slope factor determines travel energy cost per height step
- `max_cost` (number, optional, default: `0.0`): Maximum cumulative cost
- `null_cost` (number, optional): Cost assigned to null cells. By default, null cells are excluded
- `memory` (number, optional, default: `300.0`): Maximum memory to be used in MB
- `-k` (boolean, required, default: `False`): Use the 'Knight's move'; slower, but more accurate
- `-n` (boolean, required, default: `False`): Keep null values in output raster layer
- `output` (rasterDestination, required): Cumulative cost
- `outdir` (rasterDestination, required): Movement Directions
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.water.outlet

**Display Name:** r.water.outlet

**Description:** Watershed basin creation program.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Drainage direction raster
- `coordinates` (point, required, default: `0.0,0.0`): Coordinates of outlet point
- `output` (rasterDestination, required): Basin
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.watershed

**Display Name:** r.watershed

**Description:** Watershed basin analysis program.

**Group:** Raster (r.*)

**Parameters:**

- `elevation` (raster, required): Elevation
- `depression` (raster, optional): Locations of real depressions
- `flow` (raster, optional): Amount of overland flow per cell
- `disturbed_land` (raster, optional): Percent of disturbed land, for USLE
- `blocking` (raster, optional): Terrain blocking overland surface flow, for USLE
- `threshold` (number, optional): Minimum size of exterior watershed basin
- `max_slope_length` (number, optional): Maximum length of surface flow, for USLE
- `convergence` (number, optional, default: `5.0`): Convergence factor for MFD (1-10)
- `memory` (number, optional, default: `300.0`): Maximum memory to be used with -m flag (in MB)
- `-s` (boolean, required, default: `False`): Enable Single Flow Direction (D8) flow (default is Multiple Flow Direction)
- `-m` (boolean, required, default: `False`): Enable disk swap memory option (-m): Operation is slow
- `-4` (boolean, required, default: `False`): Allow only horizontal and vertical flow of water
- `-a` (boolean, required, default: `False`): Use positive flow accumulation even for likely underestimates
- `-b` (boolean, required, default: `False`): Beautify flat areas
- `accumulation` (rasterDestination, optional): Number of cells that drain through each cell
- `drainage` (rasterDestination, optional): Drainage direction
- `basin` (rasterDestination, optional): Unique label for each watershed basin
- `stream` (rasterDestination, optional): Stream segments
- `half_basin` (rasterDestination, optional): Half-basins
- `length_slope` (rasterDestination, optional): Slope length and steepness (LS) factor for USLE
- `slope_steepness` (rasterDestination, optional): Slope steepness (S) factor for USLE
- `tci` (rasterDestination, optional): Topographic index ln(a / tan(b))
- `spi` (rasterDestination, optional): Stream power index a * tan(b)
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)

---

### grass:r.what.color

**Display Name:** r.what.color

**Description:** Queries colors for a raster map layer.

**Group:** Raster (r.*)

**Parameters:**

- `input` (raster, required): Raster map to query colors
- `value` (string, optional): Values to query colors for (comma separated list)
- `format` (string, optional, default: `%d:%d:%d`): Output format (printf-style)
- `html` (fileDestination, required): Colors file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.what.coords

**Display Name:** r.what.coords

**Description:** r.what.coords - Queries raster maps on their category values and category labels on a point.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map
- `coordinates` (point, required, default: `0.0, 0.0`): Coordinates for query (east, north)
- `null_value` (string, optional, default: `*`): String representing NULL value
- `separator` (string, optional, default: `pipe`): Field separator. Special characters: pipe, comma, space, tab, newlineString representing NULL value
- `cache` (number, optional, default: `500.0`): Size of point cache
- `-n` (boolean, optional, default: `False`): Output header row
- `-f` (boolean, optional, default: `False`): Show the category labels of the grid cell(s)
- `-r` (boolean, optional, default: `False`): Output color values as RRR:GGG:BBB
- `-i` (boolean, optional, default: `False`): Output integer category values, not cell values
- `-c` (boolean, optional, default: `False`): Turn on cache reporting
- `output` (fileDestination, required): Raster Value File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)

---

### grass:r.what.points

**Display Name:** r.what.points

**Description:** r.what.points - Queries raster maps on their category values and category labels on a layer of points.

**Group:** Raster (r.*)

**Parameters:**

- `map` (raster, required): Name of raster map
- `points` (source, required): Name of vector points layer for query
- `null_value` (string, optional, default: `*`): String representing NULL value
- `separator` (string, optional, default: `pipe`): Field separator. Special characters: pipe, comma, space, tab, newline
- `cache` (number, optional, default: `500.0`): Size of point cache
- `-n` (boolean, optional, default: `False`): Output header row
- `-f` (boolean, optional, default: `False`): Show the category labels of the grid cell(s)
- `-r` (boolean, optional, default: `False`): Output color values as RRR:GGG:BBB
- `-i` (boolean, optional, default: `False`): Output integer category values, not cell values
- `-c` (boolean, optional, default: `False`): Turn on cache reporting
- `output` (fileDestination, required): Raster Values File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.buffer

**Display Name:** v.buffer

**Description:** Creates a buffer around vector features of given type.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `cats` (string, optional): Category values
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `type` (enum, optional, default: `[0, 1, 4]`): Input feature type
- `distance` (number, optional): Buffer distance in map units
- `minordistance` (number, optional): Buffer distance along minor axis in map units
- `angle` (number, optional, default: `0.0`): Angle of major axis in degrees
- `layer` (string, required, default: `-1`): Layer number or name ('-1' for all layers)
- `column` (field, optional): Name of column to use for buffer distances
- `scale` (number, optional, default: `1.0`): Scaling factor for attribute column values
- `tolerance` (number, optional, default: `0.01`): Maximum distance between theoretical arc and polygon segments as multiple of buffer
- `-s` (boolean, required, default: `False`): Make outside corners straight
- `-c` (boolean, required, default: `False`): Do not make caps at the ends of polylines
- `-t` (boolean, required, default: `False`): Transfer categories and attributes
- `output` (vectorDestination, required): Buffer
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.build.check

**Display Name:** v.build.check

**Description:** v.build.check - Checks for topological errors.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of vector map
- `error` (vectorDestination, required): Topological errors
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.build.polylines

**Display Name:** v.build.polylines

**Description:** Builds polylines from lines or boundaries.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `cats` (enum, optional, default: `0`): Category number mode
- `type` (enum, optional, default: `[0, 1]`): Input feature type
- `output` (vectorDestination, required): Polylines
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.class

**Display Name:** v.class

**Description:** Classifies attribute data, e.g. for thematic mapping.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Input vector layer
- `column` (field, required): Column name or expression
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `algorithm` (enum, required, default: `0`): Algorithm to use for classification
- `nbclasses` (number, required, default: `3.0`): Number of classes to define
- `-g` (boolean, required, default: `True`): Print only class breaks (without min and max)
- `html` (fileDestination, required, default: `report.html`): Classification
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.clean

**Display Name:** v.clean

**Description:** Toolset for cleaning topology of vector map.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Layer to clean
- `type` (enum, optional, default: `[0, 1, 2, 3, 4, 5, 6]`): Input feature type
- `tool` (enum, required, default: `[0]`): Cleaning tool
- `threshold` (string, optional): Threshold (comma separated for each tool)
- `-b` (boolean, required, default: `False`): Do not build topology for the output vector
- `-c` (boolean, required, default: `False`): Combine tools with recommended follow-up tools
- `output` (vectorDestination, required): Cleaned
- `error` (vectorDestination, required): Errors
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.cluster

**Display Name:** v.cluster

**Description:** Performs cluster identification

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input layer
- `distance` (number, optional): Maximum distance to neighbors
- `min` (number, optional): Minimum number of points to create a cluster
- `method` (enum, optional, default: `[0]`): Clustering method
- `-2` (boolean, required, default: `False`): Force 2D clustering
- `-b` (boolean, required, default: `False`): Do not build topology
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `output` (vectorDestination, required): Clustered
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.db.select

**Display Name:** v.db.select

**Description:** Prints vector map attributes

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Input vector map 
- `layer` (number, required, default: `1.0`): Layer Number
- `columns` (string, optional): Name of attribute column(s), comma separated
- `-c` (boolean, required, default: `False`): Do not include column names in output
- `separator` (string, optional, default: `,`): Output field separator
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `group` (string, optional): GROUP BY conditions of SQL statement without 'group by' keyword
- `vertical_separator` (string, optional): Output vertical record separator
- `null_value` (string, optional): Null value indicator
- `-v` (boolean, required, default: `False`): Vertical output (instead of horizontal)
- `-r` (boolean, required, default: `False`): Print minimal region extent of selected vector features instead of attributes
- `file` (fileDestination, required): Attributes
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.decimate

**Display Name:** v.decimate

**Description:** Decimates a point cloud

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector
- `zrange` (range, optional): Filter range for z data (min,max)
- `cats` (string, optional): Category values
- `skip` (number, optional): Throw away every n-th point
- `preserve` (number, optional): Preserve only every n-th point
- `offset` (number, optional): Skip first n points
- `limit` (number, optional): Copy only n points
- `zdiff` (number, optional): Minimal difference of z values
- `cell_limit` (number, optional): Preserve only n points per grid cell
- `-g` (boolean, optional, default: `False`): Apply grid-based decimation
- `-f` (boolean, optional, default: `False`): Use only first point in grid cell during grid-based decimation
- `-c` (boolean, optional, default: `False`): Only one point per cat in grid cell
- `-z` (boolean, optional, default: `False`): Use z in grid decimation
- `-x` (boolean, optional, default: `False`): Store only the coordinates, throw away categories
- `-b` (boolean, optional, default: `False`): Do not build topology
- `output` (vectorDestination, required): Output vector map
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.delaunay

**Display Name:** v.delaunay

**Description:** Creates a Delaunay triangulation from an input vector map containing points or centroids.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `-r` (boolean, required, default: `False`): Use only points in current region
- `-l` (boolean, required, default: `False`): Output triangulation as a graph (lines), not areas
- `output` (vectorDestination, required): Delaunay triangulation
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.dissolve

**Display Name:** v.dissolve

**Description:** Dissolves boundaries between adjacent areas sharing a common category number or attribute.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `column` (field, optional): Name of column used to dissolve common boundaries
- `output` (vectorDestination, required): Dissolved
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.distance

**Display Name:** v.distance

**Description:** Finds the nearest element in vector map 'to' for elements in vector map 'from'.

**Group:** Vector (v.*)

**Parameters:**

- `from` (source, required): 'from' vector map
- `from_type` (enum, optional, default: `[0, 1, 3]`): 'from' feature type
- `to` (source, required): 'to' vector map
- `to_type` (enum, optional, default: `[0, 1, 3]`): 'to' feature type
- `dmax` (number, optional, default: `-1.0`): Maximum distance or -1.0 for no limit
- `dmin` (number, optional, default: `-1.0`): Minimum distance or -1.0 for no limit
- `upload` (enum, required, default: `[0]`): 'upload': Values describing the relation between two nearest features
- `column` (field, required): Column name(s) where values specified by 'upload' option will be uploaded
- `to_column` (field, optional): Column name of nearest feature (used with upload=to_attr)
- `from_output` (vectorDestination, required): Nearest
- `output` (vectorDestination, required): Distance
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.drape

**Display Name:** v.drape

**Description:** Converts 2D vector features to 3D by sampling of elevation raster map.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `type` (enum, optional, default: `[0, 1, 3, 4]`): Input feature type
- `elevation` (raster, required): Elevation raster map for height extraction
- `method` (enum, optional, default: `0`): Sampling method
- `scale` (number, optional, default: `1.0`): Scale factor sampled raster values
- `null_value` (number, optional): Height for sampled raster NULL values
- `output` (vectorDestination, required): 3D vector
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.edit

**Display Name:** v.edit

**Description:** Edits a vector map, allows adding, deleting and modifying selected vector features.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of vector layer
- `type` (enum, optional, default: `[0, 1, 2, 3]`): Input feature type
- `tool` (enum, required, default: `0`): Tool
- `input` (file, optional): ASCII file for add tool
- `move` (string, optional): Difference in x,y,z direction for moving feature or vertex
- `threshold` (string, optional): Threshold distance (coords,snap,query)
- `ids` (string, optional): Feature ids
- `cats` (string, optional): Category values
- `coords` (string, optional): List of point coordinates
- `bbox` (extent, optional): Bounding box for selecting features
- `polygon` (string, optional): Polygon for selecting features
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `query` (enum, optional): Query tool
- `bgmap` (source, optional): Name of background vector map
- `snap` (enum, optional, default: `0`): Snap added or modified features in the given threshold to the nearest existing feature
- `zbulk` (string, optional): Starting value and step for z bulk-labeling. Pair: value,step (e.g. 1100,10)
- `-r` (boolean, required, default: `False`): Reverse selection
- `-c` (boolean, required, default: `False`): Close added boundaries (using threshold distance)
- `-n` (boolean, required, default: `False`): Do not expect header of input data
- `-b` (boolean, required, default: `False`): Do not build topology
- `-1` (boolean, required, default: `False`): Modify only first found feature in bounding box
- `output` (vectorDestination, required): Edited
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.extract

**Display Name:** v.extract

**Description:** Selects vector objects from a vector layer and creates a new layer containing only the selected objects.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Vector layer
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `type` (enum, optional, default: `[0, 1, 3, 4, 5, 6]`): Input feature type
- `file` (file, optional): Input text file with category numbers/number ranges to be extracted
- `random` (number, optional): Number of random categories matching vector objects to extract
- `new` (number, optional, default: `-1.0`): Desired new category value (enter -1 to keep original categories)
- `-d` (boolean, required, default: `True`): Dissolve common boundaries
- `-t` (boolean, required, default: `False`): Do not copy attributes
- `-r` (boolean, required, default: `False`): Reverse selection
- `output` (vectorDestination, required): Selected
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.extrude

**Display Name:** v.extrude

**Description:** Extrudes flat vector object to 3D with defined height.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input 2D vector map
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `type` (enum, optional, default: `[0, 1, 2]`): Input feature type
- `zshift` (number, optional, default: `0.0`): Shifting value for z coordinates
- `height` (number, optional): Fixed height for 3D vector objects
- `height_column` (field, optional): Name of attribute column with object heights
- `elevation` (raster, optional): Elevation raster for height extraction
- `method` (enum, optional, default: `0`): Sampling interpolation method
- `scale` (number, optional, default: `1.0`): Scale factor sampled raster values
- `null_value` (number, optional): Height for sampled raster NULL values
- `-t` (boolean, required, default: `False`): Trace elevation
- `output` (vectorDestination, required): 3D Vector
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.generalize

**Display Name:** v.generalize

**Description:** Vector based generalization.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input layer
- `type` (enum, optional, default: `[0, 1, 2]`): Input feature type
- `cats` (string, optional): Category values
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `method` (enum, required, default: `0`): Generalization algorithm
- `threshold` (number, required, default: `1.0`): Maximal tolerance value
- `look_ahead` (number, optional, default: `7.0`): Look-ahead parameter
- `reduction` (number, optional, default: `50.0`): Percentage of the points in the output of 'douglas_reduction' algorithm
- `slide` (number, optional, default: `0.5`): Slide of computed point toward the original point
- `angle_thresh` (number, optional, default: `3.0`): Minimum angle between two consecutive segments in Hermite method
- `degree_thresh` (number, optional, default: `0.0`): Degree threshold in network generalization
- `closeness_thresh` (number, optional, default: `0.0`): Closeness threshold in network generalization
- `betweeness_thresh` (number, optional, default: `0.0`): Betweenness threshold in network generalization
- `alpha` (number, optional, default: `1.0`): Snakes alpha parameter
- `beta` (number, optional, default: `1.0`): Snakes beta parameter
- `iterations` (number, optional, default: `1.0`): Number of iterations
- `-t` (boolean, required, default: `False`): Do not copy attributes
- `-l` (boolean, required, default: `True`): Disable loop support
- `output` (vectorDestination, required): Generalized
- `error` (vectorDestination, required): Errors
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.hull

**Display Name:** v.hull

**Description:** Produces a convex hull for a given vector map.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input layer
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `-f` (boolean, required, default: `False`): Create a 'flat' 2D hull even if the input is 3D points
- `output` (vectorDestination, required): Convex hull
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.ascii

**Display Name:** v.in.ascii

**Description:** Creates a vector map from an ASCII points file or ASCII vector file.

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): ASCII file to be imported
- `format` (enum, optional, default: `0`): Input file format
- `separator` (string, optional, default: `pipe`): Field separator
- `text` (string, optional): Text delimiter
- `skip` (number, optional, default: `0.0`): Number of header lines to skip at top of input file
- `columns` (string, optional): Column definition in SQL style (example: 'x double precision, y double precision, cat int, name varchar(10)')
- `x` (number, optional, default: `1.0`): Number of column used as x coordinate
- `y` (number, optional, default: `2.0`): Number of column used as y coordinate
- `z` (number, optional, default: `0.0`): Number of column used as z coordinate
- `cat` (number, optional, default: `0.0`): Number of column used as category
- `-z` (boolean, required, default: `False`): Create 3D vector map
- `-n` (boolean, required, default: `False`): Do not expect a header when reading in standard format
- `-t` (boolean, required, default: `False`): Do not create table in points mode
- `-b` (boolean, required, default: `False`): Do not build topology in points mode
- `-r` (boolean, required, default: `False`): Only import points falling within current region (points mode)
- `-i` (boolean, required, default: `False`): Ignore broken line(s) in points mode
- `output` (vectorDestination, required): ASCII
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.dxf

**Display Name:** v.in.dxf

**Description:** Converts files in DXF format to GRASS vector map format.

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): Name of input DXF file
- `layers` (string, optional): List of layers to import
- `-e` (boolean, required, default: `True`): Ignore the map extent of DXF file
- `-t` (boolean, required, default: `False`): Do not create attribute tables
- `-f` (boolean, required, default: `True`): Import polyface meshes as 3D wire frame
- `-l` (boolean, required, default: `False`): List available layers and exit
- `-i` (boolean, required, default: `False`): Invert selection by layers (don't import layers in list)
- `-1` (boolean, required, default: `True`): Import all objects into one layer
- `output` (vectorDestination, required): Converted
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.e00

**Display Name:** v.in.e00

**Description:** Imports E00 file into a vector map

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): Name of input E00 file
- `type` (enum, optional, default: `[0]`): Input feature type
- `output` (vectorDestination, required): Name of output vector
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.geonames

**Display Name:** v.in.geonames

**Description:** Imports geonames.org country files into a GRASS vector points map.

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): Uncompressed geonames file from (with .txt extension)
- `output` (vectorDestination, required): Geonames
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.lidar

**Display Name:** v.in.lidar

**Description:** Converts LAS LiDAR point clouds to a GRASS vector map with libLAS.

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): LiDAR input files in LAS format (*.las or *.laz)
- `spatial` (extent, optional): Import subregion only
- `zrange` (range, optional): Filter range for z data
- `return_filter` (enum, optional): Only import points of selected return type
- `class_filter` (string, optional): Only import points of selected class(es) (comma separated integers)
- `skip` (number, optional): Do not import every n-th point
- `preserve` (number, optional): Import only every n-th point
- `offset` (number, optional): Skip first n points
- `limit` (number, optional): Import only n points
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `-c` (boolean, required, default: `False`): Do not automatically add unique ID as category to each point
- `-b` (boolean, required, default: `False`): Do not build topology
- `output` (vectorDestination, required): Lidar
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.lines

**Display Name:** v.in.lines

**Description:** Import ASCII x,y[,z] coordinates as a series of lines.

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): ASCII file to be imported
- `separator` (string, optional, default: `pipe`): Field separator
- `-z` (boolean, required, default: `False`): Create 3D vector map
- `output` (vectorDestination, required): Lines
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.mapgen

**Display Name:** v.in.mapgen

**Description:** Imports Mapgen or Matlab-ASCII vector maps into GRASS.

**Group:** Vector (v.*)

**Parameters:**

- `input` (file, required): Name of input file in Mapgen/Matlab format
- `-z` (boolean, required, default: `False`): Create 3D vector map
- `-f` (boolean, required, default: `False`): Input map is in Matlab format
- `output` (vectorDestination, required): Mapgen
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.in.wfs

**Display Name:** v.in.wfs

**Description:** Import GetFeature from WFS

**Group:** Vector (v.*)

**Parameters:**

- `url` (string, required, default: `http://`): GetFeature URL starting with 'http'
- `srs` (crs, optional): Alternate spatial reference system
- `name` (string, optional): Comma separated names of data layers to download
- `maximum_features` (number, optional): Maximum number of features to download
- `start_index` (number, optional): Skip earlier feature IDs and start downloading at this one
- `output` (vectorDestination, required): Converted
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.info

**Display Name:** v.info

**Description:** Outputs basic information about a user-specified vector map.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of input vector map
- `-c` (boolean, required, default: `False`): Print types/names of table columns for specified layer instead of info
- `-g` (boolean, required, default: `False`): Print map region only
- `-e` (boolean, required, default: `False`): Print extended metadata info in shell script style
- `-t` (boolean, required, default: `False`): Print topology information only
- `html` (fileDestination, required, default: `report.html`): Information report
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.kcv

**Display Name:** v.kcv

**Description:** Randomly partition points into test/train sets.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Input layer
- `npartitions` (number, required, default: `10.0`): Number of partitions
- `column` (string, optional, default: `part`): Name for new column to which partition number is written
- `output` (vectorDestination, required): Partition
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.kernel.rast

**Display Name:** v.kernel.rast

**Description:** v.kernel.rast - Generates a raster density map from vector points map.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map with training points
- `radius` (number, required, default: `10.0`): Kernel radius in map units
- `dsize` (number, optional, default: `0.0`): Discretization error in map units
- `segmax` (number, optional, default: `100.0`): Maximum length of segment on network
- `distmax` (number, optional, default: `100.0`): Maximum distance from point to network
- `multiplier` (number, optional, default: `1.0`): Multiply the density result by this number
- `node` (enum, required, default: `0`): Node method
- `kernel` (enum, optional, default: `5`): Kernel function
- `-o` (boolean, required, default: `False`): Try to calculate an optimal radius with given 'radius' taken as maximum (experimental)
- `output` (rasterDestination, required): Kernel
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.kernel.vector

**Display Name:** v.kernel.vector

**Description:** v.kernel.vector - Generates a vector density map from vector points on a vector network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map with training points
- `net` (source, required): Name of input network vector map
- `radius` (number, required, default: `10.0`): Kernel radius in map units
- `dsize` (number, optional, default: `0.0`): Discretization error in map units
- `segmax` (number, optional, default: `100.0`): Maximum length of segment on network
- `distmax` (number, optional, default: `100.0`): Maximum distance from point to network
- `multiplier` (number, optional, default: `1.0`): Multiply the density result by this number
- `node` (enum, required, default: `0`): Node method
- `kernel` (enum, optional, default: `5`): Kernel function
- `-o` (boolean, required, default: `False`): Try to calculate an optimal radius with given 'radius' taken as maximum (experimental)
- `-n` (boolean, required, default: `False`): Normalize values by sum of density multiplied by length of each segment.
- `-m` (boolean, required, default: `False`): Multiply the result by number of input points
- `output` (vectorDestination, required): Kernel
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.lidar.correction

**Display Name:** v.lidar.correction

**Description:** Correction of the v.lidar.growing output. It is the last of the three algorithms for LIDAR filtering.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer (v.lidar.growing output)
- `ew_step` (number, optional, default: `25.0`): Length of each spline step in the east-west direction
- `ns_step` (number, optional, default: `25.0`): Length of each spline step in the north-south direction
- `lambda_c` (number, optional, default: `1.0`): Regularization weight in reclassification evaluation
- `tch` (number, optional, default: `2.0`): High threshold for object to terrain reclassification
- `tcl` (number, optional, default: `1.0`): Low threshold for terrain to object reclassification
- `-e` (boolean, required, default: `False`): Estimate point density and distance
- `output` (vectorDestination, required): Classified
- `terrain` (vectorDestination, required): Only 'terrain' points
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.lidar.edgedetection

**Display Name:** v.lidar.edgedetection

**Description:** Detects the object's edges from a LIDAR data set.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `ew_step` (number, optional, default: `4.0`): Length of each spline step in the east-west direction
- `ns_step` (number, optional, default: `4.0`): Length of each spline step in the north-south direction
- `lambda_g` (number, optional, default: `0.01`): Regularization weight in gradient evaluation
- `tgh` (number, optional, default: `6.0`): High gradient threshold for edge classification
- `tgl` (number, optional, default: `3.0`): Low gradient threshold for edge classification
- `theta_g` (number, optional, default: `0.26`): Angle range for same direction detection
- `lambda_r` (number, optional, default: `2.0`): Regularization weight in residual evaluation
- `-e` (boolean, required, default: `False`): Estimate point density and distance
- `output` (vectorDestination, required): Edges
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.lidar.growing

**Display Name:** v.lidar.growing

**Description:** Building contour determination and Region Growing algorithm for determining the building inside

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector (v.lidar.edgedetection output)
- `first` (source, required): First pulse vector layer
- `tj` (number, optional, default: `0.2`): Threshold for cell object frequency in region growing
- `td` (number, optional, default: `0.6`): Threshold for double pulse in region growing
- `output` (vectorDestination, required): Buildings
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.mkgrid

**Display Name:** v.mkgrid

**Description:** Creates a GRASS vector layer of a user-defined grid.

**Group:** Vector (v.*)

**Parameters:**

- `grid` (string, required, default: `10,10`): Number of rows and columns in grid
- `position` (enum, optional, default: `0`): Where to place the grid
- `coordinates` (point, optional): Lower left easting and northing coordinates of map
- `box` (string, required, default: ``): Width and height of boxes in grid
- `angle` (number, optional, default: `0.0`): Angle of rotation (in degrees counter-clockwise)
- `breaks` (number, optional, default: `0.0`): Number of vertex points per grid cell
- `type` (enum, optional, default: `2`): Output feature type
- `-h` (boolean, required, default: `False`): Create hexagons (default: rectangles)
- `-a` (boolean, required, default: `False`): Allow asymmetric hexagons
- `map` (vectorDestination, required): Grid
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.neighbors

**Display Name:** v.neighbors

**Description:** Makes each cell value a function of attribute values and stores in an output raster map.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `method` (enum, required, default: `0`): Method for aggregate statistics (count if non given)
- `points_column` (field, optional): Column name of points map to use for statistics
- `size` (number, required, default: `0.1`): Neighborhood diameter in map units
- `output` (rasterDestination, required): Neighborhood
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.net

**Display Name:** v.net

**Description:** Performs network maintenance

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, optional): Input vector line layer (arcs)
- `points` (source, optional): Input vector point layer (nodes)
- `file` (file, optional): Name of input arcs file
- `operation` (enum, required, default: `0`): Operation to be performed
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_type` (enum, optional, default: `[0, 1]`): Arc type
- `-s` (boolean, required, default: `False`): Snap points to network
- `-c` (boolean, required, default: `False`): Assign unique categories to new points
- `output` (vectorDestination, required): Network
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.alloc

**Display Name:** v.net.alloc

**Description:** Allocates subnets for nearest centers

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `center_cats` (string, required, default: `1-100000`): Category values
- `arc_type` (enum, required, default: `[0, 1]`): Arc type
- `method` (enum, optional, default: `0`): Use costs from centers or costs to centers
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): Network Alloction
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.allpairs

**Display Name:** v.net.allpairs

**Description:** Computes the shortest path between all pairs of nodes in the network

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `cats` (string, optional, default: `1-10000`): Category values
- `where` (string, optional): WHERE condition of SQL statement without 'where' keyword'
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): Network_Allpairs
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.bridge

**Display Name:** v.net.bridge

**Description:** Computes bridges and articulation points in the network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (network)
- `points` (source, optional): Centers point layer (nodes)
- `method` (enum, required, default: `0`): Feature type
- `threshold` (number, optional, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (name)
- `arc_backward_column` (field, optional): Arc backward direction cost column (name)
- `node_column` (field, optional): Node cost column (number)
- `output` (vectorDestination, required): Bridge
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.centrality

**Display Name:** v.net.centrality

**Description:** Computes degree, centrality, betweenness, closeness and eigenvector centrality measures in the network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (network)
- `degree` (string, optional, default: `degree`): Name of output degree centrality column
- `closeness` (string, optional, default: `closeness`): Name of output closeness centrality column
- `betweenness` (string, optional, default: `betweenness`): Name of output betweenness centrality column
- `eigenvector` (string, optional, default: `eigenvector`): Name of output eigenvector centrality column
- `iterations` (number, optional, default: `1000.0`): Maximum number of iterations to compute eigenvector centrality
- `error` (number, optional, default: `0.1`): Cumulative error tolerance for eigenvector centrality
- `cats` (string, optional): Category values
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-a` (boolean, optional, default: `True`): Add points on nodes
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): Network Centrality
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.components

**Display Name:** v.net.components

**Description:** Computes strongly and weakly connected components in the network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (network)
- `points` (source, optional): Centers point layer (nodes)
- `threshold` (number, optional, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `method` (enum, required, default: `0`): Type of components
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-a` (boolean, optional, default: `True`): Add points on nodes
- `output` (vectorDestination, required): Network_Components_Line
- `output_point` (vectorDestination, required): Network_Components_Point
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.connectivity

**Display Name:** v.net.connectivity

**Description:** Computes vertex connectivity between two sets of nodes in the network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (network)
- `points` (source, required): Input vector point layer (first set of nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `set1_cats` (string, optional): Set1 Category values
- `set1_where` (string, optional): Set1 WHERE conditions of SQL statement without 'where' keyword
- `set2_cats` (string, optional): Set2 Category values
- `set2_where` (string, optional): Set2 WHERE conditions of SQL statement without 'where' keyword
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `output` (vectorDestination, required): Network_Connectivity
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.distance

**Display Name:** v.net.distance

**Description:** Computes shortest distance via the network between the given sets of features.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (network)
- `flayer` (source, required): Input vector from points layer (from)
- `tlayer` (source, required): Input vector to layer (to)
- `threshold` (number, required, default: `50.0`): Threshold for connecting nodes to the network (in map unit)
- `arc_type` (enum, optional, default: `[0, 1]`): Arc type
- `from_cats` (string, optional): From Category values
- `from_where` (string, optional): From WHERE conditions of SQL statement without 'where' keyword
- `to_type` (enum, optional, default: `[0]`): To feature type
- `to_cats` (string, optional): To Category values
- `to_where` (string, optional): To WHERE conditions of SQL statement without 'where' keyword
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `-l` (boolean, optional, default: `False`): Write each output path as one line, not as original input segments
- `output` (vectorDestination, required): Network_Distance
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.flow

**Display Name:** v.net.flow

**Description:** Computes the maximum flow between two sets of nodes in the network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (network)
- `points` (source, required): Input vector point layer (flow nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `source_cats` (string, optional): Source Category values
- `source_where` (string, optional): Source WHERE conditions of SQL statement without 'where' keyword
- `sink_cats` (string, optional): Sink Category values
- `sink_where` (string, optional): Sink WHERE conditions of SQL statement without 'where' keyword
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `output` (vectorDestination, required): Network_Flow
- `cut` (vectorDestination, required): Network_Cut
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.iso

**Display Name:** v.net.iso

**Description:** Splits network by cost isolines.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_type` (enum, required, default: `[0, 1]`): Arc type
- `center_cats` (string, required, default: `1-100000`): Category values
- `costs` (string, required, default: `1000,2000,3000`): Costs for isolines
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): Network_Iso
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.nreport

**Display Name:** v.net.nreport

**Description:** v.net.nreport - Reports nodes information of a network

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `output` (fileDestination, required): NReport
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.net.path

**Display Name:** v.net.path

**Description:** Finds shortest path on vector network

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `file` (file, required): Name of file containing start and end points
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_type` (enum, required, default: `[0, 1]`): Arc type
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `dmax` (number, optional, default: `1000.0`): Maximum distance to the network
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `-s` (boolean, optional, default: `False`): Write output as original input segments, not each path as one line
- `output` (vectorDestination, required): Network_Path
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.report

**Display Name:** v.net.report

**Description:** v.net.report - Reports lines information of a network

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `html` (fileDestination, required): Report
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.net.salesman

**Display Name:** v.net.salesman

**Description:** Creates a cycle connecting given nodes (Traveling salesman problem)

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_type` (enum, required, default: `[0, 1]`): Arc type
- `center_cats` (string, required, default: `1-100000`): Category values
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): Network_Salesman
- `sequence` (fileDestination, optional): Output file holding node sequence
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.spanningtree

**Display Name:** v.net.spanningtree

**Description:** Computes minimum spanning tree for the network.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, optional): Input point layer (nodes)
- `threshold` (number, optional, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): SpanningTree
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.steiner

**Display Name:** v.net.steiner

**Description:** Creates Steiner tree for the network and given terminals

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_type` (enum, optional, default: `[0, 1]`): Arc type
- `terminal_cats` (string, required, default: `1-100000`): Category values
- `acolumn` (field, optional): Arc forward/both direction(s) cost column (number)
- `npoints` (number, optional, default: `-1.0`): Number of Steiner points
- `-g` (boolean, optional, default: `False`): Use geodesic calculation for longitude-latitude locations
- `output` (vectorDestination, required): Network Steiner
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.timetable

**Display Name:** v.net.timetable

**Description:** Finds shortest path using timetables.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `points` (source, required): Centers point layer (nodes)
- `walk_layer` (source, optional): Layer number or name with walking connections
- `threshold` (number, required, default: `50.0`): Threshold for connecting centers to the network (in map unit)
- `arc_column` (field, optional): Arc forward/both direction(s) cost column (number)
- `arc_backward_column` (field, optional): Arc backward direction cost column (number)
- `node_column` (field, optional): Node cost column (number)
- `route_id` (field, optional): Name of column with route ids
- `stop_time` (field, optional): Name of column with stop timestamps
- `to_stop` (field, optional): Name of column with stop ids
- `walk_length` (field, optional): Name of column with walk lengths
- `output` (vectorDestination, required): Network Timetable
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.net.visibility

**Display Name:** v.net.visibility

**Description:** Performs visibility graph construction.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector line layer (arcs)
- `coordinates` (string, optional): Coordinates
- `visibility` (source, optional): Input vector line layer containing visible points
- `output` (vectorDestination, required): Network Visibility
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.normal

**Display Name:** v.normal

**Description:** Tests for normality for points.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): point vector defining sample points
- `tests` (string, required, default: `1-3`): Lists of tests (1-15): e.g. 1,3-8,13
- `column` (field, required): Attribute column
- `-r` (boolean, required, default: `True`): Use only points in current region
- `-l` (boolean, required, default: `False`): lognormal
- `html` (fileDestination, required, default: `report.html`): Normality
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.out.ascii

**Display Name:** v.out.ascii

**Description:** Exports a vector map to a GRASS ASCII vector representation.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `type` (enum, optional, default: `[0, 1, 2, 3, 4, 5, 6]`): Input feature type
- `columns` (field, optional): Name of attribute column(s) to be exported
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `format` (enum, required, default: `0`): Output format
- `separator` (enum, required, default: `0`): Field separator
- `precision` (number, optional, default: `8.0`): Number of significant digits (floating point only)
- `-o` (boolean, required, default: `False`): Create old (version 4) ASCII file
- `-c` (boolean, required, default: `False`): Include column names in output (points mode)
- `output` (fileDestination, required): Name for output ASCII file or ASCII vector name if '-o' is defined
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.out.dxf

**Display Name:** v.out.dxf

**Description:** Exports GRASS vector map layers to DXF file format.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `output` (fileDestination, required): DXF vector
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.out.postgis

**Display Name:** v.out.postgis

**Description:** Exports a vector map layer to PostGIS feature table.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `type` (enum, optional, default: `[7]`): Input feature type
- `output` (string, required, default: `PG:dbname=grass`): Name for output PostGIS datasource
- `output_layer` (string, optional): Name for output PostGIS layer
- `options` (string, optional): Creation options
- `-t` (boolean, required, default: `False`): Do not export attribute table
- `-l` (boolean, required, default: `False`): Export PostGIS topology instead of simple features
- `-2` (boolean, required, default: `False`): Force 2D output even if input is 3D
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.out.pov

**Display Name:** v.out.pov

**Description:** Converts to POV-Ray format, GRASS x,y,z -> POV-Ray x,z,y

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `type` (enum, optional, default: `[0, 1, 4, 5]`): Input feature type
- `size` (number, required, default: `10.0`): Radius of sphere for points and tube for lines
- `zmod` (string, optional): Modifier for z coordinates, this string is appended to each z coordinate
- `objmod` (string, optional): Object modifier (OBJECT_MODIFIER in POV-Ray documentation)
- `output` (fileDestination, required): POV vector
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.out.svg

**Display Name:** v.out.svg

**Description:** Exports a vector map to SVG file.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `type` (enum, required, default: `0`): Output type
- `precision` (number, optional, default: `6.0`): Coordinate precision
- `attribute` (field, optional): Attribute(s) to include in output SVG
- `output` (fileDestination, required): SVG File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.out.vtk

**Display Name:** v.out.vtk

**Description:** Converts a vector map to VTK ASCII output.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `type` (enum, optional, default: `[0, 1, 2, 3, 4, 5, 6]`): Input feature type
- `precision` (number, optional, default: `2.0`): Number of significant digits (floating point only)
- `zscale` (number, optional, default: `1.0`): Scale factor for elevation
- `-c` (boolean, required, default: `False`): Correct the coordinates to fit the VTK-OpenGL precision
- `-n` (boolean, required, default: `False`): Export numeric attribute table fields as VTK scalar variables
- `output` (fileDestination, required): VTK File
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.outlier

**Display Name:** v.outlier

**Description:** Removes outliers from vector point data.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `ew_step` (number, optional, default: `10.0`): Interpolation spline step value in east direction
- `ns_step` (number, optional, default: `10.0`): Interpolation spline step value in north direction
- `lambda` (number, optional, default: `0.1`): Tykhonov regularization weight
- `threshold` (number, optional, default: `50.0`): Threshold for the outliers
- `filter` (enum, optional, default: `0`): Filtering option
- `-e` (boolean, required, default: `False`): Estimate point density and distance
- `output` (vectorDestination, required): Layer without outliers
- `outlier` (vectorDestination, required): Outliers
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.overlay

**Display Name:** v.overlay

**Description:** Overlays two vector maps.

**Group:** Vector (v.*)

**Parameters:**

- `ainput` (source, required): Input layer (A)
- `atype` (enum, optional, default: `0`): Input layer (A) Type
- `binput` (source, required): Input layer (B)
- `btype` (enum, optional, default: `0`): Input layer (B) Type
- `operator` (enum, required, default: `0`): Operator to use
- `snap` (number, optional, default: `1e-08`): Snapping threshold for boundaries
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `output` (vectorDestination, required): Overlay
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.pack

**Display Name:** v.pack

**Description:** Exports a vector map as GRASS GIS specific archive file.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map to pack
- `-c` (boolean, required, default: `False`): Switch the compression off
- `output` (fileDestination, required, default: `output.pack`): Packed archive
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.parallel

**Display Name:** v.parallel

**Description:** Creates parallel line to input vector lines.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input lines
- `distance` (number, required, default: `1.0`): Offset along major axis in map units
- `minordistance` (number, optional): Offset along minor axis in map units
- `angle` (number, optional, default: `0.0`): Angle of major axis in degrees
- `side` (enum, required, default: `0`): Side
- `tolerance` (number, optional): Tolerance of arc polylines in map units
- `-r` (boolean, required, default: `False`): Make outside corners round
- `-b` (boolean, required, default: `False`): Create buffer-like parallel lines
- `output` (vectorDestination, required): Parallel lines
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.patch

**Display Name:** v.patch

**Description:** Create a new vector map layer by combining other vector map layers.

**Group:** Vector (v.*)

**Parameters:**

- `input` (multilayer, required): Input layers
- `-e` (boolean, required, default: `True`): Copy also attribute table
- `output` (vectorDestination, required): Combined
- `bbox` (vectorDestination, required): Bounding boxes
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.perturb

**Display Name:** v.perturb

**Description:** Random location perturbations of GRASS vector points

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Vector points to be spatially perturbed
- `distribution` (enum, optional, default: `0`): Distribution of perturbation
- `parameters` (string, optional): Parameter(s) of distribution (uniform: maximum; normal: mean and stddev)
- `minimum` (number, optional, default: `0.0`): Minimum deviation in map units
- `seed` (number, optional, default: `0.0`): Seed for random number generation
- `output` (vectorDestination, required): Perturbed
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.proj

**Display Name:** v.proj

**Description:** Re-projects a vector layer to another coordinate reference system

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector to reproject
- `crs` (crs, required): New coordinate reference system
- `smax` (number, optional, default: `10000.0`): Maximum segment length in meters in output vector map
- `-z` (boolean, optional, default: `False`): Assume z coordinate is ellipsoidal height and transform if possible
- `-w` (boolean, optional, default: `False`): Disable wrapping to -180,180 for latlon output
- `output` (vectorDestination, required): Output vector map
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.qcount

**Display Name:** v.qcount

**Description:** Indices for quadrat counts of vector point lists.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Vector points layer
- `nquadrats` (number, required, default: `4.0`): Number of quadrats
- `radius` (number, required, default: `10.0`): Quadrat radius
- `output` (vectorDestination, required): Quadrats
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.random

**Display Name:** v.random

**Description:** Randomly generate a 2D/3D vector points map.

**Group:** Vector (v.*)

**Parameters:**

- `npoints` (number, required, default: `100.0`): Number of points to be created
- `restrict` (source, optional): Restrict points to areas in input vector
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `zmin` (number, optional, default: `0.0`): Minimum z height for 3D output
- `zmax` (number, optional, default: `0.0`): Maximum z height for 3D output
- `seed` (number, optional): Seed for random number generation
- `column` (string, optional, default: `z`): Column for Z values
- `column_type` (enum, optional, default: `0`): Type of column for z values
- `-z` (boolean, optional, default: `False`): Create 3D output
- `-a` (boolean, optional, default: `False`): Generate n points for each individual area
- `output` (vectorDestination, required): Random
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.rast.stats

**Display Name:** v.rast.stats

**Description:** Calculates univariate statistics from a raster map based on vector polygons and uploads statistics to new attribute columns.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of vector polygon map
- `raster` (raster, required): Name of raster map to calculate statistics from
- `column_prefix` (string, required): Column prefix for new attribute columns
- `method` (enum, optional, default: `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]`): The methods to use
- `percentile` (number, optional, default: `90.0`): Percentile to calculate
- `output` (vectorDestination, required): Rast stats
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.reclass

**Display Name:** v.reclass

**Description:** Changes vector category values for an existing vector map according to results of SQL queries or a value in attribute table column.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input layer
- `type` (enum, optional, default: `[0, 1, 2, 3]`): Input feature type
- `column` (field, optional): The name of the column whose values are to be used as new categories
- `rules` (file, optional): Reclass rule file
- `output` (vectorDestination, required): Reclassified
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.rectify

**Display Name:** v.rectify

**Description:** Rectifies a vector by computing a coordinate transformation for each object in the vector based on the control points.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `inline_points` (string, optional): Inline control points
- `points` (file, optional): Name of input file with control points
- `order` (number, optional, default: `1.0`): Rectification polynomial order
- `separator` (string, optional, default: `pipe`): Field separator for RMS report
- `-3` (boolean, required, default: `False`): Perform 3D transformation
- `-o` (boolean, required, default: `False`): Perform orthogonal 3D transformation
- `-b` (boolean, required, default: `False`): Do not build topology
- `output` (vectorDestination, required): Rectified
- `rmsfile` (fileDestination, required): Root Mean Square errors file
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.report

**Display Name:** v.report

**Description:** Reports geometry statistics for vectors.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Input layer
- `option` (enum, required, default: `0`): Value to calculate
- `units` (enum, optional, default: `2`): units
- `sort` (enum, optional, default: `0`): Sort the result (ascending, descending)
- `html` (fileDestination, required, default: `report.html`): Report
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.sample

**Display Name:** v.sample

**Description:** Samples a raster layer at vector point locations.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Vector layer defining sample points
- `column` (field, required): Vector layer attribute column to use for comparison
- `raster` (raster, required): Raster map to be sampled
- `zscale` (number, optional, default: `1.0`): Sampled raster values will be multiplied by this factor
- `method` (enum, optional, default: `0`): Sampling interpolation method
- `output` (vectorDestination, optional): Sampled
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.segment

**Display Name:** v.segment

**Description:** Creates points/segments from input vector lines and positions.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input lines layer
- `rules` (file, required): File containing segment rules
- `output` (vectorDestination, required): Segments
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.select

**Display Name:** v.select

**Description:** Selects features from vector map (A) by features from other vector map (B).

**Group:** Vector (v.*)

**Parameters:**

- `ainput` (source, required): Input layer (A)
- `atype` (enum, optional, default: `[0, 1, 4]`): Input layer (A) Type
- `binput` (source, required): Input layer (B)
- `btype` (enum, optional, default: `[0, 1, 4]`): Input layer (B) Type
- `operator` (enum, required, default: `0`): Operator to use
- `relate` (string, optional): Intersection Matrix Pattern used for 'relate' operator
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `-c` (boolean, required, default: `False`): Do not skip features without category
- `-r` (boolean, required, default: `False`): Reverse selection
- `output` (vectorDestination, required): Selected
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.split

**Display Name:** v.split

**Description:** Split lines to shorter segments by length.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input lines layer
- `length` (number, optional): Maximum segment length
- `units` (enum, optional, default: `0`): Length units
- `vertices` (number, optional): Maximum number of vertices in segment
- `-n` (boolean, optional, default: `False`): Add new vertices, but do not split
- `-f` (boolean, optional, default: `False`): Force segments to be exactly of given length, except for last one
- `output` (vectorDestination, required): Split by length
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.surf.bspline

**Display Name:** v.surf.bspline

**Description:** Bicubic or bilinear spline interpolation with Tykhonov regularization.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input points layer
- `column` (field, optional): Attribute table column with values to interpolate
- `sparse_input` (source, optional): Sparse points layer
- `ew_step` (number, optional, default: `4.0`): Length of each spline step in the east-west direction
- `ns_step` (number, optional, default: `4.0`): Length of each spline step in the north-south direction
- `method` (enum, optional, default: `0`): Spline interpolation algorithm
- `lambda_i` (number, optional, default: `0.01`): Tykhonov regularization parameter (affects smoothing)
- `solver` (enum, optional, default: `0`): Type of solver which should solve the symmetric linear equation system
- `maxit` (number, optional, default: `10000.0`): Maximum number of iteration used to solve the linear equation system
- `error` (number, optional, default: `1e-06`): Error break criteria for iterative solver
- `memory` (number, optional, default: `300.0`): Maximum memory to be used (in MB)
- `output` (vectorDestination, optional): Output vector
- `raster_output` (rasterDestination, optional): Interpolated spline
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.surf.idw

**Display Name:** v.surf.idw

**Description:** Surface interpolation from vector point data by Inverse Distance Squared Weighting.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `npoints` (number, optional, default: `12.0`): Number of interpolation points
- `power` (number, optional, default: `2.0`): Power parameter; greater values assign greater influence to closer points
- `column` (field, required): Attribute table column with values to interpolate
- `-n` (boolean, required, default: `False`): Don't index points by raster cell
- `output` (rasterDestination, required): Interpolated IDW
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.surf.rst

**Display Name:** v.surf.rst

**Description:** Performs surface interpolation from vector points map by splines.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input points layer
- `zcolumn` (field, optional): Name of the attribute column with values to be used for approximation
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `mask` (raster, optional): Name of the raster map used as mask
- `tension` (number, optional, default: `40.0`): Tension parameter
- `smooth` (number, optional): Smoothing parameter
- `smooth_column` (field, optional): Name of the attribute column with smoothing parameters
- `segmax` (number, optional, default: `40.0`): Maximum number of points in a segment
- `npmin` (number, optional, default: `300.0`): Minimum number of points for approximation in a segment (>segmax)
- `dmin` (number, optional): Minimum distance between points (to remove almost identical points)
- `dmax` (number, optional): Maximum distance between points on isoline (to insert additional points)
- `zscale` (number, optional, default: `1.0`): Conversion factor for values used for approximation
- `theta` (number, optional): Anisotropy angle (in degrees counterclockwise from East)
- `scalex` (number, optional): Anisotropy scaling factor
- `-t` (boolean, required, default: `False`): Use scale dependent tension
- `-d` (boolean, required, default: `False`): Output partial derivatives instead of topographic parameters
- `elevation` (rasterDestination, optional): Interpolated RST
- `slope` (rasterDestination, optional): Slope
- `aspect` (rasterDestination, optional): Aspect
- `pcurvature` (rasterDestination, optional): Profile curvature
- `tcurvature` (rasterDestination, optional): Tangential curvature
- `mcurvature` (rasterDestination, optional): Mean curvature
- `deviations` (vectorDestination, optional): Deviations
- `treeseg` (vectorDestination, optional): Quadtree Segmentation
- `overwin` (vectorDestination, optional): Overlapping Windows
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.surf.rst.cvdev

**Display Name:** v.surf.rst.cvdev

**Description:** v.surf.rst.cvdev - Performs surface interpolation from vector points map by splines.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input points layer
- `zcolumn` (field, optional): Name of the attribute column with values to be used for approximation
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `mask` (raster, optional): Name of the raster map used as mask
- `tension` (number, optional, default: `40.0`): Tension parameter
- `smooth` (number, optional): Smoothing parameter
- `smooth_column` (field, optional): Name of the attribute column with smoothing parameters
- `segmax` (number, optional, default: `40.0`): Maximum number of points in a segment
- `npmin` (number, optional, default: `300.0`): Minimum number of points for approximation in a segment (>segmax)
- `dmin` (number, optional): Minimum distance between points (to remove almost identical points)
- `dmax` (number, optional): Maximum distance between points on isoline (to insert additional points)
- `zscale` (number, optional, default: `1.0`): Conversion factor for values used for approximation
- `theta` (number, optional): Anisotropy angle (in degrees counterclockwise from East)
- `scalex` (number, optional): Anisotropy scaling factor
- `-t` (boolean, required, default: `False`): Use scale dependent tension
- `-c` (boolean, required, default: `True`): Perform cross-validation procedure without raster approximation [leave this option as True]
- `cvdev` (vectorDestination, optional): Cross Validation Errors
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.to.3d

**Display Name:** v.to.3d

**Description:** Performs transformation of 2D vector features to 3D.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `type` (enum, optional, default: `[0, 1, 2, 3]`): Input feature type
- `height` (number, optional): Fixed height for 3D vector features
- `column` (field, optional): Name of attribute column used for height
- `-r` (boolean, required, default: `False`): Reverse transformation; 3D vector features to 2D
- `-t` (boolean, required, default: `False`): Do not copy attribute table
- `output` (vectorDestination, required): 3D
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.to.lines

**Display Name:** v.to.lines

**Description:** Converts vector polygons or points to lines.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of input vector map
- `method` (enum, optional, default: `0`): Method used for point interpolation
- `output` (vectorDestination, required): Lines
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.to.points

**Display Name:** v.to.points

**Description:** Create points along input lines

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input lines layer
- `type` (enum, optional, default: `[0, 1, 2, 3, 5]`): Input feature type
- `use` (enum, optional, default: `0`): Use line nodes or vertices only
- `dmax` (number, optional, default: `100.0`): Maximum distance between points in map units
- `-i` (boolean, required, default: `False`): Interpolate points between line vertices
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `output` (vectorDestination, required): Points along lines
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.to.rast

**Display Name:** v.to.rast

**Description:** Converts (rasterize) a vector layer into a raster layer.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `type` (enum, optional, default: `[0, 1, 3]`): Input feature type
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `use` (enum, required, default: `0`): Source of raster values
- `attribute_column` (field, optional): Name of column for 'attr' parameter (data type must be numeric)
- `rgb_column` (field, optional): Name of color definition column (with RRR:GGG:BBB entries)
- `label_column` (field, optional): Name of column used as raster category labels
- `value` (number, optional, default: `1.0`): Raster value (for use=val)
- `memory` (number, optional, default: `300.0`): Maximum memory to be used (in MB)
- `output` (rasterDestination, required): Rasterized
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_RASTER_FORMAT_OPT` (string, optional): Output Rasters format options (createopt)
- `GRASS_RASTER_FORMAT_META` (string, optional): Output Rasters format metadata options (metaopt)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.transform

**Display Name:** v.transform

**Description:** Performs an affine transformation on a vector layer.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input vector layer
- `xshift` (number, optional, default: `0.0`): X shift
- `yshift` (number, optional, default: `0.0`): Y shift
- `zshift` (number, optional, default: `0.0`): Z shift
- `xscale` (number, optional, default: `1.0`): X scale
- `yscale` (number, optional, default: `1.0`): Y scale
- `zscale` (number, optional, default: `1.0`): Z scale
- `zrotation` (number, optional, default: `0.0`): Rotation around z axis in degrees counterclockwise
- `columns` (string, optional): Name of attribute column(s) used as transformation parameters (Format: parameter:column, e.g. xshift:xs,yshift:ys,zrot:zr)
- `-t` (boolean, required, default: `False`): Shift all z values to bottom=0
- `-w` (boolean, required, default: `False`): Swap coordinates x, y and then apply other parameters
- `-x` (boolean, required, default: `False`): Swap coordinates x, z and then apply other parameters
- `-y` (boolean, required, default: `False`): Swap coordinates y, z and then apply other parameters
- `-a` (boolean, required, default: `False`): Swap coordinates after the other transformations
- `-b` (boolean, required, default: `False`): Do not build topology
- `output` (vectorDestination, required): Transformed
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.type

**Display Name:** v.type

**Description:** Change the type of geometry elements.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Name of existing vector map
- `from_type` (enum, required, default: `1`): Feature type to convert from
- `to_type` (enum, required, default: `2`): Feature type to convert to
- `output` (vectorDestination, required): Typed
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.univar

**Display Name:** v.univar

**Description:** Calculates univariate statistics for attribute. Variance and standard deviation is calculated only for points if specified.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of input vector map
- `type` (enum, optional, default: `[0, 1, 4]`): Input feature type
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `column` (field, required): Column name
- `percentile` (number, optional, default: `90.0`): Percentile to calculate
- `-g` (boolean, required, default: `True`): Print the stats in shell script style
- `-e` (boolean, required, default: `False`): Calculate extended statistics
- `-w` (boolean, required, default: `False`): Weigh by line length or area size
- `-d` (boolean, required, default: `False`): Calculate geometric distances instead of attribute statistics
- `html` (fileDestination, required, default: `report.html`): Statistics
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area

---

### grass:v.vect.stats

**Display Name:** v.vect.stats

**Description:** Count points in areas and calculate statistics.

**Group:** Vector (v.*)

**Parameters:**

- `points` (source, required): Name of existing vector map with points
- `areas` (source, required): Name of existing vector map with areas
- `type` (enum, required, default: `[0]`): Input feature type
- `method` (enum, required, default: `0`): Method for aggregate statistics
- `points_column` (field, required): Column name of points map to use for statistics
- `count_column` (string, required): Column name to upload points count (integer, created if doesn't exists)
- `stats_column` (string, required): Column name to upload statistics (double, created if doesn't exists)
- `output` (vectorDestination, required): Updated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.voronoi

**Display Name:** v.voronoi

**Description:** v.voronoi - Creates a Voronoi diagram from an input vector layer containing points.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input points layer
- `-l` (boolean, required, default: `False`): Output tessellation as a graph (lines), not areas
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `output` (vectorDestination, required): Voronoi
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.voronoi.skeleton

**Display Name:** v.voronoi.skeleton

**Description:** v.voronoi.skeleton - Creates a Voronoi diagram for polygons or compute the center line/skeleton of polygons.

**Group:** Vector (v.*)

**Parameters:**

- `input` (source, required): Input polygons layer
- `smoothness` (number, optional, default: `0.25`): Factor for output smoothness
- `thin` (number, optional, default: `-1.0`): Maximum dangle length of skeletons (-1 will extract the center line)
- `-a` (boolean, required, default: `False`): Create Voronoi diagram for input areas
- `-s` (boolean, required, default: `True`): Extract skeletons for input areas
- `-l` (boolean, required, default: `False`): Output tessellation as a graph (lines), not areas
- `-t` (boolean, required, default: `False`): Do not create attribute table
- `output` (vectorDestination, required): Voronoi
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.what.rast

**Display Name:** v.what.rast

**Description:** Uploads raster values at positions of vector centroids to the table.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of vector points map for which to edit attributes
- `raster` (raster, required): Raster map to be sampled
- `type` (enum, required, default: `0`): Input feature type
- `column` (field, required): Name of attribute column to be updated with the query result
- `where` (string, optional): WHERE conditions of SQL statement without 'where' keyword
- `-i` (boolean, optional, default: `False`): Interpolate values from the nearest four cells
- `output` (vectorDestination, required): Sampled
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_REGION_CELLSIZE_PARAMETER` (number, required, default: `0.0`): GRASS GIS region cellsize (leave 0 for default)
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

### grass:v.what.vect

**Display Name:** v.what.vect

**Description:** Uploads vector values at positions of vector points to the table.

**Group:** Vector (v.*)

**Parameters:**

- `map` (source, required): Name of vector points map for which to edit attributes
- `column` (field, required): Column to be updated with the query result
- `query_map` (source, required): Vector map to be queried
- `query_column` (field, required): Column to be queried
- `dmax` (number, optional, default: `0.0`): Maximum query distance in map units
- `output` (vectorDestination, required): Updated
- `GRASS_REGION_PARAMETER` (extent, optional): GRASS GIS region extent
- `GRASS_SNAP_TOLERANCE_PARAMETER` (number, required, default: `-1.0`): v.in.ogr snap tolerance (-1 = no snap)
- `GRASS_MIN_AREA_PARAMETER` (number, required, default: `0.0001`): v.in.ogr min area
- `GRASS_OUTPUT_TYPE_PARAMETER` (enum, required, default: `0`): v.out.ogr output type
- `GRASS_VECTOR_DSCO` (string, optional): v.out.ogr output data source options (dsco)
- `GRASS_VECTOR_LCO` (string, optional): v.out.ogr output layer options (lco)
- `GRASS_VECTOR_EXPORT_NOCAT` (boolean, required, default: `False`): Also export features without category (not labeled). Otherwise only features with category are exported

---

## QGIS (native c++)

Provider ID: `native`
Total algorithms: 271

### native:addautoincrementalfield

**Display Name:** Add autoincremental field

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD_NAME` (string, required, default: `AUTO`): Field name
- `START` (number, optional, default: `0`): Start values at
- `MODULUS` (number, optional, default: `0`): Modulus value
- `GROUP_FIELDS` (field, optional): Group values by
- `SORT_EXPRESSION` (expression, optional): Sort expression
- `SORT_ASCENDING` (boolean, required, default: `True`): Sort ascending
- `SORT_NULLS_FIRST` (boolean, required, default: `False`): Sort nulls first
- `OUTPUT` (sink, required): Incremented

---

### native:addfieldtoattributestable

**Display Name:** Add field to attributes table

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD_NAME` (string, required): Field name
- `FIELD_TYPE` (enum, required, default: `0`): Field type
- `FIELD_LENGTH` (number, required, default: `10`): Field length
- `FIELD_PRECISION` (number, required, default: `0`): Field precision
- `FIELD_ALIAS` (string, optional): Field alias
- `FIELD_COMMENT` (string, optional): Field comment
- `OUTPUT` (sink, required): Added

---

### native:adduniquevalueindexfield

**Display Name:** Add unique value index field

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Class field
- `FIELD_NAME` (string, required, default: `NUM_FIELD`): Output field name
- `OUTPUT` (sink, optional): Layer with index field
- `SUMMARY_OUTPUT` (sink, optional): Class summary

---

### native:addxyfields

**Display Name:** Add X/Y fields to layer

**Description:** Adds X and Y (or latitude/longitude) fields to a point layer.

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `CRS` (crs, required, default: `EPSG:4326`): Coordinate system
- `PREFIX` (string, optional): Field prefix
- `OUTPUT` (sink, required): Added fields

---

### native:affinetransform

**Display Name:** Affine transform

**Description:** Applies an affine transformation to geometries.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DELTA_X` (distance, required, default: `0.0`): Translation (x-axis)
- `DELTA_Y` (distance, required, default: `0.0`): Translation (y-axis)
- `DELTA_Z` (number, required, default: `0.0`): Translation (z-axis)
- `DELTA_M` (number, required, default: `0.0`): Translation (m values)
- `SCALE_X` (number, required, default: `1.0`): Scale factor (x-axis)
- `SCALE_Y` (number, required, default: `1.0`): Scale factor (y-axis)
- `SCALE_Z` (number, required, default: `1.0`): Scale factor (z-axis)
- `SCALE_M` (number, required, default: `1.0`): Scale factor (m values)
- `ROTATION_Z` (number, required, default: `0.0`): Rotation around z-axis (degrees counter-clockwise)
- `OUTPUT` (sink, required): Transformed

---

### native:aggregate

**Display Name:** Aggregate

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `GROUP_BY` (expression, required, default: `NULL`): Group by expression (NULL to group all features)
- `AGGREGATES` (aggregates, required): Aggregates
- `OUTPUT` (sink, required): Aggregated

---

### native:alignrasters

**Display Name:** Align rasters

**Group:** Raster tools

**Parameters:**

- `LAYERS` (alignrasterlayers, required): Input layers
- `REFERENCE_LAYER` (raster, required): Reference layer
- `CRS` (crs, optional): Override reference CRS
- `CELL_SIZE_X` (number, optional): Override reference cell size X
- `CELL_SIZE_Y` (number, optional): Override reference cell size Y
- `GRID_OFFSET_X` (number, optional): Override reference grid offset X
- `GRID_OFFSET_Y` (number, optional): Override reference grid offset Y
- `EXTENT` (extent, optional): Clip to extent

---

### native:alignsingleraster

**Display Name:** Align raster

**Group:** Raster tools

**Parameters:**

- `INPUT` (raster, required): Input layer
- `RESAMPLING_METHOD` (enum, required, default: `0`): Resampling method
- `RESCALE` (boolean, required, default: `False`): Rescale values according to the cell size
- `REFERENCE_LAYER` (raster, required): Reference layer
- `CRS` (crs, optional): Override reference CRS
- `CELL_SIZE_X` (number, optional): Override reference cell size X
- `CELL_SIZE_Y` (number, optional): Override reference cell size Y
- `GRID_OFFSET_X` (number, optional): Override reference grid offset X
- `GRID_OFFSET_Y` (number, optional): Override reference grid offset Y
- `EXTENT` (extent, optional): Clip to extent
- `OUTPUT` (rasterDestination, required): Aligned raster

---

### native:angletonearest

**Display Name:** Align points to features

**Description:** Rotates point features to align them to nearby features.

**Group:** Cartography

**Parameters:**

- `INPUT` (source, required): Input layer
- `REFERENCE_LAYER` (source, required): Reference layer
- `MAX_DISTANCE` (distance, optional): Maximum distance to consider
- `FIELD_NAME` (string, required, default: `rotation`): Angle field name
- `APPLY_SYMBOLOGY` (boolean, required, default: `True`): Automatically apply symbology
- `OUTPUT` (sink, required): Aligned layer

---

### native:antimeridiansplit

**Display Name:** Geodesic line split at antimeridian

**Description:** Splits lines into multiple geodesic segments when the line crosses the antimeridian (±180 degrees longitude).

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Split

---

### native:arrayoffsetlines

**Display Name:** Array of offset (parallel) lines

**Description:** Creates multiple offset copies of lines from a layer.

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `COUNT` (number, required, default: `10`): Number of features to create
- `OFFSET` (distance, required, default: `1.0`): Offset step distance
- `SEGMENTS` (number, required, default: `8`): Segments
- `JOIN_STYLE` (enum, required, default: `0`): Join style
- `MITER_LIMIT` (number, required, default: `2`): Miter limit
- `OUTPUT` (sink, required): Offset lines

---

### native:arraytranslatedfeatures

**Display Name:** Array of translated features

**Description:** Creates multiple translated copies of features in a layer.

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `COUNT` (number, required, default: `10`): Number of features to create
- `DELTA_X` (distance, required, default: `0.0`): Step distance (x-axis)
- `DELTA_Y` (distance, required, default: `0.0`): Step distance (y-axis)
- `DELTA_Z` (number, required, default: `0.0`): Step distance (z-axis)
- `DELTA_M` (number, required, default: `0.0`): Step distance (m values)
- `OUTPUT` (sink, required): Translated

---

### native:aspect

**Display Name:** Aspect

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT` (raster, required): Elevation layer
- `Z_FACTOR` (number, required, default: `1`): Z factor
- `OUTPUT` (rasterDestination, required): Aspect

---

### native:assignprojection

**Display Name:** Assign projection

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `CRS` (crs, required, default: `EPSG:4326`): Assigned CRS
- `OUTPUT` (sink, required): Assigned CRS

---

### native:atlaslayouttoimage

**Display Name:** Export atlas layout as image

**Description:** Exports an atlas layout as a set of images.

**Group:** Cartography

**Parameters:**

- `LAYOUT` (layout, required): Atlas layout
- `COVERAGE_LAYER` (vector, optional): Coverage layer
- `FILTER_EXPRESSION` (expression, optional, default: `NULL`): Filter expression
- `SORTBY_EXPRESSION` (expression, optional, default: `NULL`): Sort expression
- `SORTBY_REVERSE` (boolean, optional, default: `False`): Reverse sort order (used when a sort expression is provided)
- `FILENAME_EXPRESSION` (expression, required, default: `'output_'||@atlas_featurenumber`): Output filename expression
- `FOLDER` (file, required): Output folder
- `LAYERS` (multilayer, optional): Map layers to assign to unlocked map item(s)
- `EXTENSION` (enum, required, default: `11`): Image format
- `DPI` (number, optional): DPI (leave blank for default layout DPI)
- `GEOREFERENCE` (boolean, required, default: `True`): Generate world file
- `INCLUDE_METADATA` (boolean, required, default: `True`): Export RDF metadata (title, author, etc.)
- `ANTIALIAS` (boolean, required, default: `True`): Enable antialiasing

---

### native:atlaslayouttomultiplepdf

**Display Name:** Export atlas layout as PDF (multiple files)

**Description:** Exports an atlas layout to multiple PDF files.

**Group:** Cartography

**Parameters:**

- `LAYOUT` (layout, required): Atlas layout
- `COVERAGE_LAYER` (vector, optional): Coverage layer
- `FILTER_EXPRESSION` (expression, optional, default: `NULL`): Filter expression
- `SORTBY_EXPRESSION` (expression, optional, default: `NULL`): Sort expression
- `SORTBY_REVERSE` (boolean, optional, default: `False`): Reverse sort order (used when a sort expression is provided)
- `LAYERS` (multilayer, optional): Map layers to assign to unlocked map item(s)
- `DPI` (number, optional): DPI (leave blank for default layout DPI)
- `FORCE_VECTOR` (boolean, required, default: `False`): Always export as vectors
- `FORCE_RASTER` (boolean, required, default: `False`): Always export as raster
- `GEOREFERENCE` (boolean, required, default: `True`): Append georeference information
- `INCLUDE_METADATA` (boolean, required, default: `True`): Export RDF metadata (title, author, etc.)
- `DISABLE_TILED` (boolean, required, default: `False`): Disable tiled raster layer exports
- `SIMPLIFY` (boolean, required, default: `True`): Simplify geometries to reduce output file size
- `TEXT_FORMAT` (enum, required, default: `0`): Text export
- `IMAGE_COMPRESSION` (enum, required, default: `0`): Image compression
- `OUTPUT_FILENAME` (expression, optional, default: `NULL`): Output filename
- `OUTPUT_FOLDER` (file, required): Output folder

---

### native:atlaslayouttopdf

**Display Name:** Export atlas layout as PDF (single file)

**Description:** Exports an atlas layout as a single PDF file.

**Group:** Cartography

**Parameters:**

- `LAYOUT` (layout, required): Atlas layout
- `COVERAGE_LAYER` (vector, optional): Coverage layer
- `FILTER_EXPRESSION` (expression, optional, default: `NULL`): Filter expression
- `SORTBY_EXPRESSION` (expression, optional, default: `NULL`): Sort expression
- `SORTBY_REVERSE` (boolean, optional, default: `False`): Reverse sort order (used when a sort expression is provided)
- `LAYERS` (multilayer, optional): Map layers to assign to unlocked map item(s)
- `DPI` (number, optional): DPI (leave blank for default layout DPI)
- `FORCE_VECTOR` (boolean, required, default: `False`): Always export as vectors
- `FORCE_RASTER` (boolean, required, default: `False`): Always export as raster
- `GEOREFERENCE` (boolean, required, default: `True`): Append georeference information
- `INCLUDE_METADATA` (boolean, required, default: `True`): Export RDF metadata (title, author, etc.)
- `DISABLE_TILED` (boolean, required, default: `False`): Disable tiled raster layer exports
- `SIMPLIFY` (boolean, required, default: `True`): Simplify geometries to reduce output file size
- `TEXT_FORMAT` (enum, required, default: `0`): Text export
- `IMAGE_COMPRESSION` (enum, required, default: `0`): Image compression
- `OUTPUT` (fileDestination, required): PDF file

---

### native:b3dmtogltf

**Display Name:** Convert B3DM to GLTF

**Group:** 3D Tiles

**Parameters:**

- `INPUT` (file, required): Input B3DM
- `OUTPUT` (fileDestination, required): Output file

---

### native:basicstatisticsforfields

**Display Name:** Basic statistics for fields

**Group:** Vector analysis

**Parameters:**

- `INPUT_LAYER` (source, required): Input layer
- `FIELD_NAME` (field, required): Field to calculate statistics on
- `OUTPUT` (sink, optional): Statistics
- `OUTPUT_HTML_FILE` (fileDestination, optional): Statistics report

---

### native:batchnominatimgeocoder

**Display Name:** Batch Nominatim geocoder

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Address field
- `OUTPUT` (sink, required): Geocoded

---

### native:bookmarkstolayer

**Display Name:** Convert spatial bookmarks to layer

**Description:** Converts stored spatial bookmarks to a polygon layer.

**Group:** Vector general

**Parameters:**

- `SOURCE` (enum, required, default: `[0, 1]`): Bookmark source
- `CRS` (crs, required, default: `<QgsCoordinateReferenceSystem: EPSG:4326>`): Output CRS
- `OUTPUT` (sink, required): Output

---

### native:boundary

**Display Name:** Boundary

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Boundary

---

### native:boundingboxes

**Display Name:** Bounding boxes

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Bounds

---

### native:buffer

**Display Name:** Buffer

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (distance, required, default: `10`): Distance
- `SEGMENTS` (number, required, default: `5`): Segments
- `END_CAP_STYLE` (enum, required, default: `0`): End cap style
- `JOIN_STYLE` (enum, required, default: `0`): Join style
- `MITER_LIMIT` (number, required, default: `2`): Miter limit
- `DISSOLVE` (boolean, required, default: `False`): Dissolve result
- `SEPARATE_DISJOINT` (boolean, required, default: `False`): Keep disjoint results separate
- `OUTPUT` (sink, required): Buffered

---

### native:bufferbym

**Display Name:** Variable width buffer (by M value)

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `SEGMENTS` (number, required, default: `16`): Segments
- `OUTPUT` (sink, required): Buffered

---

### native:calculateexpression

**Display Name:** Calculate expression

**Group:** Modeler tools

**Parameters:**

- `INPUT` (string, required): Input

---

### native:calculatevectoroverlaps

**Display Name:** Overlap analysis

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `LAYERS` (multilayer, required): Overlay layers
- `OUTPUT` (sink, required): Overlap
- `GRID_SIZE` (number, optional): Grid size

---

### native:categorizeusingstyle

**Display Name:** Create categorized renderer from styles

**Description:** Sets a vector layer's renderer to a categorized renderer using symbols from a style database.

**Group:** Cartography

**Parameters:**

- `INPUT` (vector, required): Input layer
- `FIELD` (expression, required): Categorize using expression
- `STYLE` (file, optional): Style database (leave blank to use saved symbols)
- `CASE_SENSITIVE` (boolean, required, default: `False`): Use case-sensitive match to symbol names
- `TOLERANT` (boolean, required, default: `False`): Ignore non-alphanumeric characters while matching
- `NON_MATCHING_CATEGORIES` (sink, optional): Non-matching categories
- `NON_MATCHING_SYMBOLS` (sink, optional): Non-matching symbol names

---

### native:cellstackpercentile

**Display Name:** Cell stack percentile

**Group:** Raster analysis

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `METHOD` (enum, required, default: `0`): Method
- `PERCENTILE` (number, required, default: `0.25`): Percentile
- `IGNORE_NODATA` (boolean, required, default: `True`): Ignore NoData values
- `REFERENCE_LAYER` (raster, required): Reference layer
- `OUTPUT_NODATA_VALUE` (number, required, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:cellstackpercentrankfromrasterlayer

**Display Name:** Cell stack percentrank from raster layer

**Group:** Raster analysis

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `INPUT_VALUE_RASTER` (raster, required): Value raster layer
- `VALUE_RASTER_BAND` (band, required, default: `1`): Value raster band
- `METHOD` (enum, required, default: `0`): Method
- `IGNORE_NODATA` (boolean, required, default: `True`): Ignore NoData values
- `REFERENCE_LAYER` (raster, required): Reference layer
- `OUTPUT_NODATA_VALUE` (number, required, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:cellstackpercentrankfromvalue

**Display Name:** Cell stack percent rank from value

**Group:** Raster analysis

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `METHOD` (enum, required, default: `0`): Method
- `VALUE` (number, required, default: `10`): Value
- `IGNORE_NODATA` (boolean, required, default: `True`): Ignore NoData values
- `REFERENCE_LAYER` (raster, required): Reference layer
- `OUTPUT_NODATA_VALUE` (number, required, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:cellstatistics

**Display Name:** Cell statistics

**Group:** Raster analysis

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `STATISTIC` (enum, required, default: `0`): Statistic
- `IGNORE_NODATA` (boolean, required, default: `True`): Ignore NoData values
- `REFERENCE_LAYER` (raster, required): Reference layer
- `OUTPUT_NODATA_VALUE` (number, required, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:centroids

**Display Name:** Centroids

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ALL_PARTS` (boolean, required, default: `False`): Create centroid for each part
- `OUTPUT` (sink, required): Centroids

---

### native:clip

**Display Name:** Clip

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAY` (source, required): Overlay layer
- `OUTPUT` (sink, required): Clipped

---

### native:collect

**Display Name:** Collect geometries

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, optional): Unique ID fields
- `OUTPUT` (sink, required): Collected

---

### native:combinestyles

**Display Name:** Combine style databases

**Description:** Combines multiple style databases into a single database.

**Group:** Cartography

**Parameters:**

- `INPUT` (multilayer, required): Input databases
- `OUTPUT` (fileDestination, required): Output style database
- `OBJECTS` (enum, required, default: `[0, 1, 2, 3]`): Objects to combine

---

### native:concavehull

**Display Name:** Concave hull

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ALPHA` (number, required, default: `0.3`): Threshold (0-1, where 1 is equivalent with Convex Hull)
- `HOLES` (boolean, required, default: `True`): Allow holes
- `NO_MULTIGEOMETRY` (boolean, required, default: `False`): Split multipart geometry into singleparts
- `OUTPUT` (sink, required): Concave hull

---

### native:condition

**Display Name:** Conditional branch

**Description:** Adds a conditional branch into a model, allowing parts of the model to be selectively executed.

**Group:** Modeler tools

---

### native:convertgpsdata

**Display Name:** Convert GPS data

**Group:** GPS

**Parameters:**

- `INPUT` (file, required): Input file
- `FORMAT` (string, required): Format
- `FEATURE_TYPE` (enum, required, default: `0`): Feature type
- `OUTPUT` (fileDestination, required): Output

---

### native:convertgpxfeaturetype

**Display Name:** Convert GPX feature type

**Group:** GPS

**Parameters:**

- `INPUT` (file, required): Input file
- `CONVERSION` (enum, required, default: `0`): Conversion
- `OUTPUT` (fileDestination, required): Output

---

### native:converttocurves

**Display Name:** Convert to curved geometries

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (number, required, default: `1e-06`): Maximum distance tolerance
- `ANGLE` (number, required, default: `1e-06`): Maximum angle tolerance
- `OUTPUT` (sink, required): Curves

---

### native:convexhull

**Display Name:** Convex hull

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Convex hulls

---

### native:countpointsinpolygon

**Display Name:** Count points in polygon

**Description:** Counts point features located within polygon features.

**Group:** Vector analysis

**Parameters:**

- `POLYGONS` (source, required): Polygons
- `POINTS` (source, required): Points
- `WEIGHT` (field, optional): Weight field
- `CLASSFIELD` (field, optional): Class field
- `FIELD` (string, required, default: `NUMPOINTS`): Count field name
- `OUTPUT` (sink, required): Count

---

### native:coveragesimplify

**Display Name:** Simplify coverage

**Description:** Simplifies a coverage of polygon features while retaining valid coverage

**Group:** Vector coverage

**Parameters:**

- `INPUT` (source, required): Input layer
- `TOLERANCE` (distance, required, default: `1.0`): Tolerance
- `PRESERVE_BOUNDARY` (boolean, required, default: `False`): Preserve boundary
- `OUTPUT` (sink, required): Simplified

---

### native:coverageunion

**Display Name:** Dissolve coverage

**Description:** Dissolves a coverage of polygon features

**Group:** Vector coverage

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Dissolved

---

### native:coveragevalidate

**Display Name:** Validate coverage

**Description:** Analyzes a coverage of polygon features to find places where the assumption of exactly matching edges is not met

**Group:** Vector coverage

**Parameters:**

- `INPUT` (source, required): Input layer
- `GAP_WIDTH` (distance, required, default: `0.0`): Gap width
- `INVALID_EDGES` (sink, optional): Invalid edges

---

### native:createattributeindex

**Display Name:** Create attribute index

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input layer
- `FIELD` (field, required): Attribute to index

---

### native:createconstantrasterlayer

**Display Name:** Create constant raster layer

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `NUMBER` (number, required, default: `1`): Constant value
- `OUTPUT_TYPE` (enum, required, default: `5`): Output raster data type
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Constant

---

### native:createdirectory

**Display Name:** Create directory

**Description:** Creates a new directory on a file system.

**Group:** Modeler tools

**Parameters:**

- `PATH` (layer, required): Directory path

---

### native:creategrid

**Display Name:** Create grid

**Group:** Vector creation

**Parameters:**

- `TYPE` (enum, required, default: `0`): Grid type
- `EXTENT` (extent, required): Grid extent
- `HSPACING` (distance, required, default: `1`): Horizontal spacing
- `VSPACING` (distance, required, default: `1`): Vertical spacing
- `HOVERLAY` (distance, required, default: `0`): Horizontal overlay
- `VOVERLAY` (distance, required, default: `0`): Vertical overlay
- `CRS` (crs, required, default: `ProjectCrs`): Grid CRS
- `OUTPUT` (sink, required): Grid

---

### native:createpointslayerfromtable

**Display Name:** Create points layer from table

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `XFIELD` (field, required): X field
- `YFIELD` (field, required): Y field
- `ZFIELD` (field, optional): Z field
- `MFIELD` (field, optional): M field
- `TARGET_CRS` (crs, required, default: `EPSG:4326`): Target CRS
- `OUTPUT` (sink, required): Points from table

---

### native:createrandombinomialrasterlayer

**Display Name:** Create random raster layer (binomial distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `N` (number, required, default: `10`): N
- `PROBABILITY` (number, required, default: `0.5`): Probability
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandomexponentialrasterlayer

**Display Name:** Create random raster layer (exponential distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `LAMBDA` (number, required, default: `1.0`): Lambda
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandomgammarasterlayer

**Display Name:** Create random raster layer (gamma distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `ALPHA` (number, required, default: `1.0`): Alpha
- `BETA` (number, required, default: `1.0`): Beta
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandomgeometricrasterlayer

**Display Name:** Create random raster layer (geometric distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `PROBABILITY` (number, required, default: `0.5`): Probability
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandomnegativebinomialrasterlayer

**Display Name:** Create random raster layer (negative binomial distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `K_PARAMETER` (number, required, default: `10`): Distribution parameter k
- `PROBABILITY` (number, required, default: `0.5`): Probability
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandomnormalrasterlayer

**Display Name:** Create random raster layer (normal distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `MEAN` (number, required, default: `0`): Mean of normal distribution
- `STDDEV` (number, required, default: `1`): Standard deviation of normal distribution
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandompoissonrasterlayer

**Display Name:** Create random raster layer (poisson distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `0`): Output raster data type
- `MEAN` (number, required, default: `1.0`): Mean
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createrandomuniformrasterlayer

**Display Name:** Create random raster layer (uniform distribution)

**Group:** Raster creation

**Parameters:**

- `EXTENT` (extent, required): Desired extent
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `PIXEL_SIZE` (number, required, default: `1`): Pixel size
- `OUTPUT_TYPE` (enum, required, default: `5`): Output raster data type
- `LOWER_BOUND` (number, required): Lower bound for random number range
- `UPPER_BOUND` (number, required): Upper bound for random number range
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:createspatialindex

**Display Name:** Create spatial index

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input layer

---

### native:dbscanclustering

**Display Name:** DBSCAN clustering

**Description:** Clusters point features using a density based scan algorithm.

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `MIN_SIZE` (number, required, default: `5`): Minimum cluster size
- `EPS` (distance, required, default: `1`): Maximum distance between clustered points
- `DBSCAN*` (boolean, optional, default: `False`): Treat border points as noise (DBSCAN*)
- `FIELD_NAME` (string, required, default: `CLUSTER_ID`): Cluster field name
- `SIZE_FIELD_NAME` (string, required, default: `CLUSTER_SIZE`): Cluster size field name
- `OUTPUT` (sink, required): Clusters

---

### native:delaunaytriangulation

**Display Name:** Delaunay triangulation

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `TOLERANCE` (number, optional, default: `0`): Tolerance
- `ADD_ATTRIBUTES` (boolean, required, default: `True`): Add point IDs to output
- `OUTPUT` (sink, required): Delaunay triangulation

---

### native:deletecolumn

**Display Name:** Drop field(s)

**Description:** Deletes fields from a vector layer.

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `COLUMN` (field, required): Fields to drop
- `OUTPUT` (sink, required): Remaining fields

---

### native:deleteduplicategeometries

**Display Name:** Delete duplicate geometries

**Description:** Finds duplicated geometries in a layer and removes them.

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Cleaned

---

### native:deleteholes

**Display Name:** Delete holes

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `MIN_AREA` (area, required, default: `0.0`): Remove holes with area less than
- `OUTPUT` (sink, required): Cleaned

---

### native:densifygeometries

**Display Name:** Densify by count

**Description:** Creates a densified version of geometries.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `VERTICES` (number, required, default: `1`): Number of vertices to add
- `OUTPUT` (sink, required): Densified

---

### native:densifygeometriesgivenaninterval

**Display Name:** Densify by interval

**Description:** Creates a densified version of geometries.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `INTERVAL` (distance, required, default: `1`): Interval between vertices to add
- `OUTPUT` (sink, required): Densified

---

### native:detectvectorchanges

**Display Name:** Detect dataset changes

**Description:** Calculates features which are unchanged, added or deleted between two dataset versions.

**Group:** Vector general

**Parameters:**

- `ORIGINAL` (source, required): Original layer
- `REVISED` (source, required): Revised layer
- `COMPARE_ATTRIBUTES` (field, optional): Attributes to consider for match (or none to compare geometry only)
- `MATCH_TYPE` (enum, required, default: `1`): Geometry comparison behavior
- `UNCHANGED` (sink, optional): Unchanged features
- `ADDED` (sink, optional): Added features
- `DELETED` (sink, optional): Deleted features

---

### native:difference

**Display Name:** Difference

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAY` (source, required): Overlay layer
- `OUTPUT` (sink, required): Difference
- `GRID_SIZE` (number, optional): Grid size

---

### native:dissolve

**Display Name:** Dissolve

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, optional): Dissolve field(s)
- `SEPARATE_DISJOINT` (boolean, required, default: `False`): Keep disjoint features separate
- `OUTPUT` (sink, required): Dissolved

---

### native:downloadgpsdata

**Display Name:** Download GPS data from device

**Group:** GPS

**Parameters:**

- `DEVICE` (string, required): Device
- `PORT` (string, required): Port
- `FEATURE_TYPE` (enum, required, default: `0`): Feature type
- `OUTPUT` (fileDestination, required): Output

---

### native:downloadvectortiles

**Display Name:** Download vector tiles

**Group:** Vector tiles

**Parameters:**

- `INPUT` (layer, required): Input layer
- `EXTENT` (extent, required): Extent
- `MAX_ZOOM` (number, required, default: `10`): Maximum zoom level to download
- `TILE_LIMIT` (number, required, default: `100`): Tile limit
- `OUTPUT` (vectorTileDestination, required): Output

---

### native:dropgeometries

**Display Name:** Drop geometries

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Dropped geometries

---

### native:dropmzvalues

**Display Name:** Drop M/Z values

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DROP_M_VALUES` (boolean, required, default: `False`): Drop M Values
- `DROP_Z_VALUES` (boolean, required, default: `False`): Drop Z Values
- `OUTPUT` (sink, required): Z/M Dropped

---

### native:dtmslopebasedfilter

**Display Name:** DTM filter (slope-based)

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `RADIUS` (number, required, default: `5`): Kernel radius (pixels)
- `TERRAIN_SLOPE` (number, required, default: `30`): Terrain slope (%, pixel size/vertical units)
- `FILTER_MODIFICATION` (enum, required, default: `0`): Filter modification
- `STANDARD_DEVIATION` (number, required, default: `0.1`): Standard deviation
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT_GROUND` (rasterDestination, optional): Output layer (ground)
- `OUTPUT_NONGROUND` (rasterDestination, optional): Output layer (non-ground objects)

---

### native:dxfexport

**Display Name:** Export layers to DXF

**Group:** Vector general

**Parameters:**

- `LAYERS` (dxflayers, required): Input layers
- `SYMBOLOGY_MODE` (enum, required, default: `0`): Symbology mode
- `SYMBOLOGY_SCALE` (scale, required, default: `1000000`): Symbology scale
- `MAP_THEME` (maptheme, optional): Map theme
- `ENCODING` (enum, required, default: `ISO-8859-1`): Encoding
- `CRS` (crs, required, default: `EPSG:4326`): CRS
- `EXTENT` (extent, optional): Extent
- `SELECTED_FEATURES_ONLY` (boolean, required, default: `False`): Use only selected features
- `USE_LAYER_TITLE` (boolean, required, default: `False`): Use layer title as name
- `FORCE_2D` (boolean, required, default: `False`): Force 2D output
- `MTEXT` (boolean, required, default: `True`): Export labels as MTEXT elements
- `EXPORT_LINES_WITH_ZERO_WIDTH` (boolean, required): Export lines with zero width
- `OUTPUT` (fileDestination, required): DXF

---

### native:equaltofrequency

**Display Name:** Equal to frequency

**Group:** Raster analysis

**Parameters:**

- `INPUT_VALUE_RASTER` (raster, required): Input value raster
- `INPUT_VALUE_RASTER_BAND` (band, required, default: `1`): Value raster band
- `INPUT_RASTERS` (multilayer, required): Input raster layers
- `IGNORE_NODATA` (boolean, required, default: `False`): Ignore NoData values
- `OUTPUT_NODATA_VALUE` (number, optional, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:explodehstorefield

**Display Name:** Explode HStore Field

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): HStore field
- `EXPECTED_FIELDS` (string, optional): Expected list of fields separated by a comma
- `OUTPUT` (sink, required): Exploded

---

### native:explodelines

**Display Name:** Explode lines

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Exploded

---

### native:exportlayersinformation

**Display Name:** Export layer(s) information

**Group:** Layer tools

**Parameters:**

- `LAYERS` (multilayer, required): Input layer(s)
- `OUTPUT` (sink, required): Output

---

### native:exportmeshedges

**Display Name:** Export mesh edges

**Description:** Exports mesh edges to a line vector layer

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, optional, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `VECTOR_OPTION` (enum, required, default: `0`): Export vector option
- `OUTPUT` (sink, required): Output vector layer

---

### native:exportmeshfaces

**Display Name:** Export mesh faces

**Description:** Exports mesh faces to a polygon vector layer

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, optional, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `VECTOR_OPTION` (enum, required, default: `0`): Export vector option
- `OUTPUT` (sink, required): Output vector layer

---

### native:exportmeshongrid

**Display Name:** Export mesh on grid

**Description:** Exports mesh dataset values to a gridded point vector layer

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, required, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `EXTENT` (extent, optional): Extent
- `GRID_SPACING` (distance, required, default: `10`): Grid spacing
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `VECTOR_OPTION` (enum, required, default: `0`): Export vector option
- `OUTPUT` (sink, required): Output vector layer

---

### native:exportmeshvertices

**Display Name:** Export mesh vertices

**Description:** Exports mesh vertices to a point vector layer

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, optional, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `VECTOR_OPTION` (enum, required, default: `0`): Export vector option
- `OUTPUT` (sink, required): Output vector layer

---

### native:exporttospreadsheet

**Display Name:** Export to spreadsheet

**Group:** Layer tools

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `USE_ALIAS` (boolean, required, default: `False`): Use field aliases as column headings
- `FORMATTED_VALUES` (boolean, required, default: `False`): Export formatted values instead of raw values
- `OUTPUT` (fileDestination, required): Destination spreadsheet
- `OVERWRITE` (boolean, required, default: `True`): Overwrite existing spreadsheet

---

### native:extendlines

**Display Name:** Extend lines

**Description:** Extends LineString geometries by extrapolating the start and end segments.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `START_DISTANCE` (distance, required, default: `0.0`): Start distance
- `END_DISTANCE` (distance, required, default: `0.0`): End distance
- `OUTPUT` (sink, required): Extended

---

### native:extenttolayer

**Display Name:** Create layer from extent

**Group:** Vector geometry

**Parameters:**

- `INPUT` (extent, required): Extent
- `OUTPUT` (sink, required): Extent

---

### native:extractbinary

**Display Name:** Extract binary field

**Description:** This algorithm extracts contents from a binary field, saving them to individual files.

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Binary field
- `FILENAME` (expression, required): File name
- `FOLDER` (folderDestination, required): Destination folder

---

### native:extractbyattribute

**Display Name:** Extract by attribute

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Selection attribute
- `OPERATOR` (enum, required, default: `0`): Operator
- `VALUE` (string, optional): Value
- `OUTPUT` (sink, required): Extracted (attribute)
- `FAIL_OUTPUT` (sink, optional): Extracted (non-matching)

---

### native:extractbyexpression

**Display Name:** Extract by expression

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Input layer
- `EXPRESSION` (expression, required): Expression
- `OUTPUT` (sink, required): Matching features
- `FAIL_OUTPUT` (sink, optional): Non-matching

---

### native:extractbyextent

**Display Name:** Extract/clip by extent

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `EXTENT` (extent, required): Extent
- `CLIP` (boolean, required, default: `False`): Clip features to extent
- `OUTPUT` (sink, required): Extracted

---

### native:extractbylocation

**Display Name:** Extract by location

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Extract features from
- `PREDICATE` (enum, required, default: `[0]`): Where the features (geometric predicate)
- `INTERSECT` (source, required): By comparing to the features from
- `OUTPUT` (sink, required): Extracted (location)

---

### native:extractlabels

**Display Name:** Extract labels

**Description:** Converts map labels to a point layer with relevant details saved as attributes.

**Group:** Cartography

**Parameters:**

- `EXTENT` (extent, required): Map extent
- `SCALE` (scale, required): Map scale
- `MAP_THEME` (maptheme, optional): Map theme
- `INCLUDE_UNPLACED` (boolean, optional, default: `True`): Include unplaced labels
- `DPI` (number, optional, default: `96.0`): Map resolution (in DPI)
- `OUTPUT` (sink, required): Extracted labels

---

### native:extractmvalues

**Display Name:** Extract M values

**Description:** Extracts m values (or m value statistics) from geometries into feature attributes.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `SUMMARIES` (enum, required, default: `[0]`): Summaries to calculate
- `COLUMN_PREFIX` (string, optional, default: `m_`): Output column prefix
- `OUTPUT` (sink, required): Extracted

---

### native:extractspecificvertices

**Display Name:** Extract specific vertices

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `VERTICES` (string, required, default: `0`): Vertex indices
- `OUTPUT` (sink, required): Vertices

---

### native:extractvertices

**Display Name:** Extract vertices

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Vertices

---

### native:extractwithindistance

**Display Name:** Extract within distance

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Extract features from
- `REFERENCE` (source, required): By comparing to the features from
- `DISTANCE` (distance, required, default: `100`): Where the features are within
- `OUTPUT` (sink, required): Extracted (location)

---

### native:extractzvalues

**Display Name:** Extract Z values

**Description:** Extracts z values (or z value statistics) from geometries into feature attributes.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `SUMMARIES` (enum, required, default: `[0]`): Summaries to calculate
- `COLUMN_PREFIX` (string, optional, default: `z_`): Output column prefix
- `OUTPUT` (sink, required): Extracted

---

### native:fieldcalculator

**Display Name:** Field calculator

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD_NAME` (string, required): Field name
- `FIELD_TYPE` (enum, required, default: `0`): Result field type
- `FIELD_LENGTH` (number, required, default: `0`): Result field length
- `FIELD_PRECISION` (number, required, default: `0`): Result field precision
- `FORMULA` (expression, required): Formula
- `OUTPUT` (sink, required): Calculated

---

### native:filedownloader

**Display Name:** Download file via HTTP(S)

**Description:** Downloads a URL to the file system with an HTTP(S) GET or POST request

**Group:** File tools

**Parameters:**

- `URL` (string, required): URL
- `METHOD` (enum, required, default: `0`): Method
- `DATA` (string, optional): Data
- `OUTPUT` (fileDestination, required): File destination

---

### native:fillnodata

**Display Name:** Fill NoData cells

**Group:** Raster tools

**Parameters:**

- `INPUT` (raster, required): Raster input
- `BAND` (band, required, default: `1`): Band Number
- `FILL_VALUE` (number, required, default: `1`): Fill value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:filter

**Display Name:** Feature filter

**Group:** Modeler tools

**Parameters:**

- `INPUT` (source, required): Input layer

---

### native:filterbygeometry

**Display Name:** Filter by geometry type

**Description:** Filters features by geometry type

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Input layer
- `POINTS` (sink, optional): Point features
- `LINES` (sink, optional): Line features
- `POLYGONS` (sink, optional): Polygon features
- `NO_GEOMETRY` (sink, optional): Features with no geometry

---

### native:filterlayersbytype

**Display Name:** Filter layers by type

**Description:** Filters layers by type

**Group:** Modeler tools

**Parameters:**

- `INPUT` (layer, required): Input layer
- `VECTOR` (vectorDestination, optional): Vector features
- `RASTER` (rasterDestination, optional): Raster layer

---

### native:filterverticesbym

**Display Name:** Filter vertices by M value

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `MIN` (number, optional): Minimum
- `MAX` (number, optional): Maximum
- `OUTPUT` (sink, required): Filtered

---

### native:filterverticesbyz

**Display Name:** Filter vertices by Z value

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `MIN` (number, optional): Minimum
- `MAX` (number, optional): Maximum
- `OUTPUT` (sink, required): Filtered

---

### native:fixgeometries

**Display Name:** Fix geometries

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `METHOD` (enum, required, default: `0`): Repair method
- `OUTPUT` (sink, required): Fixed geometries

---

### native:flattenrelationships

**Display Name:** Flatten relationship

**Description:** Flatten a relationship for a vector layer.

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input layer
- `OUTPUT` (sink, required): Flattened layer

---

### native:forcerhr

**Display Name:** Force right-hand-rule

**Description:** Forces polygon geometries to respect the Right-Hand-Rule.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Reoriented

---

### native:fuzzifyrastergaussianmembership

**Display Name:** Fuzzify raster (gaussian membership)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input Raster
- `BAND` (band, required, default: `1`): Band Number
- `FUZZYMIDPOINT` (number, required, default: `10`): Function midpoint
- `FUZZYSPREAD` (number, required, default: `0.01`): Function spread
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Fuzzified raster

---

### native:fuzzifyrasterlargemembership

**Display Name:** Fuzzify raster (large membership)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input Raster
- `BAND` (band, required, default: `1`): Band Number
- `FUZZYMIDPOINT` (number, required, default: `50`): Function midpoint
- `FUZZYSPREAD` (number, required, default: `5`): Function spread
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Fuzzified raster

---

### native:fuzzifyrasterlinearmembership

**Display Name:** Fuzzify raster (linear membership)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input Raster
- `BAND` (band, required, default: `1`): Band Number
- `FUZZYLOWBOUND` (number, required, default: `0`): Low fuzzy membership bound
- `FUZZYHIGHBOUND` (number, required, default: `1`): High fuzzy membership bound
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Fuzzified raster

---

### native:fuzzifyrasternearmembership

**Display Name:** Fuzzify raster (near membership)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input Raster
- `BAND` (band, required, default: `1`): Band Number
- `FUZZYMIDPOINT` (number, required, default: `50`): Function midpoint
- `FUZZYSPREAD` (number, required, default: `0.01`): Function spread
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Fuzzified raster

---

### native:fuzzifyrasterpowermembership

**Display Name:** Fuzzify raster (power membership)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input Raster
- `BAND` (band, required, default: `1`): Band Number
- `FUZZYLOWBOUND` (number, required, default: `0`): Low fuzzy membership bound
- `FUZZYHIGHBOUND` (number, required, default: `1`): High fuzzy membership bound
- `FUZZYEXPONENT` (number, required, default: `2`): Membership function exponent
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Fuzzified raster

---

### native:fuzzifyrastersmallmembership

**Display Name:** Fuzzify raster (small membership)

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input Raster
- `BAND` (band, required, default: `1`): Band Number
- `FUZZYMIDPOINT` (number, required, default: `50`): Function midpoint
- `FUZZYSPREAD` (number, required, default: `5`): Function spread
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Fuzzified raster

---

### native:generatepointspixelcentroidsinsidepolygons

**Display Name:** Generate points (pixel centroids) inside polygons

**Group:** Vector creation

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `INPUT_VECTOR` (source, required): Vector layer
- `OUTPUT` (sink, required): Pixel centroids

---

### native:geometrybyexpression

**Display Name:** Geometry by expression

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT_GEOMETRY` (enum, required, default: `0`): Output geometry type
- `WITH_Z` (boolean, required, default: `False`): Output geometry has z dimension
- `WITH_M` (boolean, required, default: `False`): Output geometry has m values
- `EXPRESSION` (expression, required, default: `@geometry`): Geometry expression
- `OUTPUT` (sink, required): Modified geometry

---

### native:gltftovector

**Display Name:** Convert GLTF to vector features

**Group:** 3D Tiles

**Parameters:**

- `INPUT` (file, required): Input GLTF
- `OUTPUT_POLYGONS` (sink, optional): Output polygons
- `OUTPUT_LINES` (sink, optional): Output lines

---

### native:greaterthanfrequency

**Display Name:** Greater than frequency

**Group:** Raster analysis

**Parameters:**

- `INPUT_VALUE_RASTER` (raster, required): Input value raster
- `INPUT_VALUE_RASTER_BAND` (band, required, default: `1`): Value raster band
- `INPUT_RASTERS` (multilayer, required): Input raster layers
- `IGNORE_NODATA` (boolean, required, default: `False`): Ignore NoData values
- `OUTPUT_NODATA_VALUE` (number, optional, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:highestpositioninrasterstack

**Display Name:** Highest position in raster stack

**Group:** Raster analysis

**Parameters:**

- `INPUT_RASTERS` (multilayer, required): Input raster layers
- `REFERENCE_LAYER` (raster, required): Reference layer
- `IGNORE_NODATA` (boolean, required, default: `False`): Ignore NoData values
- `OUTPUT_NODATA_VALUE` (number, optional, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:hillshade

**Display Name:** Hillshade

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT` (raster, required): Elevation layer
- `Z_FACTOR` (number, required, default: `1`): Z factor
- `AZIMUTH` (number, required, default: `300`): Azimuth (horizontal angle)
- `V_ANGLE` (number, required, default: `40`): Vertical angle
- `OUTPUT` (rasterDestination, required): Hillshade

---

### native:httprequest

**Display Name:** HTTP(S) POST/GET request

**Description:** Performs a HTTP(S) POST/GET request and returns the result code, error message and the data

**Group:** File tools

**Parameters:**

- `URL` (string, required): URL
- `METHOD` (enum, required, default: `0`): Method
- `DATA` (string, optional): POST data
- `OUTPUT` (fileDestination, optional): File destination
- `AUTH_CONFIG` (authcfg, optional): Authentication
- `FAIL_ON_ERROR` (boolean, required, default: `False`): Consider HTTP errors as failures

---

### native:hublines

**Display Name:** Join by lines (hub lines)

**Description:** Creates lines joining two point layers, based on a common attribute value.

**Group:** Vector analysis

**Parameters:**

- `HUBS` (source, required): Hub layer
- `HUB_FIELD` (field, required): Hub ID field
- `HUB_FIELDS` (field, optional): Hub layer fields to copy (leave empty to copy all fields)
- `SPOKES` (source, required): Spoke layer
- `SPOKE_FIELD` (field, required): Spoke ID field
- `SPOKE_FIELDS` (field, optional): Spoke layer fields to copy (leave empty to copy all fields)
- `GEODESIC` (boolean, required, default: `False`): Create geodesic lines
- `GEODESIC_DISTANCE` (distance, required, default: `1000`): Distance between vertices (geodesic lines only)
- `ANTIMERIDIAN_SPLIT` (boolean, required, default: `False`): Split lines at antimeridian (±180 degrees longitude)
- `OUTPUT` (sink, required): Hub lines

---

### native:importintopostgis

**Display Name:** Export to PostgreSQL

**Description:** Exports a vector layer to a PostgreSQL database

**Group:** Database

**Parameters:**

- `INPUT` (source, required): Layer to export
- `DATABASE` (providerconnection, required): Database (connection name)
- `SCHEMA` (databaseschema, optional, default: `public`): Schema (schema name)
- `TABLENAME` (databasetable, optional): Table to export to (leave blank to use layer name)
- `PRIMARY_KEY` (field, optional): Primary key field
- `GEOMETRY_COLUMN` (string, required, default: `geom`): Geometry column
- `ENCODING` (string, optional, default: `UTF-8`): Encoding
- `OVERWRITE` (boolean, required, default: `True`): Overwrite
- `CREATEINDEX` (boolean, required, default: `True`): Create spatial index
- `LOWERCASE_NAMES` (boolean, required, default: `True`): Convert field names to lowercase
- `DROP_STRING_LENGTH` (boolean, required, default: `False`): Drop length constraints on character fields
- `FORCE_SINGLEPART` (boolean, required, default: `False`): Create single-part geometries instead of multipart

---

### native:importphotos

**Display Name:** Import geotagged photos

**Group:** Vector creation

**Parameters:**

- `FOLDER` (file, required): Input folder
- `RECURSIVE` (boolean, required, default: `False`): Scan recursively
- `OUTPUT` (sink, optional): Photos
- `INVALID` (sink, optional): Invalid photos table

---

### native:interpolatepoint

**Display Name:** Interpolate point on line

**Description:** Interpolates a point along lines at a set distance.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (distance, required, default: `0.0`): Distance
- `OUTPUT` (sink, required): Interpolated points

---

### native:intersection

**Display Name:** Intersection

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAY` (source, required): Overlay layer
- `INPUT_FIELDS` (field, optional): Input fields to keep (leave empty to keep all fields)
- `OVERLAY_FIELDS` (field, optional): Overlay fields to keep (leave empty to keep all fields)
- `OVERLAY_FIELDS_PREFIX` (string, optional, default: `NULL`): Overlay fields prefix
- `OUTPUT` (sink, required): Intersection
- `GRID_SIZE` (number, optional): Grid size

---

### native:joinattributesbylocation

**Display Name:** Join attributes by location

**Description:** Join attributes from one vector layer to another by location.

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Join to features in
- `PREDICATE` (enum, required, default: `0`): Features they (geometric predicate)
- `JOIN` (source, required): By comparing to
- `JOIN_FIELDS` (field, optional): Fields to add (leave empty to use all fields)
- `METHOD` (enum, required, default: `0`): Join type
- `DISCARD_NONMATCHING` (boolean, required, default: `False`): Discard records which could not be joined
- `PREFIX` (string, optional): Joined field prefix
- `OUTPUT` (sink, optional): Joined layer
- `NON_MATCHING` (sink, optional): Unjoinable features from first layer

---

### native:joinattributestable

**Display Name:** Join attributes by field value

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Table field
- `INPUT_2` (source, required): Input layer 2
- `FIELD_2` (field, required): Table field 2
- `FIELDS_TO_COPY` (field, optional): Layer 2 fields to copy (leave empty to copy all fields)
- `METHOD` (enum, required, default: `1`): Join type
- `DISCARD_NONMATCHING` (boolean, required, default: `False`): Discard records which could not be joined
- `PREFIX` (string, optional): Joined field prefix
- `OUTPUT` (sink, optional): Joined layer
- `NON_MATCHING` (sink, optional): Unjoinable features from first layer

---

### native:joinbylocationsummary

**Display Name:** Join attributes by location (summary)

**Description:** Calculate summaries of attributes from one vector layer to another by location.

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Join to features in
- `PREDICATE` (enum, required, default: `0`): Where the features
- `JOIN` (source, required): By comparing to
- `JOIN_FIELDS` (field, optional): Fields to summarise (leave empty to use all fields)
- `SUMMARIES` (enum, optional): Summaries to calculate (leave empty to use all available)
- `DISCARD_NONMATCHING` (boolean, required, default: `False`): Discard records which could not be joined
- `OUTPUT` (sink, required): Joined layer

---

### native:joinbynearest

**Display Name:** Join attributes by nearest

**Description:** Joins a layer to another layer, using the closest features (nearest neighbors).

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `INPUT_2` (source, required): Input layer 2
- `FIELDS_TO_COPY` (field, optional): Layer 2 fields to copy (leave empty to copy all fields)
- `DISCARD_NONMATCHING` (boolean, required, default: `False`): Discard records which could not be joined
- `PREFIX` (string, optional): Joined field prefix
- `NEIGHBORS` (number, required, default: `1`): Maximum nearest neighbors
- `MAX_DISTANCE` (distance, optional): Maximum distance
- `OUTPUT` (sink, optional): Joined layer
- `NON_MATCHING` (sink, optional): Unjoinable features from first layer

---

### native:keepnbiggestparts

**Display Name:** Keep N biggest parts

**Group:** Vector geometry

**Parameters:**

- `POLYGONS` (source, required): Input layer
- `PARTS` (number, required, default: `1.0`): Parts to keep
- `OUTPUT` (sink, required): Parts

---

### native:kmeansclustering

**Display Name:** K-means clustering

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `CLUSTERS` (number, required, default: `5`): Number of clusters
- `FIELD_NAME` (string, required, default: `CLUSTER_ID`): Cluster field name
- `SIZE_FIELD_NAME` (string, required, default: `CLUSTER_SIZE`): Cluster size field name
- `OUTPUT` (sink, required): Clusters

---

### native:layertobookmarks

**Display Name:** Convert layer to spatial bookmarks

**Description:** Converts feature extents to stored spatial bookmarks.

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `DESTINATION` (enum, required, default: `0`): Bookmark destination
- `NAME_EXPRESSION` (expression, required): Name field
- `GROUP_EXPRESSION` (expression, optional): Group field

---

### native:lessthanfrequency

**Display Name:** Less than frequency

**Group:** Raster analysis

**Parameters:**

- `INPUT_VALUE_RASTER` (raster, required): Input value raster
- `INPUT_VALUE_RASTER_BAND` (band, required, default: `1`): Value raster band
- `INPUT_RASTERS` (multilayer, required): Input raster layers
- `IGNORE_NODATA` (boolean, required, default: `False`): Ignore NoData values
- `OUTPUT_NODATA_VALUE` (number, optional, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:linedensity

**Display Name:** Line density

**Group:** Interpolation

**Parameters:**

- `INPUT` (source, required): Input line layer
- `WEIGHT` (field, optional): Weight field 
- `RADIUS` (distance, required, default: `10`): Search radius
- `PIXEL_SIZE` (distance, required, default: `10`): Pixel size
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Line density raster

---

### native:lineintersections

**Display Name:** Line intersections

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `INTERSECT` (source, required): Intersect layer
- `INPUT_FIELDS` (field, optional): Input fields to keep (leave empty to keep all fields)
- `INTERSECT_FIELDS` (field, optional): Intersect fields to keep (leave empty to keep all fields)
- `INTERSECT_FIELDS_PREFIX` (string, optional, default: `NULL`): Intersect fields prefix
- `OUTPUT` (sink, required): Intersections

---

### native:linesubstring

**Display Name:** Line substring

**Description:** Returns the substring of lines which fall between start and end distances.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `START_DISTANCE` (distance, required, default: `0.0`): Start distance
- `END_DISTANCE` (distance, required, default: `1.0`): End distance
- `OUTPUT` (sink, required): Substring

---

### native:loadlayer

**Display Name:** Load layer into project

**Group:** Modeler tools

**Parameters:**

- `INPUT` (layer, required): Layer
- `NAME` (string, required): Loaded layer name

---

### native:lowestpositioninrasterstack

**Display Name:** Lowest position in raster stack

**Group:** Raster analysis

**Parameters:**

- `INPUT_RASTERS` (multilayer, required): Input raster layers
- `REFERENCE_LAYER` (raster, required): Reference layer
- `IGNORE_NODATA` (boolean, required, default: `False`): Ignore NoData values
- `OUTPUT_NODATA_VALUE` (number, optional, default: `-9999`): Output NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:meancoordinates

**Display Name:** Mean coordinate(s)

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `WEIGHT` (field, optional): Weight field
- `UID` (field, optional): Unique ID field
- `OUTPUT` (sink, required): Mean coordinates

---

### native:mergelines

**Display Name:** Merge lines

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Merged

---

### native:mergevectorlayers

**Display Name:** Merge vector layers

**Description:** Combines multiple vector layers of the same geometry type into a single one.

**Group:** Vector general

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `CRS` (crs, optional): Destination CRS
- `OUTPUT` (sink, required): Merged

---

### native:meshcontours

**Display Name:** Export contours

**Description:** Creates contours as vector layer from mesh scalar dataset

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, required, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `INCREMENT` (number, optional): Increment between contour levels
- `MINIMUM` (number, optional): Minimum contour level
- `MAXIMUM` (number, optional): Maximum contour level
- `CONTOUR_LEVEL_LIST` (string, optional): List of contours level
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `OUTPUT_LINES` (sink, required): Exported contour lines
- `OUTPUT_POLYGONS` (sink, required): Exported contour polygons

---

### native:meshexportcrosssection

**Display Name:** Export cross section dataset values on lines from mesh

**Description:** Extracts a mesh dataset's values from lines contained in a vector layer

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, required, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `INPUT_LINES` (source, required): Lines for data export
- `RESOLUTION` (distance, required, default: `10.0`): Line segmentation resolution
- `COORDINATES_DIGITS` (number, required, default: `2`): Digits count for coordinates
- `DATASET_DIGITS` (number, required, default: `2`): Digits count for dataset value
- `OUTPUT` (fileDestination, required): Exported data CSV file

---

### native:meshexporttimeseries

**Display Name:** Export time series values from points of a mesh dataset

**Description:** Extracts a mesh dataset's time series values from points contained in a vector layer

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, required, default: `[]`): Dataset groups
- `STARTING_TIME` (meshdatasettime, required): Starting time
- `FINISHING_TIME` (meshdatasettime, required): Finishing time
- `TIME_STEP` (number, optional, default: `0`): Time step (hours)
- `INPUT_POINTS` (source, required): Points for data export
- `COORDINATES_DIGITS` (number, required, default: `2`): Digits count for coordinates
- `DATASET_DIGITS` (number, required, default: `2`): Digits count for dataset value
- `OUTPUT` (fileDestination, required): Exported data CSV file

---

### native:meshrasterize

**Display Name:** Rasterize mesh dataset

**Description:** Creates a raster layer from a mesh dataset

**Group:** Mesh

**Parameters:**

- `INPUT` (mesh, required): Input mesh layer
- `DATASET_GROUPS` (meshdatasetgroups, optional, default: `[]`): Dataset groups
- `DATASET_TIME` (meshdatasettime, required): Dataset time
- `EXTENT` (extent, optional): Extent
- `PIXEL_SIZE` (distance, required, default: `1`): Pixel size
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster layer

---

### native:minimumenclosingcircle

**Display Name:** Minimum enclosing circles

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `SEGMENTS` (number, required, default: `72`): Number of segments in circles
- `OUTPUT` (sink, required): Minimum enclosing circles

---

### native:modelerrastercalc

**Display Name:** Raster calculator

**Group:** Raster analysis

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `EXPRESSION` (expression, required): Expression
- `EXTENT` (extent, optional): Output extent
- `CELL_SIZE` (number, optional): Output cell size (leave empty to set automatically)
- `CRS` (crs, optional): Output CRS
- `OUTPUT` (rasterDestination, required): Calculated

---

### native:modelervirtualrastercalc

**Display Name:** Raster calculator (virtual)

**Group:** Raster analysis

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `EXPRESSION` (expression, required): Expression
- `EXTENT` (extent, optional): Output extent
- `CELL_SIZE` (number, optional): Output cell size (leave empty to set automatically)
- `CRS` (crs, optional): Output CRS
- `LAYER_NAME` (string, optional): Output layer name

---

### native:multidifference

**Display Name:** Difference (multiple)

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAYS` (multilayer, required): Overlay layers
- `OUTPUT` (sink, required): Difference

---

### native:multiintersection

**Display Name:** Intersection (multiple)

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAYS` (multilayer, required): Overlay layers
- `OVERLAY_FIELDS_PREFIX` (string, optional, default: `NULL`): Overlay fields prefix
- `OUTPUT` (sink, required): Intersection

---

### native:multiparttosingleparts

**Display Name:** Multipart to singleparts

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Single parts

---

### native:multiringconstantbuffer

**Display Name:** Multi-ring buffer (constant distance)

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `RINGS` (number, required, default: `1`): Number of rings
- `DISTANCE` (distance, required, default: `1`): Distance between rings
- `OUTPUT` (sink, required): Multi-ring buffer (constant distance)

---

### native:multiunion

**Display Name:** Union (multiple)

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAYS` (multilayer, optional): Overlay layers
- `OVERLAY_FIELDS_PREFIX` (string, optional, default: `NULL`): Overlay fields prefix
- `OUTPUT` (sink, required): Union

---

### native:nearestneighbouranalysis

**Display Name:** Nearest neighbour analysis

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT_HTML_FILE` (fileDestination, optional): Nearest neighbour

---

### native:offsetline

**Display Name:** Offset lines

**Description:** Offsets lines by a specified distance.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (distance, required, default: `10.0`): Distance
- `SEGMENTS` (number, required, default: `8`): Segments
- `JOIN_STYLE` (enum, required, default: `0`): Join style
- `MITER_LIMIT` (number, required, default: `2`): Miter limit
- `OUTPUT` (sink, required): Offset

---

### native:openurl

**Display Name:** Open file or URL

**Description:** Opens files in their default associated application, or URLs in the user's default web browser.

**Group:** File tools

**Parameters:**

- `URL` (string, required): URL or file path

---

### native:orderbyexpression

**Display Name:** Order by expression

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `EXPRESSION` (expression, required): Expression
- `ASCENDING` (boolean, required, default: `True`): Sort ascending
- `NULLS_FIRST` (boolean, required, default: `False`): Sort nulls first
- `OUTPUT` (sink, required): Ordered

---

### native:orientedminimumboundingbox

**Display Name:** Oriented minimum bounding box

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Bounding boxes

---

### native:orthogonalize

**Display Name:** Orthogonalize

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ANGLE_TOLERANCE` (number, required, default: `15.0`): Maximum angle tolerance (degrees)
- `MAX_ITERATIONS` (number, required, default: `1000`): Maximum algorithm iterations
- `OUTPUT` (sink, required): Orthogonalized

---

### native:package

**Display Name:** Package layers

**Group:** Database

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `OUTPUT` (fileDestination, required): Destination GeoPackage
- `OVERWRITE` (boolean, required, default: `False`): Overwrite existing GeoPackage
- `SAVE_STYLES` (boolean, required, default: `True`): Save layer styles into GeoPackage
- `SAVE_METADATA` (boolean, required, default: `True`): Save layer metadata into GeoPackage
- `SELECTED_FEATURES_ONLY` (boolean, required, default: `False`): Save only selected features
- `EXPORT_RELATED_LAYERS` (boolean, required, default: `False`): Export related layers following relations defined in the project

---

### native:pixelstopoints

**Display Name:** Raster pixels to points

**Description:** Creates a vector layer of points corresponding to each pixel in a raster layer.

**Group:** Vector creation

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Band number
- `FIELD_NAME` (string, required, default: `VALUE`): Field name
- `OUTPUT` (sink, required): Vector points

---

### native:pixelstopolygons

**Display Name:** Raster pixels to polygons

**Description:** Creates a vector layer of polygons corresponding to each pixel in a raster layer.

**Group:** Vector creation

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Band number
- `FIELD_NAME` (string, required, default: `VALUE`): Field name
- `OUTPUT` (sink, required): Vector polygons

---

### native:pointonsurface

**Display Name:** Point on surface

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ALL_PARTS` (boolean, required, default: `False`): Create point on surface for each part
- `OUTPUT` (sink, required): Point

---

### native:pointsalonglines

**Display Name:** Points along geometry

**Description:** Creates regularly spaced points along line features.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (distance, required, default: `1.0`): Distance
- `START_OFFSET` (distance, required, default: `0.0`): Start offset
- `END_OFFSET` (distance, required, default: `0.0`): End offset
- `OUTPUT` (sink, required): Interpolated points

---

### native:pointstopath

**Display Name:** Points to path

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `CLOSE_PATH` (boolean, optional, default: `False`): Create closed paths
- `ORDER_EXPRESSION` (expression, optional): Order expression
- `NATURAL_SORT` (boolean, optional, default: `False`): Sort text containing numbers naturally
- `GROUP_EXPRESSION` (expression, optional): Path group expression
- `OUTPUT` (sink, required): Paths
- `OUTPUT_TEXT_DIR` (folderDestination, optional): Directory for text output
- `ORDER_FIELD` (field, optional): Order field
- `GROUP_FIELD` (field, optional): Group field
- `DATE_FORMAT` (string, optional): Date format (if order field is DateTime)

---

### native:pointtolayer

**Display Name:** Create layer from point

**Group:** Vector geometry

**Parameters:**

- `INPUT` (point, required): Point
- `OUTPUT` (sink, required): Point

---

### native:poleofinaccessibility

**Display Name:** Pole of inaccessibility

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `TOLERANCE` (distance, required, default: `1.0`): Tolerance
- `OUTPUT` (sink, required): Point

---

### native:polygonfromlayerextent

**Display Name:** Extract layer extent

**Group:** Layer tools

**Parameters:**

- `INPUT` (layer, required): Input layer
- `ROUND_TO` (distance, required, default: `0`): Round values to
- `OUTPUT` (sink, required): Extent

---

### native:polygonize

**Display Name:** Polygonize

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `KEEP_FIELDS` (boolean, optional, default: `False`): Keep table structure of line layer
- `OUTPUT` (sink, required): Polygons

---

### native:polygonstolines

**Display Name:** Polygons to lines

**Description:** Converts polygons to lines.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Lines

---

### native:postgisexecutesql

**Display Name:** PostgreSQL execute SQL

**Group:** Database

**Parameters:**

- `DATABASE` (providerconnection, required): Database (connection name)
- `SQL` (string, required): SQL query

---

### native:printlayoutmapextenttolayer

**Display Name:** Print layout map extent to layer

**Description:** Creates a polygon layer containing the extent of a print layout map item.

**Group:** Cartography

**Parameters:**

- `LAYOUT` (layout, required): Print layout
- `MAP` (layoutitem, optional): Map item
- `CRS` (crs, optional): Override CRS
- `OUTPUT` (sink, required): Extent

---

### native:printlayouttoimage

**Display Name:** Export print layout as image

**Description:** Exports a print layout as an image.

**Group:** Cartography

**Parameters:**

- `LAYOUT` (layout, required): Print layout
- `LAYERS` (multilayer, optional): Map layers to assign to unlocked map item(s)
- `DPI` (number, optional): DPI (leave blank for default layout DPI)
- `GEOREFERENCE` (boolean, required, default: `True`): Generate world file
- `INCLUDE_METADATA` (boolean, required, default: `True`): Export RDF metadata (title, author, etc.)
- `ANTIALIAS` (boolean, required, default: `True`): Enable antialiasing
- `OUTPUT` (fileDestination, required): Image file

---

### native:printlayouttopdf

**Display Name:** Export print layout as PDF

**Description:** Exports a print layout as a PDF.

**Group:** Cartography

**Parameters:**

- `LAYOUT` (layout, required): Print layout
- `LAYERS` (multilayer, optional): Map layers to assign to unlocked map item(s)
- `DPI` (number, optional): DPI (leave blank for default layout DPI)
- `FORCE_VECTOR` (boolean, required, default: `False`): Always export as vectors
- `FORCE_RASTER` (boolean, required, default: `False`): Always export as raster
- `GEOREFERENCE` (boolean, required, default: `True`): Append georeference information
- `INCLUDE_METADATA` (boolean, required, default: `True`): Export RDF metadata (title, author, etc.)
- `DISABLE_TILED` (boolean, required, default: `False`): Disable tiled raster layer exports
- `SIMPLIFY` (boolean, required, default: `True`): Simplify geometries to reduce output file size
- `TEXT_FORMAT` (enum, required, default: `0`): Text export
- `IMAGE_COMPRESSION` (enum, required, default: `0`): Image compression
- `SEPARATE_LAYERS` (boolean, required, default: `False`): Export layers as separate PDF files
- `OUTPUT` (fileDestination, required): PDF file

---

### native:projectpointcartesian

**Display Name:** Project points (Cartesian)

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `BEARING` (number, required, default: `0`): Bearing (degrees from North)
- `DISTANCE` (distance, required, default: `1`): Distance
- `OUTPUT` (sink, required): Projected

---

### native:promotetomulti

**Display Name:** Promote to multipart

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Multiparts

---

### native:raiseexception

**Display Name:** Raise exception

**Description:** Raises an exception and cancels a model's execution.

**Group:** Modeler tools

**Parameters:**

- `MESSAGE` (string, required): Error message
- `CONDITION` (expression, optional): Condition

---

### native:raisemessage

**Display Name:** Raise message

**Description:** Raises an information message.

**Group:** Modeler tools

**Parameters:**

- `MESSAGE` (string, required): Information message
- `CONDITION` (expression, optional): Condition

---

### native:raisewarning

**Display Name:** Raise warning

**Description:** Raises an warning message.

**Group:** Modeler tools

**Parameters:**

- `MESSAGE` (string, required): Warning message
- `CONDITION` (expression, optional): Condition

---

### native:randomextract

**Display Name:** Random extract

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Input layer
- `METHOD` (enum, required, default: `0`): Method
- `NUMBER` (number, required, default: `10`): Number/percentage of features
- `OUTPUT` (sink, required): Extracted (random)

---

### native:randompointsinextent

**Display Name:** Random points in extent

**Group:** Vector creation

**Parameters:**

- `EXTENT` (extent, required): Input extent
- `POINTS_NUMBER` (number, required, default: `1`): Number of points
- `MIN_DISTANCE` (distance, optional, default: `0`): Minimum distance between points
- `TARGET_CRS` (crs, required, default: `ProjectCrs`): Target CRS
- `MAX_ATTEMPTS` (number, optional, default: `200`): Maximum number of search attempts given the minimum distance
- `OUTPUT` (sink, required): Random points

---

### native:randompointsinpolygons

**Display Name:** Random points in polygons

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input polygon layer
- `POINTS_NUMBER` (number, required, default: `1`): Number of points for each feature
- `MIN_DISTANCE` (distance, optional, default: `0`): Minimum distance between points
- `MIN_DISTANCE_GLOBAL` (distance, optional, default: `0`): Global minimum distance between points
- `MAX_TRIES_PER_POINT` (number, optional, default: `10`): Maximum number of search attempts (for Min. dist. > 0)
- `SEED` (number, optional): Random seed
- `INCLUDE_POLYGON_ATTRIBUTES` (boolean, required, default: `True`): Include polygon attributes
- `OUTPUT` (sink, required): Random points in polygons

---

### native:randompointsonlines

**Display Name:** Random points on lines

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input line layer
- `POINTS_NUMBER` (number, required, default: `1`): Number of points for each feature
- `MIN_DISTANCE` (distance, optional, default: `0`): Minimum distance between points
- `MIN_DISTANCE_GLOBAL` (distance, optional, default: `0`): Global minimum distance between points
- `MAX_TRIES_PER_POINT` (number, optional, default: `10`): Maximum number of search attempts (for Min. dist. > 0)
- `SEED` (number, optional): Random seed
- `INCLUDE_LINE_ATTRIBUTES` (boolean, required, default: `True`): Include line attributes
- `OUTPUT` (sink, required): Random points on lines

---

### native:rasterbooleanand

**Display Name:** Raster boolean AND

**Description:** Calculates the boolean AND for a set of input raster layers

**Group:** Raster analysis

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `REF_LAYER` (raster, required): Reference layer
- `NODATA_AS_FALSE` (boolean, required, default: `False`): Treat NoData values as false
- `NO_DATA` (number, required, default: `-9999`): Output NoData value
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:rastercalc

**Display Name:** Raster calculator

**Group:** Raster analysis

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `EXPRESSION` (expression, required): Expression
- `EXTENT` (extent, optional): Output extent
- `CELL_SIZE` (number, optional): Output cell size (leave empty to set automatically)
- `CRS` (crs, optional): Output CRS
- `OUTPUT` (rasterDestination, required): Calculated

---

### native:rasterize

**Display Name:** Convert map to raster

**Description:** Renders the map canvas to a raster file.

**Group:** Raster tools

**Parameters:**

- `EXTENT` (extent, required): Minimum extent to render
- `EXTENT_BUFFER` (number, optional, default: `0`): Buffer around tiles in map units
- `TILE_SIZE` (number, required, default: `1024`): Tile size
- `MAP_UNITS_PER_PIXEL` (number, optional, default: `100`): Map units per pixel
- `MAKE_BACKGROUND_TRANSPARENT` (boolean, required, default: `False`): Make background transparent
- `MAP_THEME` (maptheme, optional): Map theme to render
- `LAYERS` (multilayer, optional): Layers to render
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:rasterlayerproperties

**Display Name:** Raster layer properties

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, optional): Band number

---

### native:rasterlayerstatistics

**Display Name:** Raster layer statistics

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `OUTPUT_HTML_FILE` (fileDestination, optional): Statistics

---

### native:rasterlayeruniquevaluesreport

**Display Name:** Raster layer unique values report

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `OUTPUT_HTML_FILE` (fileDestination, optional): Unique values report
- `OUTPUT_TABLE` (sink, optional): Unique values table

---

### native:rasterlayerzonalstats

**Display Name:** Raster layer zonal statistics

**Description:** Calculates statistics for a raster layer's values, categorized by zones defined in another raster layer.

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `ZONES` (raster, required): Zones layer
- `ZONES_BAND` (band, required, default: `1`): Zones band number
- `REF_LAYER` (enum, required, default: `0`): Reference layer
- `OUTPUT_TABLE` (sink, required): Statistics

---

### native:rasterlogicalor

**Display Name:** Raster boolean OR

**Description:** Calculates the boolean OR for a set of input raster layers

**Group:** Raster analysis

**Parameters:**

- `INPUT` (multilayer, required): Input layers
- `REF_LAYER` (raster, required): Reference layer
- `NODATA_AS_FALSE` (boolean, required, default: `False`): Treat NoData values as false
- `NO_DATA` (number, required, default: `-9999`): Output NoData value
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output layer

---

### native:rastersampling

**Display Name:** Sample raster values

**Description:** Samples raster values under a set of points.

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `RASTERCOPY` (raster, required): Raster layer
- `COLUMN_PREFIX` (string, optional, default: `SAMPLE_`): Output column prefix
- `OUTPUT` (sink, required): Sampled

---

### native:rastersurfacevolume

**Display Name:** Raster surface volume

**Description:** Calculates the volume under a raster grid's surface.

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `LEVEL` (number, required, default: `0`): Base level
- `METHOD` (enum, required): Method
- `OUTPUT_HTML_FILE` (fileDestination, optional): Surface volume report
- `OUTPUT_TABLE` (sink, optional): Surface volume table

---

### native:reclassifybylayer

**Display Name:** Reclassify by layer

**Group:** Raster analysis

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Band number
- `INPUT_TABLE` (source, required): Layer containing class breaks
- `MIN_FIELD` (field, required): Minimum class value field
- `MAX_FIELD` (field, required): Maximum class value field
- `VALUE_FIELD` (field, required): Output value field
- `NO_DATA` (number, required, default: `-9999`): Output NoData value
- `RANGE_BOUNDARIES` (enum, required, default: `0`): Range boundaries
- `NODATA_FOR_MISSING` (boolean, required, default: `False`): Use NoData when no range matches value
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Reclassified raster

---

### native:reclassifybytable

**Display Name:** Reclassify by table

**Group:** Raster analysis

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Band number
- `TABLE` (matrix, required): Reclassification table
- `NO_DATA` (number, required, default: `-9999`): Output NoData value
- `RANGE_BOUNDARIES` (enum, required, default: `0`): Range boundaries
- `NODATA_FOR_MISSING` (boolean, required, default: `False`): Use NoData when no range matches value
- `DATA_TYPE` (enum, required, default: `5`): Output data type
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Reclassified raster

---

### native:rectanglesovalsdiamonds

**Display Name:** Rectangles, ovals, diamonds

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `SHAPE` (enum, required, default: `0`): Shape
- `WIDTH` (distance, required, default: `1.0`): Width
- `HEIGHT` (distance, required, default: `1.0`): Height
- `ROTATION` (number, optional, default: `0.0`): Rotation
- `SEGMENTS` (number, required, default: `36`): Segments
- `OUTPUT` (sink, required): Polygon

---

### native:refactorfields

**Display Name:** Refactor fields

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELDS_MAPPING` (fields_mapping, required): Fields mapping
- `OUTPUT` (sink, required): Refactored

---

### native:removeduplicatesbyattribute

**Display Name:** Delete duplicates by attribute

**Description:** Removes duplicate rows by a field value (or multiple field values).

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELDS` (field, required): Field to match duplicates by
- `OUTPUT` (sink, required): Filtered (no duplicates)
- `DUPLICATES` (sink, optional): Filtered (duplicates)

---

### native:removeduplicatevertices

**Display Name:** Remove duplicate vertices

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `TOLERANCE` (distance, required, default: `1e-06`): Tolerance
- `USE_Z_VALUE` (boolean, required, default: `False`): Use Z Value
- `OUTPUT` (sink, required): Cleaned

---

### native:removenullgeometries

**Display Name:** Remove null geometries

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `REMOVE_EMPTY` (boolean, required, default: `False`): Also remove empty geometries
- `OUTPUT` (sink, optional): Non null geometries
- `NULL_OUTPUT` (sink, optional): Null geometries

---

### native:renamelayer

**Display Name:** Rename layer

**Group:** Modeler tools

**Parameters:**

- `INPUT` (layer, required): Layer
- `NAME` (string, required): New name

---

### native:renametablefield

**Display Name:** Rename field

**Description:** Renames an existing field from a vector layer.

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Field to rename
- `NEW_NAME` (string, required): New field name
- `OUTPUT` (sink, required): Renamed

---

### native:repairshapefile

**Display Name:** Repair Shapefile

**Description:** Repairs broken Shapefiles by recreating SHX files.

**Group:** Vector general

**Parameters:**

- `INPUT` (file, required): Input Shapefile

---

### native:reprojectlayer

**Display Name:** Reproject layer

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `TARGET_CRS` (crs, required, default: `EPSG:4326`): Target CRS
- `CONVERT_CURVED_GEOMETRIES` (boolean, optional, default: `False`): Convert curved geometries to straight segments
- `OPERATION` (coordinateoperation, optional): Coordinate operation
- `OUTPUT` (sink, required): Reprojected

---

### native:rescaleraster

**Display Name:** Rescale raster

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input raster
- `BAND` (band, required, default: `1`): Band number
- `MINIMUM` (number, required, default: `0`): New minimum value
- `MAXIMUM` (number, required, default: `255`): New maximum value
- `NODATA` (number, optional): New NoData value
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Rescaled

---

### native:retainfields

**Display Name:** Retain fields

**Description:** Retains selected fields from a vector layer.

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELDS` (field, required): Fields to retain
- `OUTPUT` (sink, required): Retained fields

---

### native:reverselinedirection

**Display Name:** Reverse line direction

**Description:** Reverses the direction of curve or LineString geometries.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Reversed

---

### native:rotatefeatures

**Display Name:** Rotate

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ANGLE` (number, required, default: `0.0`): Rotation (degrees clockwise)
- `ANCHOR` (point, optional): Rotation anchor point
- `OUTPUT` (sink, required): Rotated

---

### native:roundness

**Display Name:** Roundness

**Description:** Calculates the roundness of polygon features.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Roundness

---

### native:roundrastervalues

**Display Name:** Round raster

**Group:** Raster analysis

**Parameters:**

- `INPUT` (raster, required): Input raster
- `BAND` (band, required, default: `1`): Band number
- `ROUNDING_DIRECTION` (enum, required, default: `1`): Rounding direction
- `DECIMAL_PLACES` (number, required, default: `2`): Number of decimals places
- `BASE_N` (number, required, default: `10`): Base n for rounding to multiples of n
- `CREATE_OPTIONS` (string, optional): Creation options
- `OUTPUT` (rasterDestination, required): Output raster

---

### native:ruggednessindex

**Display Name:** Ruggedness index

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT` (raster, required): Elevation layer
- `Z_FACTOR` (number, required, default: `1`): Z factor
- `OUTPUT` (rasterDestination, required): Ruggedness

---

### native:savefeatures

**Display Name:** Save vector features to file

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Vector features
- `OUTPUT` (fileDestination, required): Saved features
- `LAYER_NAME` (string, optional): Layer name
- `DATASOURCE_OPTIONS` (string, optional): GDAL dataset options (separate individual options with semicolons)
- `LAYER_OPTIONS` (string, optional): GDAL layer options (separate individual options with semicolons)
- `ACTION_ON_EXISTING_FILE` (enum, required, default: `0`): Action to take on pre-existing file

---

### native:savelog

**Display Name:** Save log to file

**Description:** Saves the model's log contents to a file.

**Group:** Modeler tools

**Parameters:**

- `OUTPUT` (fileDestination, required): Log file
- `USE_HTML` (boolean, required, default: `False`): Use HTML formatting

---

### native:saveselectedfeatures

**Display Name:** Extract selected features

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input layer
- `OUTPUT` (sink, required): Selected features

---

### native:segmentizebymaxangle

**Display Name:** Segmentize by maximum angle

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ANGLE` (number, required, default: `5.0`): Maximum angle between vertices (degrees)
- `OUTPUT` (sink, required): Segmentized

---

### native:segmentizebymaxdistance

**Display Name:** Segmentize by maximum distance

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (distance, required, default: `1.0`): Maximum offset distance
- `OUTPUT` (sink, required): Segmentized

---

### native:selectbylocation

**Display Name:** Select by location

**Group:** Vector selection

**Parameters:**

- `INPUT` (vector, required): Select features from
- `PREDICATE` (enum, required, default: `[0]`): Where the features (geometric predicate)
- `INTERSECT` (source, required): By comparing to the features from
- `METHOD` (enum, required, default: `0`): Modify current selection by

---

### native:selectwithindistance

**Display Name:** Select within distance

**Group:** Vector selection

**Parameters:**

- `INPUT` (vector, required): Select features from
- `REFERENCE` (source, required): By comparing to the features from
- `DISTANCE` (distance, required, default: `100`): Where the features are within
- `METHOD` (enum, required, default: `0`): Modify current selection by

---

### native:serviceareafromlayer

**Display Name:** Service area (from layer)

**Group:** Network analysis

**Parameters:**

- `INPUT` (source, required): Vector layer representing network
- `STRATEGY` (enum, required, default: `0`): Path type to calculate
- `DIRECTION_FIELD` (field, optional): Direction field
- `VALUE_FORWARD` (string, optional): Value for forward direction
- `VALUE_BACKWARD` (string, optional): Value for backward direction
- `VALUE_BOTH` (string, optional): Value for both directions
- `DEFAULT_DIRECTION` (enum, required, default: `2`): Default direction
- `SPEED_FIELD` (field, optional): Speed field
- `DEFAULT_SPEED` (number, required, default: `50`): Default speed (km/h)
- `TOLERANCE` (distance, required, default: `0`): Topology tolerance
- `START_POINTS` (source, required): Vector layer with start points
- `TRAVEL_COST` (number, optional, default: `0`): Travel cost (distance for 'Shortest', time for 'Fastest')
- `TRAVEL_COST2` (number, required, default: `0`): Travel cost (distance for 'Shortest', time for 'Fastest')
- `INCLUDE_BOUNDS` (boolean, optional, default: `False`): Include upper/lower bound points
- `POINT_TOLERANCE` (distance, optional): Maximum point distance from network
- `OUTPUT_LINES` (sink, optional): Service area (lines)
- `OUTPUT` (sink, optional): Service area (boundary nodes)
- `OUTPUT_NON_ROUTABLE` (sink, optional): Non-routable features

---

### native:serviceareafrompoint

**Display Name:** Service area (from point)

**Group:** Network analysis

**Parameters:**

- `INPUT` (source, required): Vector layer representing network
- `STRATEGY` (enum, required, default: `0`): Path type to calculate
- `DIRECTION_FIELD` (field, optional): Direction field
- `VALUE_FORWARD` (string, optional): Value for forward direction
- `VALUE_BACKWARD` (string, optional): Value for backward direction
- `VALUE_BOTH` (string, optional): Value for both directions
- `DEFAULT_DIRECTION` (enum, required, default: `2`): Default direction
- `SPEED_FIELD` (field, optional): Speed field
- `DEFAULT_SPEED` (number, required, default: `50`): Default speed (km/h)
- `TOLERANCE` (distance, required, default: `0`): Topology tolerance
- `START_POINT` (point, required): Start point
- `TRAVEL_COST` (number, optional, default: `0`): Travel cost (distance for 'Shortest', time for 'Fastest')
- `TRAVEL_COST2` (number, required, default: `0`): Travel cost (distance for 'Shortest', time for 'Fastest')
- `POINT_TOLERANCE` (distance, optional): Maximum point distance from network
- `INCLUDE_BOUNDS` (boolean, optional, default: `False`): Include upper/lower bound points
- `OUTPUT_LINES` (sink, optional): Service area (lines)
- `OUTPUT` (sink, optional): Service area (boundary nodes)

---

### native:setlayerencoding

**Display Name:** Set layer encoding

**Description:** Sets the encoding used for reading a layer's attributes

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input layer
- `ENCODING` (string, required): Encoding

---

### native:setlayerstyle

**Display Name:** Set layer style

**Group:** Cartography

**Parameters:**

- `INPUT` (layer, required): Layer
- `STYLE` (file, required): Style file

---

### native:setmfromraster

**Display Name:** Set M value from raster

**Description:** Sets the M value for vertices to values sampled from a raster layer.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `RASTER` (raster, required): Raster layer
- `BAND` (band, required, default: `1`): Band number
- `NODATA` (number, required, default: `0.0`): Value for NoData or non-intersecting vertices
- `SCALE` (number, required, default: `1.0`): Scale factor
- `OFFSET` (number, required, default: `0.0`): Offset
- `OUTPUT` (sink, required): Draped

---

### native:setmvalue

**Display Name:** Set M value

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `M_VALUE` (number, required, default: `0.0`): M Value
- `OUTPUT` (sink, required): M Added

---

### native:setprojectvariable

**Display Name:** Set project variable

**Description:** Sets an expression variable for the current project

**Group:** Modeler tools

**Parameters:**

- `NAME` (string, required): Variable name
- `VALUE` (string, required): Variable value

---

### native:setzfromraster

**Display Name:** Drape (set Z value from raster)

**Description:** Sets the z value for vertices to values sampled from a raster layer.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `RASTER` (raster, required): Raster layer
- `BAND` (band, required, default: `1`): Band number
- `NODATA` (number, required, default: `0.0`): Value for NoData or non-intersecting vertices
- `SCALE` (number, required, default: `1.0`): Scale factor
- `OFFSET` (number, required, default: `0.0`): Offset
- `OUTPUT` (sink, required): Draped

---

### native:setzvalue

**Display Name:** Set Z value

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `Z_VALUE` (number, required, default: `0.0`): Z Value
- `OUTPUT` (sink, required): Z Added

---

### native:shortestline

**Display Name:** Shortest line between features

**Group:** Vector analysis

**Parameters:**

- `SOURCE` (source, required): Source layer
- `DESTINATION` (source, required): Destination layer
- `METHOD` (enum, required, default: `0`): Method
- `NEIGHBORS` (number, required, default: `1`): Maximum number of neighbors
- `DISTANCE` (distance, optional): Maximum distance
- `OUTPUT` (sink, required): Shortest lines

---

### native:shortestpathlayertopoint

**Display Name:** Shortest path (layer to point)

**Group:** Network analysis

**Parameters:**

- `INPUT` (source, required): Vector layer representing network
- `STRATEGY` (enum, required, default: `0`): Path type to calculate
- `DIRECTION_FIELD` (field, optional): Direction field
- `VALUE_FORWARD` (string, optional): Value for forward direction
- `VALUE_BACKWARD` (string, optional): Value for backward direction
- `VALUE_BOTH` (string, optional): Value for both directions
- `DEFAULT_DIRECTION` (enum, required, default: `2`): Default direction
- `SPEED_FIELD` (field, optional): Speed field
- `DEFAULT_SPEED` (number, required, default: `50`): Default speed (km/h)
- `TOLERANCE` (distance, required, default: `0`): Topology tolerance
- `START_POINTS` (source, required): Vector layer with start points
- `END_POINT` (point, required): End point
- `POINT_TOLERANCE` (distance, optional): Maximum point distance from network
- `OUTPUT` (sink, required): Shortest path
- `OUTPUT_NON_ROUTABLE` (sink, optional): Non-routable features

---

### native:shortestpathpointtolayer

**Display Name:** Shortest path (point to layer)

**Group:** Network analysis

**Parameters:**

- `INPUT` (source, required): Vector layer representing network
- `STRATEGY` (enum, required, default: `0`): Path type to calculate
- `DIRECTION_FIELD` (field, optional): Direction field
- `VALUE_FORWARD` (string, optional): Value for forward direction
- `VALUE_BACKWARD` (string, optional): Value for backward direction
- `VALUE_BOTH` (string, optional): Value for both directions
- `DEFAULT_DIRECTION` (enum, required, default: `2`): Default direction
- `SPEED_FIELD` (field, optional): Speed field
- `DEFAULT_SPEED` (number, required, default: `50`): Default speed (km/h)
- `TOLERANCE` (distance, required, default: `0`): Topology tolerance
- `START_POINT` (point, required): Start point
- `END_POINTS` (source, required): Vector layer with end points
- `POINT_TOLERANCE` (distance, optional): Maximum point distance from network
- `OUTPUT` (sink, required): Shortest path
- `OUTPUT_NON_ROUTABLE` (sink, optional): Non-routable features

---

### native:shortestpathpointtopoint

**Display Name:** Shortest path (point to point)

**Group:** Network analysis

**Parameters:**

- `INPUT` (source, required): Vector layer representing network
- `STRATEGY` (enum, required, default: `0`): Path type to calculate
- `DIRECTION_FIELD` (field, optional): Direction field
- `VALUE_FORWARD` (string, optional): Value for forward direction
- `VALUE_BACKWARD` (string, optional): Value for backward direction
- `VALUE_BOTH` (string, optional): Value for both directions
- `DEFAULT_DIRECTION` (enum, required, default: `2`): Default direction
- `SPEED_FIELD` (field, optional): Speed field
- `DEFAULT_SPEED` (number, required, default: `50`): Default speed (km/h)
- `TOLERANCE` (distance, required, default: `0`): Topology tolerance
- `START_POINT` (point, required): Start point
- `END_POINT` (point, required): End point
- `OUTPUT` (sink, required): Shortest path
- `POINT_TOLERANCE` (distance, optional): Maximum point distance from network

---

### native:shpencodinginfo

**Display Name:** Extract Shapefile encoding

**Description:** Extracts the attribute encoding information embedded in a Shapefile.

**Group:** Vector general

**Parameters:**

- `INPUT` (file, required): Input layer

---

### native:simplifygeometries

**Display Name:** Simplify

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `METHOD` (enum, required, default: `0`): Simplification method
- `TOLERANCE` (distance, required, default: `1.0`): Tolerance
- `OUTPUT` (sink, required): Simplified

---

### native:singlesidedbuffer

**Display Name:** Single sided buffer

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DISTANCE` (distance, required, default: `10`): Distance
- `SIDE` (enum, required, default: `0`): Side
- `SEGMENTS` (number, required, default: `8`): Segments
- `JOIN_STYLE` (enum, required, default: `0`): Join style
- `MITER_LIMIT` (number, required, default: `2`): Miter limit
- `OUTPUT` (sink, required): Buffered

---

### native:slope

**Display Name:** Slope

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT` (raster, required): Elevation layer
- `Z_FACTOR` (number, required, default: `1`): Z factor
- `OUTPUT` (rasterDestination, required): Slope

---

### native:smoothgeometry

**Display Name:** Smooth

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `ITERATIONS` (number, required, default: `1`): Iterations
- `OFFSET` (number, required, default: `0.25`): Offset
- `MAX_ANGLE` (number, required, default: `180.0`): Maximum node angle to smooth
- `OUTPUT` (sink, required): Smoothed

---

### native:snapgeometries

**Display Name:** Snap geometries to layer

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `REFERENCE_LAYER` (source, required): Reference layer
- `TOLERANCE` (distance, required, default: `10.0`): Tolerance
- `BEHAVIOR` (enum, required, default: `[0]`): Behavior
- `OUTPUT` (sink, required): Snapped geometry

---

### native:snappointstogrid

**Display Name:** Snap points to grid

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `HSPACING` (distance, required, default: `1`): X Grid Spacing
- `VSPACING` (distance, required, default: `1`): Y Grid Spacing
- `ZSPACING` (number, required, default: `0`): Z Grid Spacing
- `MSPACING` (number, required, default: `0`): M Grid Spacing
- `OUTPUT` (sink, required): Snapped

---

### native:spatialiteexecutesql

**Display Name:** SpatiaLite execute SQL

**Group:** Database

**Parameters:**

- `DATABASE` (vector, required): Database layer (or file)
- `SQL` (string, required): SQL query

---

### native:spatialiteexecutesqlregistered

**Display Name:** SpatiaLite execute SQL (registered DB)

**Group:** Database

**Parameters:**

- `DATABASE` (providerconnection, required): Database (connection name)
- `SQL` (string, required): SQL query

---

### native:splitfeaturesbycharacter

**Display Name:** Split features by character

**Description:** Splits features into multiple output features by splitting a field by a character.

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Split using values in field
- `CHAR` (string, required): Split values using character
- `REGEX` (boolean, required): Use regular expression separator
- `OUTPUT` (sink, required): Split

---

### native:splitlinesbylength

**Display Name:** Split lines by maximum length

**Description:** Splits lines into parts which are no longer than a specified length.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `LENGTH` (distance, required, default: `10`): Maximum line length
- `OUTPUT` (sink, required): Split

---

### native:splitvectorlayer

**Display Name:** Split vector layer

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Unique ID field
- `PREFIX_FIELD` (boolean, required, default: `True`): Add field prefix to file names
- `FILE_TYPE` (enum, optional, default: `0`): Output file type
- `OUTPUT` (folderDestination, required): Output directory

---

### native:splitwithlines

**Display Name:** Split with lines

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `LINES` (source, required): Split layer
- `OUTPUT` (sink, required): Split

---

### native:stdbscanclustering

**Display Name:** ST-DBSCAN clustering

**Description:** Clusters spatiotemporal point features using a time and density based scan algorithm.

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `DATETIME_FIELD` (field, required): Date/time field
- `MIN_SIZE` (number, required, default: `5`): Minimum cluster size
- `EPS` (distance, required, default: `1`): Maximum distance between clustered points
- `EPS2` (duration, required, default: `0`): Maximum time duration between clustered points
- `DBSCAN*` (boolean, optional, default: `False`): Treat border points as noise (DBSCAN*)
- `FIELD_NAME` (string, required, default: `CLUSTER_ID`): Cluster field name
- `SIZE_FIELD_NAME` (string, required, default: `CLUSTER_SIZE`): Cluster size field name
- `OUTPUT` (sink, required): Clusters

---

### native:stringconcatenation

**Display Name:** String concatenation

**Group:** Modeler tools

**Parameters:**

- `INPUT_1` (string, required): Input 1
- `INPUT_2` (string, required): Input 2

---

### native:stylefromproject

**Display Name:** Create style database from project

**Description:** Creates a style database by extracting all symbols, color ramps, text formats and label settings from a QGIS project.

**Group:** Cartography

**Parameters:**

- `INPUT` (file, optional): Input project (leave blank to use current)
- `OUTPUT` (fileDestination, required): Output style database
- `OBJECTS` (enum, required, default: `[0, 1, 2, 3]`): Objects to extract

---

### native:subdivide

**Display Name:** Subdivide

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `MAX_NODES` (number, required, default: `256`): Maximum nodes in parts
- `OUTPUT` (sink, required): Subdivided

---

### native:sumlinelengths

**Display Name:** Sum line lengths

**Group:** Vector analysis

**Parameters:**

- `POLYGONS` (source, required): Polygons
- `LINES` (source, required): Lines
- `LEN_FIELD` (string, required, default: `LENGTH`): Lines length field name
- `COUNT_FIELD` (string, required, default: `COUNT`): Lines count field name
- `OUTPUT` (sink, required): Line length

---

### native:swapxy

**Display Name:** Swap X and Y coordinates

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Swapped

---

### native:symmetricaldifference

**Display Name:** Symmetrical difference

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAY` (source, required): Overlay layer
- `OVERLAY_FIELDS_PREFIX` (string, optional, default: `NULL`): Overlay fields prefix
- `OUTPUT` (sink, required): Symmetrical difference
- `GRID_SIZE` (number, optional): Grid size

---

### native:taperedbuffer

**Display Name:** Tapered buffers

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `START_WIDTH` (number, required, default: `0.0`): Start width
- `END_WIDTH` (number, required, default: `1`): End width
- `SEGMENTS` (number, required, default: `16`): Segments
- `OUTPUT` (sink, required): Buffered

---

### native:tilesxyzdirectory

**Display Name:** Generate XYZ tiles (Directory)

**Group:** Raster tools

**Parameters:**

- `EXTENT` (extent, required): Extent
- `ZOOM_MIN` (number, required, default: `12`): Minimum zoom
- `ZOOM_MAX` (number, required, default: `12`): Maximum zoom
- `DPI` (number, required, default: `96`): DPI
- `BACKGROUND_COLOR` (color, optional, default: `<QColor: RGBA 0, 0, 0, 0>`): Background color
- `ANTIALIAS` (boolean, required, default: `True`): Enable antialiasing
- `TILE_FORMAT` (enum, required, default: `0`): Tile format
- `QUALITY` (number, required, default: `75`): Quality (JPG only)
- `METATILESIZE` (number, required, default: `4`): Metatile size
- `TILE_WIDTH` (number, required, default: `256`): Tile width
- `TILE_HEIGHT` (number, required, default: `256`): Tile height
- `TMS_CONVENTION` (boolean, optional, default: `False`): Use inverted tile Y axis (TMS convention)
- `HTML_TITLE` (string, optional): Leaflet HTML output title
- `HTML_ATTRIBUTION` (string, optional): Leaflet HTML output attribution
- `HTML_OSM` (boolean, optional, default: `False`): Include OpenStreetMap basemap in Leaflet HTML output
- `OUTPUT_DIRECTORY` (folderDestination, required): Output directory
- `OUTPUT_HTML` (fileDestination, optional): Output html (Leaflet)

---

### native:tilesxyzmbtiles

**Display Name:** Generate XYZ tiles (MBTiles)

**Group:** Raster tools

**Parameters:**

- `EXTENT` (extent, required): Extent
- `ZOOM_MIN` (number, required, default: `12`): Minimum zoom
- `ZOOM_MAX` (number, required, default: `12`): Maximum zoom
- `DPI` (number, required, default: `96`): DPI
- `BACKGROUND_COLOR` (color, optional, default: `<QColor: RGBA 0, 0, 0, 0>`): Background color
- `ANTIALIAS` (boolean, required, default: `True`): Enable antialiasing
- `TILE_FORMAT` (enum, required, default: `0`): Tile format
- `QUALITY` (number, required, default: `75`): Quality (JPG only)
- `METATILESIZE` (number, required, default: `4`): Metatile size
- `OUTPUT_FILE` (fileDestination, required): Output

---

### native:tinmeshcreation

**Display Name:** TIN Mesh Creation

**Description:** Creates a TIN mesh layer from vector layers

**Group:** Mesh

**Parameters:**

- `SOURCE_DATA` (tininputlayers, required): Input layers
- `MESH_FORMAT` (enum, required, default: `0`): Output format
- `CRS_OUTPUT` (crs, optional): Output coordinate system
- `OUTPUT_MESH` (fileDestination, required): Output file

---

### native:transect

**Display Name:** Transect

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `LENGTH` (distance, required, default: `5.0`): Length of the transect
- `ANGLE` (number, required, default: `90.0`): Angle in degrees from the original line at the vertices
- `SIDE` (enum, required): Side to create the transects
- `OUTPUT` (sink, required): Transect

---

### native:transferannotationsfrommain

**Display Name:** Transfer annotations from main layer

**Group:** Cartography

**Parameters:**

- `LAYER_NAME` (string, required, default: `Annotations`): New layer name

---

### native:translategeometry

**Display Name:** Translate

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `DELTA_X` (distance, required, default: `0.0`): Offset distance (x-axis)
- `DELTA_Y` (distance, required, default: `0.0`): Offset distance (y-axis)
- `DELTA_Z` (number, required, default: `0.0`): Offset distance (z-axis)
- `DELTA_M` (number, required, default: `0.0`): Offset distance (m values)
- `OUTPUT` (sink, required): Translated

---

### native:truncatetable

**Display Name:** Truncate table

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input layer

---

### native:union

**Display Name:** Union

**Group:** Vector overlay

**Parameters:**

- `INPUT` (source, required): Input layer
- `OVERLAY` (source, optional): Overlay layer
- `OVERLAY_FIELDS_PREFIX` (string, optional, default: `NULL`): Overlay fields prefix
- `OUTPUT` (sink, required): Union
- `GRID_SIZE` (number, optional): Grid size

---

### native:uploadgpsdata

**Display Name:** Upload GPS data to device

**Group:** GPS

**Parameters:**

- `INPUT` (file, required): Input file
- `DEVICE` (string, required): Device
- `PORT` (string, required): Port
- `FEATURE_TYPE` (enum, required, default: `0`): Feature type

---

### native:virtualrastercalc

**Display Name:** Raster calculator (virtual)

**Group:** Raster analysis

**Parameters:**

- `LAYERS` (multilayer, required): Input layers
- `EXPRESSION` (expression, required): Expression
- `EXTENT` (extent, optional): Output extent
- `CELL_SIZE` (number, optional): Output cell size (leave empty to set automatically)
- `CRS` (crs, optional): Output CRS
- `LAYER_NAME` (string, optional): Output layer name

---

### native:voronoipolygons

**Display Name:** Voronoi polygons

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `BUFFER` (number, required, default: `0`): Buffer region (% of extent)
- `TOLERANCE` (number, optional, default: `0`): Tolerance
- `COPY_ATTRIBUTES` (boolean, required, default: `True`): Copy attributes from input features
- `OUTPUT` (sink, required): Voronoi polygons

---

### native:wedgebuffers

**Display Name:** Create wedge buffers

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `AZIMUTH` (number, required, default: `0`): Azimuth (degrees from North)
- `WIDTH` (number, required, default: `45`): Wedge width (in degrees)
- `OUTER_RADIUS` (number, required, default: `1`): Outer radius
- `INNER_RADIUS` (number, optional, default: `0`): Inner radius
- `OUTPUT` (sink, required): Buffers

---

### native:writevectortiles_mbtiles

**Display Name:** Write Vector Tiles (MBTiles)

**Group:** Vector tiles

**Parameters:**

- `OUTPUT` (vectorTileDestination, required): Destination MBTiles
- `LAYERS` (vectortilewriterlayers, required): Input layers
- `MIN_ZOOM` (number, required, default: `0`): Minimum zoom level
- `MAX_ZOOM` (number, required, default: `3`): Maximum zoom level
- `EXTENT` (extent, optional): Extent
- `META_NAME` (string, optional): Metadata: Name
- `META_DESCRIPTION` (string, optional): Metadata: Description
- `META_ATTRIBUTION` (string, optional): Metadata: Attribution
- `META_VERSION` (string, optional): Metadata: Version
- `META_TYPE` (string, optional): Metadata: Type
- `META_CENTER` (string, optional): Metadata: Center

---

### native:writevectortiles_xyz

**Display Name:** Write Vector Tiles (XYZ)

**Group:** Vector tiles

**Parameters:**

- `OUTPUT_DIRECTORY` (folderDestination, required): Output directory
- `XYZ_TEMPLATE` (string, required, default: `{z}/{x}/{y}.pbf`): File template
- `LAYERS` (vectortilewriterlayers, required): Input layers
- `MIN_ZOOM` (number, required, default: `0`): Minimum zoom level
- `MAX_ZOOM` (number, required, default: `3`): Maximum zoom level
- `EXTENT` (extent, optional): Extent

---

### native:zonalhistogram

**Display Name:** Zonal histogram

**Group:** Raster analysis

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Band number
- `INPUT_VECTOR` (source, required): Vector layer containing zones
- `COLUMN_PREFIX` (string, optional, default: `HISTO_`): Output column prefix
- `OUTPUT` (sink, required): Output zones

---

### native:zonalstatistics

**Display Name:** Zonal statistics (in place)

**Description:** Calculates statistics for a raster layer's values for each feature of an overlapping polygon vector layer.

**Group:** Raster analysis

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Raster band
- `INPUT_VECTOR` (vector, required): Vector layer containing zones
- `COLUMN_PREFIX` (string, required, default: `_`): Output column prefix
- `STATISTICS` (enum, required, default: `[0, 1, 2]`): Statistics to calculate

---

### native:zonalstatisticsfb

**Display Name:** Zonal statistics

**Group:** Raster analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `INPUT_RASTER` (raster, required): Raster layer
- `RASTER_BAND` (band, required, default: `1`): Raster band
- `COLUMN_PREFIX` (string, required, default: `_`): Output column prefix
- `STATISTICS` (enum, required, default: `[0, 1, 2]`): Statistics to calculate
- `OUTPUT` (sink, required): Zonal Statistics

---

## QGIS

Provider ID: `qgis`
Total algorithms: 50

### qgis:advancedpythonfieldcalculator

**Display Name:** Advanced Python field calculator

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD_NAME` (string, required, default: `NewField`): Result field name
- `FIELD_TYPE` (enum, required): Field type
- `FIELD_LENGTH` (number, required, default: `10`): Field length
- `FIELD_PRECISION` (number, required, default: `3`): Field precision
- `GLOBAL` (string, optional): Global expression
- `FORMULA` (string, required, default: `value = `): Formula
- `OUTPUT` (sink, required): Calculated

---

### qgis:barplot

**Display Name:** Bar plot

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input layer
- `NAME_FIELD` (field, required): Category name field
- `VALUE_FIELD` (field, required): Value field
- `OUTPUT` (fileDestination, required): Bar plot

---

### qgis:boxplot

**Display Name:** Box plot

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input layer
- `NAME_FIELD` (field, required): Category name field
- `VALUE_FIELD` (field, required): Value field
- `MSD` (enum, required, default: `0`): Additional Statistic Lines
- `OUTPUT` (fileDestination, required): Box plot

---

### qgis:checkvalidity

**Display Name:** Check validity

**Group:** Vector geometry

**Parameters:**

- `INPUT_LAYER` (source, required): Input layer
- `METHOD` (enum, required, default: `2`): Method
- `IGNORE_RING_SELF_INTERSECTION` (boolean, required, default: `False`): Ignore ring self intersections
- `VALID_OUTPUT` (sink, optional): Valid output
- `INVALID_OUTPUT` (sink, optional): Invalid output
- `ERROR_OUTPUT` (sink, optional): Error output

---

### qgis:climbalongline

**Display Name:** Climb along line

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Line layer
- `OUTPUT` (sink, required): Climb layer

---

### qgis:convertgeometrytype

**Display Name:** Convert geometry type

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `TYPE` (enum, required): New geometry type
- `OUTPUT` (sink, required): Converted

---

### qgis:definecurrentprojection

**Display Name:** Define Shapefile projection

**Description:** Changes a Shapefile's projection to a new CRS without reprojecting features

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Input Shapefile
- `CRS` (crs, required, default: `EPSG:4326`): CRS

---

### qgis:distancematrix

**Display Name:** Distance matrix

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input point layer
- `INPUT_FIELD` (field, required): Input unique ID field
- `TARGET` (source, required): Target point layer
- `TARGET_FIELD` (field, required): Target unique ID field
- `MATRIX_TYPE` (enum, required, default: `0`): Output matrix type
- `NEAREST_POINTS` (number, required, default: `0`): Use only the nearest (k) target points
- `OUTPUT` (sink, required): Distance matrix

---

### qgis:distancetonearesthublinetohub

**Display Name:** Distance to nearest hub (line to hub)

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Source points layer
- `HUBS` (source, required): Destination hubs layer
- `FIELD` (field, required): Hub layer name attribute
- `UNIT` (enum, required): Measurement unit
- `OUTPUT` (sink, required): Hub distance

---

### qgis:distancetonearesthubpoints

**Display Name:** Distance to nearest hub (points)

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Source points layer
- `HUBS` (source, required): Destination hubs layer
- `FIELD` (field, required): Hub layer name attribute
- `UNIT` (enum, required): Measurement unit
- `OUTPUT` (sink, required): Hub distance

---

### qgis:eliminateselectedpolygons

**Display Name:** Eliminate selected polygons

**Group:** Vector geometry

**Parameters:**

- `INPUT` (vector, required): Input layer
- `MODE` (enum, required): Merge selection with the neighbouring polygon with the
- `OUTPUT` (sink, required): Eliminated

---

### qgis:executesql

**Display Name:** Execute SQL

**Group:** Vector general

**Parameters:**

- `INPUT_DATASOURCES` (multilayer, optional): Input data sources (called input1, .., inputN in the query)
- `INPUT_QUERY` (execute_sql, required): SQL query
- `INPUT_UID_FIELD` (string, optional): Unique identifier field
- `INPUT_GEOMETRY_FIELD` (string, optional): Geometry field
- `INPUT_GEOMETRY_TYPE` (enum, required, default: `0`): Geometry type
- `INPUT_GEOMETRY_CRS` (crs, optional): CRS
- `OUTPUT` (sink, required): SQL Output

---

### qgis:exportaddgeometrycolumns

**Display Name:** Add geometry attributes

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `CALC_METHOD` (enum, required, default: `0`): Calculate using
- `OUTPUT` (sink, required): Added geom info

---

### qgis:findprojection

**Display Name:** Find projection

**Group:** Vector general

**Parameters:**

- `INPUT` (source, required): Input layer
- `TARGET_AREA` (extent, required): Target area for layer
- `TARGET_AREA_CRS` (crs, optional): Target area CRS
- `OUTPUT` (sink, required): CRS candidates

---

### qgis:generatepointspixelcentroidsalongline

**Display Name:** Generate points (pixel centroids) along line

**Group:** Vector creation

**Parameters:**

- `INPUT_RASTER` (raster, required): Raster layer
- `INPUT_VECTOR` (source, required): Vector layer
- `OUTPUT` (sink, required): Points along lines

---

### qgis:heatmapkerneldensityestimation

**Display Name:** Heatmap (Kernel Density Estimation)

**Group:** Interpolation

**Parameters:**

- `INPUT` (source, required): Point layer
- `RADIUS` (distance, required, default: `100.0`): Radius
- `RADIUS_FIELD` (field, optional): Radius from field
- `PIXEL_SIZE` (number, required, default: `0.1`): Output raster size
- `WEIGHT_FIELD` (field, optional): Weight from field
- `KERNEL` (enum, required, default: `0`): Kernel shape
- `DECAY` (number, optional, default: `0.0`): Decay ratio (Triangular kernels only)
- `OUTPUT_VALUE` (enum, required, default: `0`): Output value scaling
- `OUTPUT` (rasterDestination, required): Heatmap

---

### qgis:hypsometriccurves

**Display Name:** Hypsometric curves

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT_DEM` (raster, required): DEM to analyze
- `BOUNDARY_LAYER` (source, required): Boundary layer
- `STEP` (number, required, default: `100.0`): Step
- `USE_PERCENTAGE` (boolean, required, default: `False`): Use % of area instead of absolute value
- `OUTPUT_DIRECTORY` (folderDestination, required): Hypsometric curves

---

### qgis:idwinterpolation

**Display Name:** IDW interpolation

**Group:** Interpolation

**Parameters:**

- `INTERPOLATION_DATA` (idw_interpolation_data, required): Input layer(s)
- `DISTANCE_COEFFICIENT` (number, required, default: `2.0`): Distance coefficient P
- `EXTENT` (extent, required): Extent
- `PIXEL_SIZE` (number, required, default: `0.1`): Output raster size
- `COLUMNS` (number, optional): Number of columns
- `ROWS` (number, optional): Number of rows
- `OUTPUT` (rasterDestination, required): Interpolated

---

### qgis:importintospatialite

**Display Name:** Export to SpatiaLite

**Description:** Exports a vector layer to a SpatiaLite database

**Group:** Database

**Parameters:**

- `INPUT` (source, required): Layer to import
- `DATABASE` (vector, required): File database
- `TABLENAME` (string, optional): Table to import to (leave blank to use layer name)
- `PRIMARY_KEY` (field, optional): Primary key field
- `GEOMETRY_COLUMN` (string, required, default: `geom`): Geometry column
- `ENCODING` (string, optional, default: `UTF-8`): Encoding
- `OVERWRITE` (boolean, required, default: `True`): Overwrite
- `CREATEINDEX` (boolean, required, default: `True`): Create spatial index
- `LOWERCASE_NAMES` (boolean, required, default: `True`): Convert field names to lowercase
- `DROP_STRING_LENGTH` (boolean, required, default: `False`): Drop length constraints on character fields
- `FORCE_SINGLEPART` (boolean, required, default: `False`): Create single-part geometries instead of multi-part

---

### qgis:knearestconcavehull

**Display Name:** Concave hull (k-nearest neighbor)

**Description:** Creates a concave hull using the k-nearest neighbor algorithm.

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `KNEIGHBORS` (number, required, default: `3`): Number of neighboring points to consider (a lower number is more concave, a higher number is smoother)
- `FIELD` (field, optional): Field (set if creating concave hulls by class)
- `OUTPUT` (sink, required): Concave hull

---

### qgis:linestopolygons

**Display Name:** Lines to polygons

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `OUTPUT` (sink, required): Polygons

---

### qgis:listuniquevalues

**Display Name:** List unique values

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELDS` (field, required): Target field(s)
- `OUTPUT` (sink, optional): Unique values
- `OUTPUT_HTML_FILE` (fileDestination, optional): HTML report

---

### qgis:meanandstandarddeviationplot

**Display Name:** Mean and standard deviation plot

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input table
- `NAME_FIELD` (field, required): Category name field
- `VALUE_FIELD` (field, required): Value field
- `OUTPUT` (fileDestination, required): Plot

---

### qgis:minimumboundinggeometry

**Display Name:** Minimum bounding geometry

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, optional): Field (optional, set if features should be grouped by class)
- `TYPE` (enum, required): Geometry type
- `OUTPUT` (sink, required): Bounding geometry

---

### qgis:pointsdisplacement

**Display Name:** Points displacement

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `PROXIMITY` (distance, required, default: `1.0`): Minimum distance to other points
- `DISTANCE` (distance, required, default: `1.0`): Displacement distance
- `HORIZONTAL` (boolean, required): Horizontal distribution for two point case
- `OUTPUT` (sink, required): Displaced

---

### qgis:polarplot

**Display Name:** Polar plot

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input layer
- `NAME_FIELD` (field, required): Category name field
- `VALUE_FIELD` (field, required): Value field
- `OUTPUT` (fileDestination, required): Polar plot

---

### qgis:postgisexecuteandloadsql

**Display Name:** PostgreSQL execute and load SQL

**Description:** Executes a SQL command on a PostgreSQL database and loads the result as a table

**Group:** Database

**Parameters:**

- `DATABASE` (providerconnection, required): Database (connection name)
- `SQL` (string, required): SQL query
- `ID_FIELD` (string, required, default: `id`): Unique ID field name
- `GEOMETRY_FIELD` (string, optional, default: `geom`): Geometry field name

---

### qgis:randomextractwithinsubsets

**Display Name:** Random extract within subsets

**Group:** Vector selection

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): ID field
- `METHOD` (enum, required, default: `0`): Method
- `NUMBER` (number, required, default: `10`): Number/percentage of selected features
- `OUTPUT` (sink, required): Extracted (random stratified)

---

### qgis:randompointsalongline

**Display Name:** Random points along line

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `POINTS_NUMBER` (number, required, default: `1`): Number of points
- `MIN_DISTANCE` (distance, required, default: `0`): Minimum distance between points
- `OUTPUT` (sink, required): Random points

---

### qgis:randompointsinlayerbounds

**Display Name:** Random points in layer bounds

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `POINTS_NUMBER` (number, required, default: `1`): Number of points
- `MIN_DISTANCE` (distance, required, default: `0`): Minimum distance between points
- `OUTPUT` (sink, required): Random points

---

### qgis:randompointsinsidepolygons

**Display Name:** Random points inside polygons

**Group:** Vector creation

**Parameters:**

- `INPUT` (source, required): Input layer
- `STRATEGY` (enum, required, default: `0`): Sampling strategy
- `VALUE` (number, required, default: `1`): Point count or density
- `EXPRESSION` (expression, optional): Expression
- `MIN_DISTANCE` (distance, optional): Minimum distance between points
- `OUTPUT` (sink, required): Random points

---

### qgis:randomselection

**Display Name:** Random selection

**Group:** Vector selection

**Parameters:**

- `INPUT` (vector, required): Input layer
- `METHOD` (enum, required, default: `0`): Method
- `NUMBER` (number, required, default: `10`): Number/percentage of selected features

---

### qgis:randomselectionwithinsubsets

**Display Name:** Random selection within subsets

**Group:** Vector selection

**Parameters:**

- `INPUT` (vector, required): Input layer
- `FIELD` (field, required): ID field
- `METHOD` (enum, required, default: `0`): Method
- `NUMBER` (number, required, default: `10`): Number/percentage of selected features

---

### qgis:rastercalculator

**Display Name:** Raster calculator

**Group:** Raster analysis

**Parameters:**

- `EXPRESSION` (raster_calc_expression, required): Expression
- `LAYERS` (multilayer, optional): Reference layer(s) (used for automated extent, cellsize, and CRS)
- `CELLSIZE` (number, optional, default: `0.0`): Cell size (use 0 or empty to set it automatically)
- `EXTENT` (extent, optional): Output extent
- `CRS` (crs, optional): Output CRS
- `OUTPUT` (rasterDestination, required): Output

---

### qgis:rasterlayerhistogram

**Display Name:** Raster layer histogram

**Group:** Plots

**Parameters:**

- `INPUT` (raster, required): Input layer
- `BAND` (band, required, default: `1`): Band number
- `BINS` (number, required, default: `10`): number of bins
- `OUTPUT` (fileDestination, required): Histogram

---

### qgis:rectanglesovalsdiamondsvariable

**Display Name:** Rectangles, ovals, diamonds (variable)

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `SHAPE` (enum, required): Buffer shape
- `WIDTH` (field, required): Width field
- `HEIGHT` (field, required): Height field
- `ROTATION` (field, optional): Rotation field
- `SEGMENTS` (number, required, default: `36`): Number of segments
- `OUTPUT` (sink, required): Output

---

### qgis:regularpoints

**Display Name:** Regular points

**Group:** Vector creation

**Parameters:**

- `EXTENT` (extent, required): Input extent
- `SPACING` (distance, required, default: `100`): Point spacing/count
- `INSET` (distance, required, default: `0.0`): Initial inset from corner (LH side)
- `RANDOMIZE` (boolean, required, default: `False`): Apply random offset to point spacing
- `IS_SPACING` (boolean, required, default: `True`): Use point spacing
- `CRS` (crs, required, default: `ProjectCrs`): Output layer CRS
- `OUTPUT` (sink, required): Regular points

---

### qgis:relief

**Display Name:** Relief

**Group:** Raster terrain analysis

**Parameters:**

- `INPUT` (raster, required): Elevation layer
- `Z_FACTOR` (number, required, default: `1.0`): Z factor
- `AUTO_COLORS` (boolean, required, default: `False`): Generate relief classes automatically
- `COLORS` (relief_colors, optional): Relief colors
- `OUTPUT` (rasterDestination, required): Relief
- `FREQUENCY_DISTRIBUTION` (fileDestination, optional): Frequency distribution

---

### qgis:scatter3dplot

**Display Name:** Vector layer scatterplot 3D

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input layer
- `XFIELD` (field, required): X attribute
- `YFIELD` (field, required): Y attribute
- `ZFIELD` (field, required): Z attribute
- `OUTPUT` (fileDestination, required): Histogram

---

### qgis:selectbyattribute

**Display Name:** Select by attribute

**Group:** Vector selection

**Parameters:**

- `INPUT` (vector, required): Input layer
- `FIELD` (field, required): Selection attribute
- `OPERATOR` (enum, required, default: `0`): Operator
- `VALUE` (string, optional): Value
- `METHOD` (enum, required, default: `0`): Modify current selection by

---

### qgis:selectbyexpression

**Display Name:** Select by expression

**Group:** Vector selection

**Parameters:**

- `INPUT` (vector, required): Input layer
- `EXPRESSION` (expression, required): Expression
- `METHOD` (enum, required, default: `0`): Modify current selection by

---

### qgis:setstyleforrasterlayer

**Display Name:** Set style for raster layer

**Group:** Raster tools

**Parameters:**

- `INPUT` (raster, required): Raster layer
- `STYLE` (file, required): Style file

---

### qgis:setstyleforvectorlayer

**Display Name:** Set style for vector layer

**Group:** Vector general

**Parameters:**

- `INPUT` (vector, required): Vector layer
- `STYLE` (file, required): Style file

---

### qgis:statisticsbycategories

**Display Name:** Statistics by categories

**Group:** Vector analysis

**Parameters:**

- `INPUT` (source, required): Input vector layer
- `VALUES_FIELD_NAME` (field, optional): Field to calculate statistics on (if empty, only count is calculated)
- `CATEGORIES_FIELD_NAME` (field, required): Field(s) with categories
- `OUTPUT` (sink, required): Statistics by category

---

### qgis:texttofloat

**Display Name:** Text to float

**Group:** Vector table

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Text attribute to convert to float
- `OUTPUT` (sink, required): Float from text

---

### qgis:tininterpolation

**Display Name:** TIN interpolation

**Group:** Interpolation

**Parameters:**

- `INTERPOLATION_DATA` (idw_interpolation_data, required): Input layer(s)
- `METHOD` (enum, required, default: `0`): Interpolation method
- `EXTENT` (extent, required): Extent
- `PIXEL_SIZE` (number, required, default: `0.1`): Output raster size
- `COLUMNS` (number, optional): Number of columns
- `ROWS` (number, optional): Number of rows
- `OUTPUT` (rasterDestination, required): Interpolated
- `TRIANGULATION` (sink, optional): Triangulation

---

### qgis:topologicalcoloring

**Display Name:** Topological coloring

**Group:** Cartography

**Parameters:**

- `INPUT` (source, required): Input layer
- `MIN_COLORS` (number, required, default: `4`): Minimum number of colors
- `MIN_DISTANCE` (distance, required, default: `0.0`): Minimum distance between features
- `BALANCE` (enum, required, default: `0`): Balance color assignment
- `OUTPUT` (sink, required): Colored

---

### qgis:variabledistancebuffer

**Display Name:** Variable distance buffer

**Group:** Vector geometry

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Distance field
- `SEGMENTS` (number, required, default: `5`): Segments
- `DISSOLVE` (boolean, required, default: `False`): Dissolve result
- `END_CAP_STYLE` (enum, required, default: `0`): End cap style
- `JOIN_STYLE` (enum, required, default: `0`): Join style
- `MITER_LIMIT` (number, required, default: `2`): Miter limit
- `OUTPUT` (sink, required): Buffer

---

### qgis:vectorlayerhistogram

**Display Name:** Vector layer histogram

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input layer
- `FIELD` (field, required): Attribute
- `BINS` (number, required, default: `10`): number of bins
- `OUTPUT` (fileDestination, required): Histogram

---

### qgis:vectorlayerscatterplot

**Display Name:** Vector layer scatterplot

**Group:** Plots

**Parameters:**

- `INPUT` (source, required): Input layer
- `XFIELD` (field, required): X attribute
- `YFIELD` (field, required): Y attribute
- `OUTPUT` (fileDestination, required): Scatterplot

---

