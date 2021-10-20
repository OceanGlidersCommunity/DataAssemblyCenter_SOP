# Coriolis DAC - Standard Operational practices

## How to provide glider data to Coriolis ?  (users point of view)
To provide glider observations to Coriolis, providers have to push the data to Coriolis ftp server.·        
ftp eftp.ifremer.fr
Contact codac@ifremer.fr for user name and password.
Glider data submission directory structure : submit/XXX/XXX_YYYYMMDD/ where:
XXX: glider name
 YYYYMMDD : deployment date of the glider
Inside each deployment repository, we need raw files (m and dat files for slocum, netcdf or bpo files for seaglider and gz files for seaexplorer) and json files containing all the necessary information (global attributes, sensors information, calibration coefficient) if the provider wants us to decode data. Otherwise, we need final files if the provider/DAC generates itself the files that we must disseminate.
Data recovery (Coriolis point of view)
If we must decode data:
We check the json files format and informations
We use a matlab decoder developed by Ifremer ( https://www.seanoe.org/data/00343/45402/ ) to produce the files to disseminate (explained in the next chapter). Note that a compiled version is available. It’s not necessary to have a matlab license to run the decoder 
If we get already decoded data:
We check the format of the netcdf files received. If needed, we produce the profiles files from the EGO/OCEANGLIDERS netcdf file. 
Note that we can get/produce/disseminate data in real time on a daily basis.
Data format
We produce and disseminate two types of netcdf files.
The timeseries EGO/OCEANGLIDERS netcdf file (at the moment described here: https://archimer.ifremer.fr/doc/00239/34980/ ). It contains the full dataset of the glider deployment (one file per deployment)
·        
The netcdf profile files (one file per profile) when it’s possible.
Formats of these files are systematically checked by our format checker (available here : https://www.seanoe.org/data/00344/45538/ )
Diffusion
All decoded and recovered data are available on an ftp space ( ftp://ftp.ifremer.fr/ifremer/glider/v2/ ). We generate index files at the root of this space to facilitate the search for data
An ERDDAP is link the this space ( http://www.ifremer.fr/erddap/tabledap/OceanGlidersGDACTrajectories.html )
This ERDDAP is used for the map of the https://www.oceangliders.org/ website.
The profiles files are ingested into Coriolis database then automatically disseminate to different projects like Copernicus or Emodnet physics
It’s also possible to assign DOI to each deployment dataset (https://www.seanoe.org/data/00453/56454/ )
Summary of tools / documentations / link  used
Matlab decoder : https://www.seanoe.org/data/00343/45402/ .
The complete documentation available in the link. Some functionalities: decode data from seaglider, slocum and seaexplorer, create EGO file and profile files, apply NRT QC to data, possibility to compute some parameters with the intermediate parameters and calibration coefficients ( PSAL, BBP700, DOXY, CHLA, TURBIDITY)
Format checker : https://www.seanoe.org/data/00344/45538/ 
Format manual : https://archimer.ifremer.fr/doc/00239/34980/ 
FTP: ftp://ftp.ifremer.fr/ifremer/glider/v2/ 
ERDDAPP Glider : http://www.ifremer.fr/erddap/tabledap/OceanGlidersGDACTrajectories.html 
Improvement
By experience, we have some difficulties.
For provider: provide complete and correct jsons. The way to fill/retrieve this metadata should be facilitated. As long as we have to check and correct the jsons, the ingestion cannot be automated. 
Get coefficient calibration: Very important for example to compute, validate DOXY. We have difficulty in recovering these coefficients from providers.
Manage a common format between DACs as all DAC use their own tools. The future OceanGliders format will help a lot.
