FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

WORKDIR /
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && rm ${SRC_FILE}
WORKDIR /resmgr/bin
EXPOSE 9001

ENTRYPOINT ["java",
            "-Djava.ext.dirs='/resmgr/lib'",
            "-Djava.util.logging.config.file='/resmgr/etc/logging.properties'",
            "-Dorg.apache.oodt.cas.resource.properties=/filemgr/etc/resource.properties'",
            "-Djava.io.tmpdir='/tmp'",
            "org.apache.oodt.cas.resource.system.XmlRpcResourceManager",
            "--portNum", "9001"]
