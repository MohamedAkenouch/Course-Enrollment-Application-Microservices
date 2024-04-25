# Course Enrollment Microservices, Spring Cloud, Spring Boot, Angular 8, MySQL, H2, Hibernate, Liquibase, NodeJS, MongoDB

The application structure is as follows.
- **microservice-user-management** - Microservice implemented using Spring boot. [More info](microservice-user-management/README.md)
- **microservice-course-management** - Microservice implemented using Spring boot. [More info](microservice-course-management/README.md)
- **microservice-tutorial-management** - Microservice implemented using Spring eureka and H2 database. [More info](eureka-discovery-service/README.md)
- **zuul-gateway-service** - Microservice implemented using Spring zuul. [More info](zuul-gateway-service/README.md)
- **client-side** - A NodeJs application implemented using Angular 8. This consumes services hosted by server side.  [More info](client-side/README.md)

You should have Docker installed in your server in order to run this project.

The application ports.
- **microservice-user-management** - port 8080
- **microservice-user-management-MongoDB** - port 27017 (Mongo database)
- **microservice-course-management** - port 8001 
- **microservice-course-management-Mysql** - port 3306 (Mysql Database)
- **microservice-tutorial-management** - port 8081 (H2 Database)
- **zuul-gateway-service** - port 8765
- **eureka-service** - port 8761
- **client-side** - port 80

### Build

#### 1) Build Spring Boot microservices
   
```
$ cd RootProject
$ cd microservice-course-management && ./gradlew bootJar && cd ..
$ cd zuul-gateway-service && ./gradlew bootJar && cd ..
$ cd microservice-tutorial-management && mvn package && cd .. (You should have Maven installed in your server)
```

#### 2) Build Microservice's docker images 

```
$ cd RootProject
$ docker build -t course-image:latest --no-cache ./microservice-course-management
$ docker build -t tutorial-micro:latest --no-cache ./microservice-tutorial-management
$ docker build -t auth-micro:latest --no-cache ./microservice-user-management
$ docker build -t gateway-micro:latest --no-cache ./zuul-gateway-service
$ docker build -t client-side:latest --no-cache ./client-side
```

### Run the application with Docker Compose
```
$ cd RootProject
$ docker-compose up
```

### Access application using following URL

```
http://localhost/home
```
### Get the status of Eureka server using following URL

```
http://localhost:8761/lastn
```