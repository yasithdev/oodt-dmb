FROM tomcat:8.0-slim
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Environment Variables
#ENV SOLR_HOME=.

# Extract Source
ARG SRC_FILE
COPY target/${SRC_FILE} ${CATALINA_HOME}/webapps