FROM gradle:7.6-jdk11 AS build
WORKDIR /app
COPY . .
RUN gradle bootJar --no-daemon

FROM eclipse-temurin:11-jre
WORKDIR /app
COPY --from=build /app/build/libs/*.jar app.jar
EXPOSE 16060
ENTRYPOINT ["java", "-jar", "app.jar"]
