FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

ARG src_file
COPY target/${src_file} /
RUN apk add tar && tar -xvf /${src_file} && rm /${src_file}

ENV FILEMGR_HOME=/filemgr
WORKDIR ${FILEMGR_HOME}

ENTRYPOINT ["./bin/filemgr", "start"]
