FROM openjdk:17-jdk-slim AS build

WORKDIR /kwon

COPY ./kwon .

RUN ./gradlew build

FROM openjdk:17-jdk-slim AS production

WORKDIR /app

COPY --from=build /kwon/build/libs/*.jar app.jar

ENTRYPOINT ["java","-jar","/app.jar"]




