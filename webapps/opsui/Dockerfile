FROM tomcat:8.0-slim
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Environment Variables
ENV FILEMGR_URL=localhost:9000
ENV RESMGR_URL=localhost:9001
ENV WORKFLOW_URL=localhost:9002

ENV WORKFLOW_HOME=.
ENV PCS_HOME=.
ENV GANGLIA_URL=.

# Extract Source
ARG SRC_FILE
ADD target/${SRC_FILE} ${CATALINA_HOME}/webapps/opsui.war
RUN mkdir ${CATALINA_HOME}/logs