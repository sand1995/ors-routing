From osrm/osrm-backend:latest
# COPY colombia-latest.osm.pbf data/osm_file.pbf
# RUN wget -p data/ -o osm_file.pbf http://download.geofabrik.de/south-america/colombia-latest.osm.pbf
RUN apt-get update
RUN apt-get -qq -y install wget
RUN mkdir data
RUN wget -q http://download.geofabrik.de/south-america/colombia-latest.osm.pbf -O data/osm_file.pbf
# RUN osrm/osrm-backend osrm-extract -p /opt/car.lua /data/osm_file.pbf
# RUN osrm-partition /data/osm_file.osrm
# RUN osrm-customize /data/osm_file.osrm

EXPOSE 5000