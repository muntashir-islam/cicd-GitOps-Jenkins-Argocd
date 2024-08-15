
FROM openjdk:8-jre-alpine

COPY build/libs/spring-boot-0.0.1-SNAPSHOT.jar /springboot.jar
EXPOSE 8080
CMD ["/usr/bin/java", "-jar", "-Dspring.profiles.active=default", "springboot.jar"]