FROM solr:8-slim
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Extract Source
WORKDIR /oodt
# Using root user, as tar extraction was giving permission denied errors
USER root
ARG SRC_FILE
ADD target/${SRC_FILE} ${SOLR_HOME}
