FROM openjdk:17-jdk-alpine
VOLUME /tmp
COPY target/sms-0.0.1-SNAPSHOT.jar sms-app.jar
ENTRYPOINT ["java", "-jar", "/sms-app.jar"]
