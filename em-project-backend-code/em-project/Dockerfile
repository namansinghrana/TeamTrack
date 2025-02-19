# Use an official OpenJDK runtime as a parent image
FROM openjdk:19-jdk AS build
WORKDIR /app
COPY pom.xml .
COPY src src

# Copy Maven wrapper
COPY mvnw .
COPY .mvn .mvn

# Resolve dependencies and package the application
RUN chmod +x ./mvnw
RUN ./mvnw clean package -DskipTests

# Make port 9090 available to the world outside this container
EXPOSE 9090

# Run the application
ENTRYPOINT ["java", "-jar", "target/em-project-0.0.1-SNAPSHOT.jar"]
