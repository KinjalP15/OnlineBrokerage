FROM gradle:4.7.0-jdk8-alpine AS build
COPY --chown=gradle:gradle . /home/gradle/src
WORKDIR /home/gradle/src
RUN gradle build --no-daemon

FROM openjdk
COPY build/libs/OnlineBrokerageSystem-0.0.1-SNAPSHOT.jar /app
WORKDIR /app
EXPOSE 8080
CMD ["java", "-jar", "OnlineBrokerageSystem-0.0.1-SNAPSHOT.jar"]
