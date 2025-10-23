FROM gradle:7.6.1-jdk17 AS build2
WORKDIR /app2
COPY . .
RUN gradle bootJar

FROM openjdk:17-jdk-slim
WORKDIR /app2
COPY --from=build2 /app2/build/libs/*.jar app2.jar
ENTRYPOINT ["java", "-jar", "app2.jar"]