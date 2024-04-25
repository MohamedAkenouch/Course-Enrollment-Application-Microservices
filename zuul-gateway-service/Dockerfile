FROM openjdk:11
RUN mkdir /app
WORKDIR /app
COPY ./build/libs/zuul-gateway-service-0.0.1-SNAPSHOT.jar /app/zuul.jar
EXPOSE 8765
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app/zuul.jar", "--spring.profiles.active=docker"]
