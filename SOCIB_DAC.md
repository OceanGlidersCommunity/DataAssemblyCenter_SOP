## SOCIB DAC

The SOCIB glider data workflow describes the different steps of the glider data lifecycle from data acquisition to dissemination. The metadata catalog is key to perform the data cycle in an automatic way. 
There are three major working flows that include: 
- real time (RT), 
- recovery (DT) and,
- delayed mode/scientific corrected (DM) data, 
- well aligned with international standards and initiatives such as CMEMS. 
 
SOCIB also produces three types of data outputs: 
- data files (netcdf), 
- figures (png), 
- and trajectories (kmz). 

The processing of in-situ observations results in three levels of netcdf data files: L0, L1 and L2. 
- The L0 level contains scientific and engineering parameters as sent from the glider. 
- The L1 level files contain in-situ observations, calibrations, unit corrections and derived variables such as salinity. It also includes delayed mode corrections like the thermal lag (Garau et al., 2011).
- The L2  level files are gridded observations from the glider profiles. 

SOCIB data files are available through the SOCIB Thredds Data Server. In addition, the SOCIB Data API facilitates discoverability and accessibility to any user (including other international aggregators) to gather SOCIB data in an automatic way. 
SOCIB Netcdf files are produced following international conventions and standards to guarantee interoperability. Additionally, EGO format netcdf files are produced and pushed to the Coriolis ftp so it is aggregated into Coriolis and, in turn, into the Copernicus Marine Service, EMODnet and GTS. 
In addition, SOCIB, in order to improve the FAIRness of its data assets, is also minting DOIs to data products related to its sustained endurance lines and/or specific scientific projects. The latter implies that some glider related data products are minted with a DOI and are accessible through the SOCIB Data Catalog.

Two main tools enable SOCIB glider workflow : 
- The SOCIB Glider Toolbox (Troupin et al 2016) enables glider data processing for the real-time and recovery data, generating both netcdfs and figures. It is being used by leading institutions to process their glider data, such as NOAA fisheries (Reiss et al 2021) and DFO-MPO (Cyr - mission report, 2018). 
- The SOCIB salinity correction toolbox (Allen et al 2020) is also used to perform delay mode calibrations on glider salinity data against ship-based observations from seasonal cruises over the study area. More information on the data flow and glider data management can be found in the SOCIB workflow and strategy description.
