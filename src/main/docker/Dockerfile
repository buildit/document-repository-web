FROM haproxy:1.8-alpine

ENV JVM_OPTIONS ""
ENV WORKDIR_PATH /
ENV LOOKUP_PATH .
ENV JAR_FILENAME app.jar

ADD $LOOKUP_PATH/$JAR_FILENAME $WORKDIR_PATH
ADD $LOOKUP_PATH/haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg

RUN apk add --update bash openjdk8-jre && rm -rf /var/cache/apk/*

EXPOSE 8080
EXPOSE 80

ENTRYPOINT ["/bin/bash", "-c", "java $JVM_OPTIONS -jar $JAR_FILENAME"]
