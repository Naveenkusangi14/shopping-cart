# FROM openjdk:8u151-jdk-alpine3.7

# EXPOSE 8070

# ENV APP_HOME /usr/src/app

# COPY target/shopping-cart-0.0.1-SNAPSHOT.jar $APP_HOME/app.jar

# WORKDIR $APP_HOME

# ENTRYPOINT exec java -jar app.jar

# Stage 1: Build the application
FROM openjdk:latest AS build

ENV APP_HOME /usr/app
WORKDIR $APP_HOME

COPY target/shopping-cart-0.0.1-SNAPSHOT.jar $APP_HOME/app.jar

# Stage 2: Run the application
FROM gcr.io/distroless/java

COPY --from=build /usr/app/app.jar /app.jar

CMD ["java", "-jar", "/app.jar"]

