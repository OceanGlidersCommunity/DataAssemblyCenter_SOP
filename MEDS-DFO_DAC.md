# MEDS / DFO DAC

## Glider fleets
The Department of Fisheries and Oceans Canada (DFO) has seven Sea Explorer gliders from Alseamar and one Slocum glider in partnershippartner with the University of Victoria. 
The gliders are managed at Bedford Institute of Oceanography in Dartmouth, Nova Scotia, and the Institute of Ocean Sciences in Sidney, British Columbia. 
And, the Marine Environmental Data Section (MEDS) in Ottawa, Ontario, manages glider data.

## Data Flow
Before launching a glider, it should have a WMO number. 
Once the glider is deployed, the deployment operator will send the metadata related to the mission:
- ship name, 
- glider name, 
- mission number, 
- deployment date and location,  
- principal investigator, 
- deployment operator, 
- sensor information to MEDS.  
-
MEDS will record the metadata into the system for data processing. MEDS will also declare the information at https://www.ocean-ops.org/board?t=oceangliders.
Besides sending metadata to MEDS, the deployment operator also makes raw glider data available via FTP site or HTTP so that the system can automatically access the raw data. 
MEDS used SOCIB software as the primary data processing to generate L0, L1 and L2 NetCDF files. Then, the L1 NetCDF file is converted to EGO NetCDF format using an in-house Java program that maps SOCIB variables to equivalent EGO variables. 
The EGO NetCDF file is split into mono NetCDF files. The mono NetCDF files are transformed into TESAC format for Global Telecommunication System (GTS) dissemination. 
The EGO and mono profile NetCDF files are made available automatically to the MEDS FTP site, ftp://ftp.isdm.gc.ca/pub/glider/, and manually to ftp://ftp.ifremer.fr/ifremer/glider/v2/
