

# FROM openjdk-17-alpine 
# COPY . .
# RUN mvn clean package -DskipTests

# FROM openjdk:17.0.1-jdk-slim
# COPY target/sms-0.0.1-SNAPSHOT.jar sms.jar
# EXPOSE 8080
# ENTRYPOINT ["java","-jar","sms.jar"]

# Build stage
FROM eclipse-temurin:17-jdk-alpine AS builder
 
WORKDIR /app
COPY . .
RUN ./mvnw package
 
# Run stage
FROM eclipse-temurin:17-jdk-alpine AS runner
 
WORKDIR /app
COPY --from=builder target/sms-0.0.1-SNAPSHOT.jar sms.jar
 
CMD ["java", "-jar", "sms.jar"]