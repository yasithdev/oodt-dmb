FROM openjdk:8-jre-alpine
MAINTAINER Yasith Jayawardana <yasith.jayawardana@icloud.com>

WORKDIR /
ARG SRC_FILE
COPY target/${SRC_FILE} .
RUN apk add tar && tar -xvf ${SRC_FILE} && rm ${SRC_FILE}
WORKDIR /workflow/bin
EXPOSE 9002

ENTRYPOINT ["java",
            "-Djava.ext.dirs='/workflow/lib'",
            "-Djava.util.logging.config.file='/workflow/etc/logging.properties'",
            "-Dorg.apache.oodt.cas.workflow.properties=/workflow/etc/workflow.properties'",
            "-Djava.io.tmpdir='/tmp'",
            "-Dorg.apache.oodt.cas.pge.task.metkeys.legacyMode='true'",
            "-Dorg.apache.oodt.cas.pge.task.status.legacyMode='true'",
            "org.apache.oodt.cas.workflow.system.XmlRpcWorkflowManager",
            "--portNum", "9002"]
