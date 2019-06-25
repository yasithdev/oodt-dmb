FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Environment Variables
ENV HOME=/oodt
ENV RESMGR_HOME=/oodt/resmgr

# Volumes
VOLUME /oodt/logs

# Extract Source
WORKDIR /oodt
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && rm ${SRC_FILE}

# Start
WORKDIR /oodt/resmgr
EXPOSE 9001
CMD java -Djava.ext.dirs="./lib" -Djava.util.logging.config.file="./etc/logging.properties" -Dorg.apache.oodt.cas.resource.properties="./etc/resource.properties" -Djava.io.tmpdir="/tmp" org.apache.oodt.cas.resource.system.XmlRpcResourceManager --portNum 9001
