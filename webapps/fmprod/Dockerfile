FROM tomcat:8.0-slim
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Environment Variables
ENV FMPROD_HOME=/oodt
ENV FILEMGR_URL=localhost:9000

# Extract Source
ARG SRC_FILE
COPY target/${SRC_FILE} ${CATALINA_HOME}/webapps