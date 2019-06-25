FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Environment Variables
ENV OODT=/oodt
ENV WORKFLOW_HOME=/oodt/workflow

# Volumes
VOLUME /oodt/logs

# Extract Source
WORKDIR /oodt
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && rm ${SRC_FILE}

# Start
WORKDIR /oodt/workflow
EXPOSE 9002
CMD java -Djava.ext.dirs="./lib" -Djava.util.logging.config.file="./etc/logging.properties" -Dorg.apache.oodt.cas.workflow.properties="./etc/workflow.properties" -Djava.io.tmpdir="/tmp" -Dorg.apache.oodt.cas.pge.task.metkeys.legacyMode="true" -Dorg.apache.oodt.cas.pge.task.status.legacyMode="true" org.apache.oodt.cas.workflow.system.XmlRpcWorkflowManager --portNum 9002
