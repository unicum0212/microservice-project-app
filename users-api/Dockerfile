FROM openjdk:8-alpine

EXPOSE 8083
WORKDIR /usr/src/app


COPY pom.xml mvnw ./
COPY .mvn/ ./.mvn
RUN apk add dos2unix
RUN dos2unix mvnw
RUN /bin/sh mvnw dependency:resolve

COPY . .
RUN dos2unix mvnw
RUN /bin/sh mvnw install

CMD ["java", "-jar", "./target/users-api-0.0.1-SNAPSHOT.jar"]
