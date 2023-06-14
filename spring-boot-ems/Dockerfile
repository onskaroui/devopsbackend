#for the build stage
FROM maven:3.8.4-openjdk-11 AS build
WORKDIR /spring-boot-ems
COPY pom.xml .
COPY src ./src
RUN mvn clean install
#for the running stage
FROM openjdk:11
WORKDIR /spring-boot-ems
COPY --from=build /spring-boot-ems/target/my-spring-boot-app.jar .
CMD java -jar my-spring-boot-app.jar
