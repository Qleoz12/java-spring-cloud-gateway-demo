FROM openjdk:17-jdk-slim
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} api-user.jar
ENTRYPOINT ["java", "-jar", "api-user.jar"]