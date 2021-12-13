FROM giscience/openrouteservice:latest
# FROM giscience/openrouteservice:latest
# COPY colombia-latest.osm.pbf data/osm_file.pbf
# RUN wget -p data/ -o osm_file.pbf http://download.geofabrik.de/south-america/colombia-latest.osm.pbf
RUN wget -q http://download.geofabrik.de/south-america/colombia-latest.osm.pbf -O /ors-core/data/osm_file.pbf
# RUN wget http://download.geofabrik.de/south-america/colombia-latest.osm.pbf
# RUN mv colombia-latest.osm.pbf ./data/osm_file.pbf
# copy file app.config in path /openrouteservice/src/main/resources/  to test
COPY ors-config.json /ors-conf/ors-config.json
COPY ors-config.json /ors-core/openrouteservice/src/main/resources/ors-config.json
EXPOSE 8080
EXPOSE 9001
ENV BUILD_GRAPHS=True
ENV JAVA_OPTS="-Djava.awt.headless=true -server -XX:TargetSurvivorRatio=75 -XX:SurvivorRatio=64 -XX:MaxTenuringThreshold=3 -XX:+UseG1GC -XX:+ScavengeBeforeFullGC -XX:ParallelGCThreads=4 -Xms2g -Xmx4g"
ENV CATALINA_OPTS="-Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.port=9001 -Dcom.sun.management.jmxremote.rmi.port=9001 -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false -Djava.rmi.server.hostname=localhost"
#ENV MAVEN_OPTS="-Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true -Dmaven.wagon.http.ssl.ignore.validity.dates=true"