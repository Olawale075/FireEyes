

FROM openjdk-17-alpine 
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --from=build /target/sms-0.0.1-SNAPSHOT.jar sms.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","sms.jar"]