FROM solr:8-slim
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

# Extract Source
WORKDIR /oodt
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && cp -al solr/* /var/solr/ && rm -rf solr/ && rm ${SRC_FILE}

