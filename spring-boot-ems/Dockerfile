#for the build stage
FROM maven:3.8.4-openjdk-11 AS build
WORKDIR /spring-boot-ems
EXPOSE 8090
COPY pom.xml .
COPY src ./src
RUN mvn clean install
#for the running stage
FROM openjdk:11
WORKDIR /spring-boot-ems
COPY --from=build /spring-boot-ems/target/spring-boot-ems-0.0.1-SNAPSHOT.jar .
CMD java -jar spring-boot-ems-0.0.1-SNAPSHOT.jar
