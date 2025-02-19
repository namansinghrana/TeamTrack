# Use an official OpenJDK runtime as a parent image
FROM openjdk:11-jre-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Resolve dependencies and package the application
RUN ./mvnw clean package -DskipTests

# Make port 9090 available to the world outside this container
EXPOSE 9090

# Run the application
ENTRYPOINT ["java", "-jar", "target/em-project-0.0.1-SNAPSHOT.jar"]
