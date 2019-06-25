FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Environment Variables
ENV OODT_HOME=/oodt
ENV FILEMGR_HOME=/oodt/filemgr

# Volumes
VOLUME /oodt/logs

# Extract Source
WORKDIR /oodt
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && rm ${SRC_FILE}

# Start
WORKDIR /oodt/filemgr
EXPOSE 9000
CMD java -Djava.ext.dirs="./lib" -Djava.util.logging.config.file="./etc/logging.properties" -Dorg.apache.oodt.cas.filemgr.properties="./etc/filemgr.properties" -Djava.io.tmpdir="/tmp" org.apache.oodt.cas.filemgr.system.XmlRpcFileManager --portNum 9000
