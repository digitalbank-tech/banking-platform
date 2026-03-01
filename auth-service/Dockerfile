# Stage 1 - Build
FROM gradle:8.5-jdk21 AS builder
WORKDIR /app
COPY . .
RUN gradle clean build -x test

FROM eclipse-temurin:21-jdk-jammy
WORKDIR /app
COPY build/libs/auth-service-0.0.1.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar","app.jar"]