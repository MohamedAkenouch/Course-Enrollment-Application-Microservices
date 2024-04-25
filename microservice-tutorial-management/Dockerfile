FROM openjdk:11
EXPOSE 8081
ADD ./target/spring-boot-jpa-h2-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]