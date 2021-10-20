# IOOS DAC - Standard Operational Practice

Data providers wishing to submit real-time and/or delayed mode data sets to the United States Integrated Ocean Observing System (IOOS) glider data assembly center (DAC) must first register and receive a user account.  
Registration is typically done by emailing the IOOS DAC support group at glider.dac.support@noaa.gov and provide the following information:
- Full name
- Email address
- Phone Number
- Institution

The user receives a user account and temporary password that should be changed immediately upon logging in for the first time.

Once registered, the user may submit real-time and/or delayed mode datasets using the following process:
For data sets that are to be released to the Global Telecommunication System (GTS, real-time data sets only), the data provider should request a WMO id from the DAC support team (glider.dac.support@noaa.gov). 
WMO ids are unique to a single glider deployed in one of the WMO regions and should only be used for deployment of the same glider in the region for which it is assigned.
Native telemetered glider data files are parsed to retrieve individual profiles from the time-series data set. The indexed profiles are then written to the NetCDF format according to the specification provided at https://ioos.github.io/ioosngdac/ngdac-netcdf-file-format-version-2.html which attempts to conform to CF, ACDD and IOOS Metadata Profile standards. 

The NetCDF format detailed here stores a single profile time-series that can include any number of time indexed variables with the exception of the following variables:

  a.  Calculated water currents and their associated GPS coordinates, all of which are stored as scalar variables containing a single u, v, latitude and longitude according to CF specifications.
  
  b. A trajectory variable, containing a string or character array, specifying the unique name of the dataset which can also be interpreted as the deployment name.  This string has the following format: glider-YYYYmmddTHHMM (glider name and ISO-8601 formatted deployment start date and time).
  
  c. Descriptions of the instruments contained in the glider payload are stored as empty scalar variables who attributes convey information about the instrument including instrument type, calibration date(s) and serial number.
The deployment name (1b) is registered on the IOOS Glider DAC deployment registration page located at https://gliders.ioos.us/providers/. The following information is required during registration:
- Glider name
- ISO-8601 formatted date/timestamp
- Attribution of the funding agencies.
Following deployment registration, the data provider uploads one or more profile-based NetCDF files (described in 2) via ftp to the DAC data submission server. 
These individual files are then aggregated into a TrajectoryProfile dataset via NOAA Environmental Research Division’s Data Access Program (ERDDAP), located at https://gliders.ioos.us/erddap/info and real-time data set status is monitored at https://marine.rutgers.edu/cool/data/gliders/dac/status.
The National Data Buoy Center harvests new data from all data sets for which a valid WMO id has been supplied, encodes the data to the profiling float BUFR format and releases the messages to GTS.

It is anticipated that the U.S. IOOS Glider Data Assembly will undertake the conversion of existing a future submitted data sets to the OceanGliders 1.0 NetCDF format, once it is adopted (2021 or 2022).  
While we do not anticipate a change to our existing data format to accomplish this, it is very likely that we will ask data providers to submit additional metadata to be included in the OceanGliders data sets.  We are currently reviewing and comparing the OceanGliders format to our existing format in order to identify and missing metadata.
