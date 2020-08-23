FROM openjdk:8-jdk-alpine

ADD libs/webapi-1.0.0.jar app.jar

ENV JAVA_OPS="-Xms64m -Xmx512m"

ENTRYPOINT exec java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar
