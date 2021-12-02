# OGI_MIPilot
Open Gov Intelligence Marine Institute Pilot

# Binder
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/IrishMarineInstitute/OGI_MIPilot/master)

# Adding a new station
1. Sort out data acquisition.
2. Update the mappings file located here (mappings/dimension_station_id.csv) with the station info. Format is id, name, description, longitude, latitude.
3. Remote log-on to the docker host (dmdock01 - 172.17.1.119).
4. Navigate to ogidashboard (***cd /ogidashboard/OGI_dashboard/mappings***).
5. Update the mappings CSV file with your new station info (***nano dimension_station_id.csv***) and save.
6. Run this script to bind those mappings (***/usr/bin/docker run --rm --name=ogipy --mount source=rdf-vol,destination=/rdf continuumio/anaconda3 /bin/bash -c "/opt/conda/bin/python /rdf/datacube_generator.py && exit"***). Don't worry, this will take a few minutes and eventually return a warning, but should be seemless.
