[[Category:Attribute Conventions Dataset Discovery]]
[[Category:ACDD]]
[[Category: Documentation Cluster]]

# Context
## Document
This is the Attribute Convention for Data Discovery (ACDD).

## Version and Status
This version is designated as Version 1.3; it is the latest released version.

The page [[Attribute Convention for Data Discovery]]  always points to the current released version of the Convention. The version number at the top of the resulting page will show the current version.

See the [http://wiki.esipfed.org/index.php/Category:Attribute_Conventions_Dataset_Discovery ACDD category page] for information on the history and maintenance of this convention.

### Development
For development versions of the ACDD, please see the page [[Attribute Convention for Data Discovery Working]].

Questions about this specification may be addressed to (esip-documentation(at)lists.esipfed.org)([https://lists.esipfed.org/mailman/listinfo/esip-discovery subscribe]). 
Please also have a look at the [https://lists.esipfed.org/pipermail/esip-documentation/ email archive].

# Overview
This document describes attributes recommended for describing a netCDF dataset to discovery systems such as Digital Libraries. THREDDS and other tools can use these attributes to extract metadata from datasets, and exporting to Dublin Core, DIF, ADN, FGDC, ISO 19115 and other metadata formats. This will help systems and users locate and use data efficiently.

## Alignment with netCDF and CF Conventions
The NetCDF User Guide [http://www.unidata.ucar.edu/software/netcdf/docs/netcdf.html (NUG)] provides basic recommendations for creating netCDF files; the netCDF Climate and Forecast Metadata Conventions [http://cfconventions.org/ (CF)]  provides more specific guidance. The ACDD builds upon and is compatible with these conventions; it may refine the definition of some terms in those conventions, but does not preclude the use of any attributes defined by the NUG or CF. 

The NUG does not require any global attributes, though it recommends and defines three, title, history, and Conventions. CF specifies more: institution, source, references, comment, and featureType. ACDD 1.3 adopts all CF 1.6 global attributes. In a change from ACDD 1.1, we adopt the NUG recommendation to supply all conventions in the single Conventions attribute.

## Attribute Crosswalks
Many of these attributes correspond to general discovery metadata content, so similar terms exist in many metadata standards. This [[Attribute_Convention_for_Data_Discovery_(ACDD)_Mappings]] page includes a crosswalk to THREDDS, OGC CSW, ISO 19115-2 and Rubric Categories.

## Additional Metadata: metadata_link attribute
Documents using other metadata specifications (e.g., ISO 19115) can provide additional information about the dataset. If additional metadata exists, you can make users aware of it by adding a global attribute named "metadata_link" to the netCDF file. The value of this attribute is a URL that gives the location of the more complete metadata.

## Definitions: Data and Metadata
In several ACDD attribute names or definitions, the terms 'data' and 'metadata' are used. In the context of netCDF files, these refer specifically to the values within the file, and the attributes of the file, respectively.

## Maintenance of Metadata
ACDD attributes characterize the data they are associated with. Any processing that alters these characteristics is responsible for updating the relevant attributes.

NetCDF file creators and software developers should ensure that the attributes of output data accurately represent that data, and specifically should not "pass through" any source  attribute in unaltered form, unless it is known to remain accurate. NetCDF data users should  verify critical attribute values, to be confident the source metadata is appropriate.

The ACDD geospatiotemporal attributes present a special case, as this information is already fully defined by the CF coordinate variables. These attributes are recommended, despite being redundant, because they greatly simplify data discovery and access.

The risk of inconsistency between these attributes and the actual data is highest after aggregation or subsetting; checking them against the data can serve as a useful test of the metadata's validity.

## Attribute Content Guidance
### Date and Time: ISO 8601 Recommended Formats
The ACDD specifies [http://en.wikipedia.org/wiki/ISO_8601 ISO 8601:2004] date and time formats for its temporal attributes. ACDD strongly encourages the use of the 'extended' format date-time, in the form 
 <tt>YYYY-MM-DDThh:mm:ss<zone></tt>
(although ss, mm, and hh can be omitted, and <zone> can be Z, ±hh:mm, or ±hh). Per the standard, the shortened or basic format, which omits the - and : separators, "should be avoided in plain text."

For duration attributes, again the extended form is strongly encouraged for readability:
 <tt>P[YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]</tt>

If for some reason the strongly encouraged formats can not be used, other ISO 8601-compatible formats are acceptable, but may not be handled by some processing software.

### Comma-Separated Lists
Several attributes explicitly allow the entry of multiple entities as comma-separated values.  Any entities within such lists which contain a comma must be enclosed in straight double quotation marks ("), which will not be considered part of the entity.

Spaces (ASCII character 32) between the entities are recommended for readability, but not required.  Example: 'John Doe, Jane Lee, "L J Smith, Jr." '

The same protocol may be used within free-text attributes, but is only recommended in cases where the attribute is being populated with structured data (rather than unconstrained text).

### Free Text Formatting: Structured Text Considerations
In some attributes, it may be desirable to use structured text to support computer parsing of human-readable content. Because netCDF files are often translated between binary and text-based encodings like ncML (e.g., by the netCDF command line tools ''nco''), such structures should tolerate changes in white space, including end-of-line characters, that may occur during translation.

# Global Attributes

## Highly Recommended
<table width="95%" border="1" cellpadding="2" cellspacing="2">
<tr>
<th valign="top" width="200px">Attribute</th>
<th valign="top">Description</th>
</tr>
<tr>
<td valign="top" id="title">title</td>
<td valign="top">A short phrase or sentence describing the dataset. In many discovery systems, the title will be displayed in the results list from a search, and therefore should be human readable and reasonable to display in a list of such names. This attribute is also recommended by the  [http://www.unidata.ucar.edu/software/netcdf/docs/netcdf.html#Attribute-Conventions NetCDF Users Guide] and the [http://cfconventions.org/ CF conventions]. </td>
</tr>
<tr>
<td valign="top" id="summary">summary</td>
<td valign="top">A paragraph describing the dataset, analogous to an abstract for a paper.</td>
</tr>
<tr>
<td valign="top" id="keywords">keywords</td>
<td valign="top">A comma-separated list of key words and/or phrases. Keywords may be common words or phrases, terms from a controlled vocabulary ([http://gcmd.gsfc.nasa.gov/learn/keywords.html GCMD] is often used), or URIs for terms from a controlled vocabulary (see also "keywords_vocabulary" attribute).</td>
</tr>
<tr>
<td valign="top" id="Conventions">Conventions</td>
<td valign="top">A comma-separated list of the conventions that are followed by the dataset. For files that follow this version of ACDD, include the string 'ACDD-1.3'. (This attribute is described in the  [http://www.unidata.ucar.edu/software/netcdf/docs/netcdf.html#Conventions NetCDF Users Guide].)</td>
</tr>
</table>

## Recommended 
<table width="95%" border="1" cellpadding="2" cellspacing="2">
<tr>
<th valign="top" width="200px">Attribute</th>
<th valign="top">Description</th>
</tr>
<tr>
<td valign="top" id="id">id</td>
<td valign="top">An identifier for the data set, provided by and unique within its naming authority. The combination of the "naming authority" and the "id" should be globally unique, but the id can be globally unique by itself also. IDs can be URLs, URNs, DOIs, meaningful text strings, a local key, or any other unique string of characters. The id should not include white space characters. </td>
</tr>
<tr>
<td valign="top" id="naming_authority">naming_authority</td>
<td valign="top"> The organization that provides the initial id (see above) for the dataset. The naming authority should be uniquely specified by this attribute. We recommend using reverse-DNS naming for the naming authority; URIs are also acceptable. Example: 'edu.ucar.unidata'.</td>
</tr>
<tr>
<td valign="top" id="history">history</td>
<td valign="top">Provides an audit trail for modifications to the original data. This attribute is also in the [http://www.unidata.ucar.edu/software/netcdf/docs/netcdf.html#Attribute-Conventions NetCDF Users Guide]: 'This is a character array with a line for each invocation of a program that has modified the dataset. Well-behaved generic netCDF applications should append a line containing: date, time of day, user name, program name and command arguments.' To include a more complete description you can append a reference to an ISO Lineage entity; see [https://geo-ide.noaa.gov/wiki/index.php?title=ISO_Lineage NOAA EDM ISO Lineage guidance]. </td>
</tr>
<tr>
<td valign="top" id="source">source</td>
<td valign="top">The method of production of the original data. If it was model-generated, source should name the model and its version. If it is observational, source should characterize it. This attribute is defined in the CF Conventions. Examples: 'temperature from CTD #1234'; 'world model v.0.1'. 
</tr>
<tr>
<td valign="top" id="processing_level">processing_level</td>
<td valign="top">A textual description of the processing (or quality control) level of the data.</td>
</tr>
<tr>
<td valign="top" id="comment">comment</td>
<td valign="top"> Miscellaneous information about the data, not captured elsewhere. This attribute is defined in the [http://cfconventions.org/ CF Conventions].</td>
</tr>
<tr>
<td valign="top" id="acknowledgement">acknowledgement</td>
<td valign="top">A place to acknowledge various types of support for the project that produced this data. </td>
</tr>
<tr>
<td valign="top" id="license">license</td>
<td valign="top">Provide the URL to a standard or specific license, enter "Freely Distributed" or "None", or describe any restrictions to data access and distribution in free text.</td>
</tr>
<tr>
<td valign="top" id="standard_name_vocabulary">standard_name_vocabulary</td>
<td valign="top"> The name and version of the controlled vocabulary from which variable standard names are taken. (Values for any standard_name attribute must come from the CF Standard Names vocabulary for the data file or product to comply with CF.) Example: 'CF Standard Name Table v27'.</td>
</tr>
<tr>
<td valign="top" id="date_created">date_created</td>
<td valign="top">The date on which this version of the data was created. (Modification of values implies a new version, hence this would be assigned the date of the most recent values modification.) Metadata changes are not considered when assigning the date_created.  The ISO 8601:2004 extended date format is recommended, as described in the Attribute Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="creator_name">creator_name</td>
<td valign="top">The name of the person (or other creator type specified by the creator_type attribute) principally responsible for creating this data.</td>
</tr>
<tr>
<td valign="top" id="creator_email">creator_email</td>
<td valign="top">The email address of the person (or other creator type specified by the creator_type attribute) principally responsible for creating this data.</td>
</tr>
<tr>
<td valign="top" id="creator_url">creator_url</td>
<td valign="top">The URL of the person (or other creator type specified by the creator_type attribute) principally responsible for creating this data.</td>
</tr>
<tr>
<td valign="top" id="institution">institution</td>
<td valign="top">The name of the institution principally responsible for originating this data. This attribute is recommended by the CF convention.</td>
</tr>
<tr>
<td valign="top" id="project">project</td>
<td valign="top">The name of the project(s) principally responsible for originating this data. Multiple projects can be separated by commas, as described under Attribute Content Guidelines. Examples: 'PATMOS-X', 'Extended Continental Shelf Project'.</td>
</tr>
<tr>
<td valign="top" id="publisher_name">publisher_name</td>
<td valign="top">The name of the person (or other entity specified by the publisher_type attribute) responsible for publishing the data file or product to users, with its current metadata and format.</td>
</tr>
<tr>
<td valign="top" id="publisher_email">publisher_email</td>
<td valign="top">The email address of the person (or other entity specified by the publisher_type attribute) responsible for publishing the data file or product to users, with its current metadata and format.</td>
</tr>
<tr>
<td valign="top" id="publisher_url">publisher_url</td>
<td valign="top">The URL of the person (or other entity specified by the publisher_type attribute) responsible for publishing the data file or product to users, with its current metadata and format.</td>
</tr>
<tr>
<td valign="top" id="geospatial_bounds">geospatial_bounds</td>
<td>Describes the data's 2D or 3D geospatial extent in OGC's Well-Known Text (WKT) Geometry format (reference the OGC Simple Feature Access (SFA) specification). The meaning and order of values for each point's coordinates depends on the coordinate reference system (CRS). The ACDD default is 2D geometry in the EPSG:4326 coordinate reference system. The default may be overridden with geospatial_bounds_crs and geospatial_bounds_vertical_crs (see those attributes). EPSG:4326 coordinate values are latitude (decimal degrees_north) and longitude (decimal degrees_east), in that order. Longitude values in the default case are limited to the [-180, 180) range. Example: 'POLYGON ((40.26 -111.29, 41.26 -111.29, 41.26 -110.29, 40.26 -110.29, 40.26 -111.29))'.</td>
</tr>
<tr>
<td valign="top" id="geospatial_bounds_crs">geospatial_bounds_crs</td>
<td>The coordinate reference system (CRS) of the point coordinates in the geospatial_bounds attribute. This CRS may be 2-dimensional or 3-dimensional, but together with geospatial_bounds_vertical_crs, if that attribute is supplied, must match the dimensionality, order, and meaning of point coordinate values in the geospatial_bounds attribute. If geospatial_bounds_vertical_crs is also present then this attribute must only specify a 2D CRS. EPSG CRSs are strongly recommended. If this attribute is not specified, the CRS is assumed to be EPSG:4326. Examples: 'EPSG:4979' (the 3D WGS84 CRS), 'EPSG:4047'.</td>
</tr>
<tr>
<td valign="top" id="geospatial_bounds_vertical_crs">geospatial_bounds_vertical_crs</td>
<td>The vertical coordinate reference system (CRS) for the Z axis of the point coordinates in the geospatial_bounds attribute. This attribute cannot be used if the CRS in geospatial_bounds_crs is 3-dimensional; to use this attribute, geospatial_bounds_crs must exist and specify a 2D CRS. EPSG CRSs are strongly recommended. There is no default for this attribute when not specified. Examples: 'EPSG:5829' (instantaneous height above sea level), "EPSG:5831" (instantaneous depth below sea level), or 'EPSG:5703' (NAVD88 height).</td>
</tr>
<tr>
<td valign="top" id="geospatial_lat_min">geospatial_lat_min</td>
<td valign="top">Describes a simple lower latitude limit; may be part of a 2- or 3-dimensional bounding region. Geospatial_lat_min specifies the southernmost latitude covered by the dataset.</td>
</tr>
<tr>
<td valign="top" id="geospatial_lat_max">geospatial_lat_max</td>
<td valign="top">Describes a simple upper latitude limit; may be part of a 2- or 3-dimensional bounding region. Geospatial_lat_max specifies the northernmost latitude covered by the dataset.</td>
</tr>
<tr>
<td valign="top" id="geospatial_lon_min">geospatial_lon_min</td>
<td valign="top">Describes a simple longitude limit; may be part of a 2- or 3-dimensional bounding region. geospatial_lon_min specifies the westernmost longitude covered by the dataset. See also geospatial_lon_max.</td>
</tr>
<tr>
<td valign="top" id="geospatial_lon_max">geospatial_lon_max</td>
<td valign="top">Describes a simple longitude limit; may be part of a 2- or 3-dimensional bounding region. geospatial_lon_max specifies the easternmost longitude covered by the dataset. Cases where geospatial_lon_min is greater than geospatial_lon_max indicate the bounding box extends from geospatial_lon_max, through the longitude range discontinuity meridian (either the antimeridian for -180:180 values, or Prime Meridian for 0:360 values), to geospatial_lon_min; for example, geospatial_lon_min=170 and geospatial_lon_max=-175 incorporates 15 degrees of longitude (ranges 170 to 180 and -180 to -175).</td>
</tr>
<tr>
<td valign="top" id="geospatial_vertical_min">geospatial_vertical_min</td>
<td valign="top">Describes the numerically smaller vertical limit; may be part of a 2- or 3-dimensional bounding region. See geospatial_vertical_positive and geospatial_vertical_units.</td>
</tr>
<tr>
<td valign="top" id="geospatial_vertical_max">geospatial_vertical_max</td>
<td valign="top">Describes the numerically larger vertical limit; may be part of a 2- or 3-dimensional bounding region. See geospatial_vertical_positive and geospatial_vertical_units.</td>
</tr>
<tr>
<td valign="top" id="geospatial_vertical_positive">geospatial_vertical_positive</td>
<td valign="top">One of 'up' or 'down'. If up, vertical values are interpreted as 'altitude', with negative values corresponding to below the reference datum (e.g., under water). If down, vertical values are interpreted as 'depth', positive values correspond to below the reference datum. Note that if geospatial_vertical_positive is down ('depth' orientation), the geospatial_vertical_min attribute specifies the data's vertical location furthest from the earth's center, and the geospatial_vertical_max attribute specifies the location closest to the earth's center.</td>
</tr>
<tr>
<td valign="top" id="time_coverage_start">time_coverage_start</td>
<td valign="top">Describes the time of the first data point in the data set. Use the ISO 8601:2004 date format, preferably the extended format as recommended in the Attribute Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="time_coverage_end">time_coverage_end</td>
<td valign="top">Describes the time of the last data point in the data set. Use ISO 8601:2004 date format, preferably the extended format as recommended in the Attribute Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="time_coverage_duration">time_coverage_duration</td>
<td valign="top">Describes the duration of the data set. Use ISO 8601:2004 duration format, preferably the extended format as recommended in the Attribute Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="time_coverage_resolution">time_coverage_resolution</td>
<td valign="top">Describes the targeted time period between each value in the data set. Use ISO 8601:2004 duration format, preferably the extended format as recommended in the Attribute Content Guidance section.</td>
</tr>
</table>

## Suggested
<table width="95%" border="1" cellpadding="2" cellspacing="2">
<tr>
<th valign="top" width="200px">Attribute</th>
<th valign="top">Description</th>
</tr>
<tr>
<td valign="top" id="creator_type">creator_type</td>
<td valign="top">Specifies type of creator with one of the following: 'person', 'group', 'institution', or 'position'. If this attribute is not specified, the creator is assumed to be a person.</td>
</tr>
<tr>
<td valign="top" id="creator_institution">creator_institution</td>
<td valign="top">The institution of the creator; should uniquely identify the creator's institution. This attribute's value should be specified even if it matches the value of publisher_institution, or if creator_type is institution.</td>
</tr>
<tr>
<td valign="top" id="publisher_type">publisher_type</td>
<td valign="top">Specifies type of publisher with one of the following: 'person', 'group', 'institution', or 'position'. If this attribute is not specified, the publisher is assumed to be a person.</td>
</tr>
<tr>
<td valign="top" id="publisher_institution">publisher_institution</td>
<td valign="top">The institution that presented the data file or equivalent product to users; should uniquely identify the institution. If publisher_type is institution, this should have the same value as publisher_name.</td>
</tr>
<tr>
<td valign="top" id="program">program</td>
<td valign="top">The overarching program(s) of which the dataset is a part. A program consists of a set (or portfolio) of related and possibly interdependent projects that meet an overarching objective. Examples: 'GHRSST', 'NOAA CDR', 'NASA EOS', 'JPSS', 'GOES-R'.
</td>
</tr>
<tr>
<td valign="top" id="contributor_name">contributor_name</td>
<td valign="top">The name of any individuals, projects, or institutions that contributed to the creation of this data. May be presented as free text, or in a structured format compatible with conversion to ncML (e.g., insensitive to changes in whitespace, including end-of-line characters).</td>
</tr>
<tr>
<td valign="top" id="contributor_role">contributor_role</td>
<td valign="top">The role of any individuals, projects, or institutions that contributed to the creation of this data. May be presented as free text, or in a structured format compatible with conversion to ncML (e.g., insensitive to changes in whitespace, including end-of-line characters). Multiple roles should be presented in the same order and number as the names in contributor_names.</td>
</tr>
<tr>
<td valign="top" id="geospatial_lat_units">geospatial_lat_units</td>
<td valign="top">Units for the latitude axis described in "geospatial_lat_min" and "geospatial_lat_max" attributes. These are presumed to be "degree_north"; other options from udunits may be specified instead.</td>
</tr>
<tr>
<td valign="top" id="geospatial_lat_resolution">geospatial_lat_resolution</td>
<td valign="top">Information about the targeted spacing of points in latitude. Recommend describing resolution as a number value followed by the units. Examples: '100 meters', '0.1 degree'</td>
</tr>
<tr>
<td valign="top" id="geospatial_lon_units">geospatial_lon_units</td>
<td valign="top">Units for the longitude axis described in "geospatial_lon_min" and "geospatial_lon_max" attributes. These are presumed to be "degree_east"; other options from udunits may be specified instead.</td>
</tr>
<tr>
<td valign="top" id="geospatial_lon_resolution">geospatial_lon_resolution</td>
<td valign="top">Information about the targeted spacing of points in longitude. Recommend describing resolution as a number value followed by units.  Examples: '100 meters', '0.1 degree'</td>
</tr>
<tr>
<td valign="top" id="geospatial_vertical_units">geospatial_vertical_units</td>
<td valign="top">Units for the vertical axis described in "geospatial_vertical_min" and "geospatial_vertical_max" attributes. The default is EPSG:4979 (height above the ellipsoid, in meters); other vertical coordinate reference systems may be specified. Note that the common oceanographic practice of using pressure for a vertical coordinate, while not strictly a depth, can be specified using the unit bar. Examples: 'EPSG:5829' (instantaneous height above sea level), 'EPSG:5831' (instantaneous depth below sea level).</td>
</tr>
<tr>
<td valign="top" id="geospatial_vertical_resolution">geospatial_vertical_resolution</td>
<td valign="top">Information about the targeted vertical spacing of points. Example: '25 meters'</td>
</tr>
<tr>
<td valign="top" id="date_modified">date_modified</td>
<td valign="top">The date on which the data was last modified. Note that this applies just to the data, not the metadata. The ISO 8601:2004 extended date format is recommended, as described in the Attributes Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="date_issued">date_issued</td>
<td valign="top">The date on which this data (including all modifications) was formally issued (i.e., made available to a wider audience). Note that these apply just to the data, not the metadata. The ISO 8601:2004 extended date format is recommended, as described in the Attributes Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="date_metadata_modified">date_metadata_modified</td>
<td valign="top">The date on which the metadata was last modified. The ISO 8601:2004 extended date format is recommended, as described in the Attributes Content Guidance section.</td>
</tr>
<tr>
<td valign="top" id="product_version">product_version</td>
<td valign="top">Version identifier of the data file or product as assigned by the data creator. For example, a new algorithm or methodology could result in a new product_version.</td>
<tr>
<td valign="top" id="keywords_vocabulary">keywords_vocabulary</td>
<td valign="top">If you are using a controlled vocabulary for the words/phrases in your "keywords" attribute, this is the unique name or identifier of the vocabulary from which keywords are taken. If more than one keyword vocabulary is used, each may be presented with a prefix and a following comma, so that keywords may optionally be prefixed with the controlled vocabulary key. Example: 'GCMD:GCMD Keywords, CF:NetCDF COARDS Climate and Forecast Standard Names'.</td>
</tr>
<tr>
<td valign="top" id="platform">platform</td>
<td valign="top">Name of the platform(s) that supported the sensor data used to create this data set or product. Platforms can be of any type, including satellite, ship, station, aircraft or other. Indicate controlled vocabulary used in platform_vocabulary.</td>
</tr>
<tr>
<td valign="top" id="platform_vocabulary">platform_vocabulary</td>
<td valign="top">Controlled vocabulary for the names used in the "platform" attribute.</td>
</tr>
<tr>
<td valign="top" id="instrument">instrument</td>
<td valign="top">Name of the contributing instrument(s) or sensor(s) used to create this data set or product. Indicate controlled vocabulary used in instrument_vocabulary.</td>
</tr>
<tr>
<td valign="top" id="instrument_vocabulary">instrument_vocabulary</td>
<td valign="top">Controlled vocabulary for the names used in the "instrument" attribute.</td>
</tr>
<tr>
<td valign="top" id="cdm_data_type">cdm_data_type</td>
<td>The data type, as derived from Unidata's Common Data Model Scientific Data types and understood by THREDDS. (This is a THREDDS "dataType", and is different from the CF NetCDF attribute 'featureType', which indicates a Discrete Sampling Geometry file in CF.)</td>
</tr>
<tr>
<td valign="top" id="metadata_link">metadata_link</td>
<td valign="top">A URL that gives the location of more complete metadata. A persistent URL is recommended for this attribute.</td>
</tr>
<tr>
<td valign="top" id="references">references</td>
<td valign="top">Published or web-based references that describe the data or methods used to produce it. Recommend URIs (such as a URL or DOI) for papers or other references. This attribute is defined in the CF conventions.</td>
</tr>
</table>

# Highly Recommended Variable Attributes
<table width="95%" border="1" cellpadding="2" cellspacing="2">
            <tr>
                <th valign="top" width="200px">Attribute</th>
                <th valign="top">Description</th>
            </tr>
            <tr>
                <td valign="top" id="long_name">long_name</td>
                <td valign="top">A long descriptive name for the variable (not necessarily from a controlled vocabulary). This attribute is recommended by the NetCDF Users Guide, the COARDS convention, and the CF convention.</td>
            </tr>
            <tr>
                <td valign="top" id="standard_name">standard_name</td>
                <td>A long descriptive name for the variable taken from a controlled vocabulary of variable names. We recommend using the CF convention and the variable names from the CF standard name table. This attribute is recommended by the CF convention.</td>
            </tr>
            <tr>
                <td valign="top" id="units">units</td>
                <td valign="top">The units of the variable's data values. This attribute value should be a valid udunits string. The "units" attribute is recommended by the NetCDF Users Guide, the COARDS convention, and the CF convention.</td>
            </tr>
            <tr>
                <td valign="top" id="coverage_content_type">coverage_content_type</td>
                <td valign="top">An ISO 19115-1 code to indicate the source of the data (image, thematicClassification, physicalMeasurement, auxiliaryInformation, qualityInformation, referenceInformation, modelResult, or coordinate).</td>
            </tr>
</table>

# Deprecated Attribute
The following term and definition is still recognized, but is no longer recommended for use by ACDD.

:Metadata_Convention: removed in favor of 'Conventions'

# Index by Attribute Name
<table>
<tr>
    <td valign="top">
        <ul>
            <li>[[#acknowledgement|acknowledgement]] (Recommended)</li>
            <li>[[#cdm_data_type|cdm_data_type]] (<font color="gray">Suggested</font>)</li>
            <li>[[#comment|comment]] (Recommended)</li>
            <li>[[#contributor_name|contributor_name]] (<font color="gray">Suggested</font>)</li>
            <li>[[#contributor_role|contributor_role]] (<font color="gray">Suggested</font>)</li>
            <li>[[#Conventions|Conventions]] ('''Highly Recommended''')</li>
            <li>[[#coverage_content_type|coverage_content_type]] ('''Highly Recommended''') [Variable]</li>
            <li>[[#creator_email|creator_email]] (Recommended)</li>
            <li>[[#creator_institution|creator_institution]] (<font color="gray">Suggested</font>)</li>
            <li>[[#creator_name|creator_name]] (Recommended)</li>
            <li>[[#creator_type|creator_type]] (<font color="gray">Suggested</font>)</li>
            <li>[[#creator_url|creator_url]] (Recommended)</li>
            <li>[[#date_created|date_created]] (Recommended)</li>
            <li>[[#date_issued|date_issued]] (<font color="gray">Suggested</font>)</li>
            <li>[[#date_metadata_modified|date_metadata_modified]] (<font color="gray">Suggested</font>)</li>
            <li>[[#date_modified|date_modified]] (<font color="gray">Suggested</font>)</li>
            <li>[[#geospatial_bounds|geospatial_bounds]] (Recommended)</li>
            <li>[[#geospatial_bounds_crs|geospatial_bounds_crs]] (Recommended)</li>
            <li>[[#geospatial_bounds_vertical_crs|geospatial_bounds_vertical_crs]] (Recommended)</li>
            <li>[[#geospatial_lat_max|geospatial_lat_max]] (Recommended)</li>
            <li>[[#geospatial_lat_min|geospatial_lat_min]] (Recommended)</li>
            <li>[[#geospatial_lat_resolution|geospatial_lat_resolution]] (<font color="gray">Suggested</font>)</li>
            </ul>
    </td>
    <td valign="top">
        <ul>                
            <li>[[#geospatial_lat_units|geospatial_lat_units]] (<font color="gray">Suggested</font>)</li>
            <li>[[#geospatial_lon_max|geospatial_lon_max]] (Recommended)</li>
            <li>[[#geospatial_lon_min|geospatial_lon_min]] (Recommended)</li>
            <li>[[#geospatial_lon_resolution|geospatial_lon_resolution]] (<font color="gray">Suggested</font>)</li>
            <li>[[#geospatial_lon_units|geospatial_lon_units]] (<font color="gray">Suggested</font>)</li>
            <li>[[#geospatial_vertical_max|geospatial_vertical_max]] (Recommended)</li>
            <li>[[#geospatial_vertical_min|geospatial_vertical_min]] (Recommended)</li>
            <li>[[#geospatial_vertical_positive|geospatial_vertical_positive]] (Recommended)</li>
            <li>[[#geospatial_vertical_resolution|geospatial_vertical_resolution]] (<font color="gray">Suggested</font>)</li>
            <li>[[#geospatial_vertical_units|geospatial_vertical_units]] (<font color="gray">Suggested</font>)</li>
            <li>[[#history|history]] (Recommended)</li>
            <li>[[#id|id]] (Recommended)</li>
            <li>[[#institution|institution]] (Recommended)</li>
            <li>[[#instrument|instrument]] (<font color="gray">Suggested</font>)</li>
            <li>[[#instrument_vocabulary|instrument_vocabulary]] (<font color="gray">Suggested</font>)</li>
            <li>[[#keywords|keywords]] ('''Highly Recommended''')</li>
            <li>[[#keywords_vocabulary|keywords_vocabulary]] (<font color="gray">Suggested</font>)</li>
            <li>[[#license|license]] (Recommended)</li>
            <li>[[#long_name|long_name]] ('''Highly Recommended''') [Variable]</li>
            <li>[[#metadata_link|metadata_link]] (<font color="gray">Suggested</font>)</li>
            <li>[[#naming_authority|naming_authority]] (Recommended)</li>
            <li>[[#platform|platform]] (<font color="gray">Suggested</font>)</li>
        </ul>
    </td>
    <td valign="top">
        <ul>
            <li>[[#platform_vocabulary|platform_vocabulary]] (<font color="gray">Suggested</font>)</li>
            <li>[[#processing_level|processing_level]] (Recommended)</li>
            <li>[[#product_version|product_version]] (<font color="gray">Suggested</font>)</li>
            <li>[[#program|program]] (<font color="gray">Suggested</font>)</li>
            <li>[[#project|project]] (Recommended)</li>
            <li>[[#publisher_email|publisher_email]] (Recommended)</li>
            <li>[[#publisher_institution|publisher_institution]] (<font color="gray">Suggested</font>)</li>
            <li>[[#publisher_name|publisher_name]] (Recommended)</li>
            <li>[[#publisher_type|publisher_type]] (<font color="gray">Suggested</font>)</li>
            <li>[[#publisher_url|publisher_url]] (Recommended)</li>
            <li>[[#references|references]] (<font color="gray">Suggested</font>)</li>
            <li>[[#source|source]] (Recommended)</li>
            <li>[[#standard_name|standard_name]] ('''Highly Recommended''') [Variable]</li>
            <li>[[#standard_name_vocabulary|standard_name_vocabulary]] (Recommended)</li>
            <li>[[#summary|summary]] ('''Highly Recommended''')</li>
            <li>[[#time_coverage_duration|time_coverage_duration]] (Recommended)</li>
            <li>[[#time_coverage_end|time_coverage_end]] (Recommended)</li>
            <li>[[#time_coverage_resolution|time_coverage_resolution]] (Recommended)</li>
            <li>[[#time_coverage_start|time_coverage_start]] (Recommended)</li>
            <li>[[#title|title]] ('''Highly Recommended''')</li>
            <li>[[#units|units]] ('''Highly Recommended''') [Variable]</li>
        </ul>
    </td>
</tr>
</table>

# Conformance Test
Conformance tests are available for verson 1.1. A conformance test for this version will be linked from this page when it is available.

# Additional Materials
These materials are not normative and may not be in alignment with this version of ACDD. 

* Mappings ACDD to other metadata dialects
  *[[Attribute Convention for Data Discovery (ACDD) Mappings]]-
* Recommended Order of Precedence
  * [[Attribute Convention for Data Discovery (ACDD) Precedence]]
* Future Directions: Object Conventions for Data Discovery
  * [[Attribute Convention for Data Discovery (ACDD) Object Conventions]]
* ISO Translation Notes
  * http://wiki.esipfed.org/index.php?title=Attribute_Convention_for_Data_Discovery_(ACDD)_ISO_TranslationNotes
