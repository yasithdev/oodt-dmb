FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

WORKDIR /
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && rm ${SRC_FILE}
WORKDIR /filemgr/bin
EXPOSE 9000

ENTRYPOINT ["java",
            "-Djava.ext.dirs='/filemgr/lib'",
            "-Djava.util.logging.config.file='/filemgr/etc/logging.properties'",
            "-Dorg.apache.oodt.cas.filemgr.properties=/filemgr/etc/filemgr.properties'",
            "-Djava.io.tmpdir='/tmp'",
            "org.apache.oodt.cas.filemgr.system.XmlRpcFileManager",
            "--portNum", "9000"]
