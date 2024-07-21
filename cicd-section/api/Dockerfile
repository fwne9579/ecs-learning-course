FROM gradle:jdk21 AS Build

WORKDIR /app
COPY . /app
RUN chmod 755 ./gradlew
RUN ./gradlew Build


FROM openjdk:21
COPY --from=build /app/build/libs/my-app-0.0.1-SNAPSHOT.jar ./my-app.jar
CMD [ "java", "-jar", "my-app.jar" ]
