# The base image for the Docker image. Serve as a starting point.
FROM eclipse-temurin:17-jdk-jammy


# Sets the working directory inside the Docker container to /app. 
WORKDIR /app


# Copies the .mvn/ directory from local PC to the /app/.mvn/ directory inside the Docker container.
# It contains Maven wrapper files and configurations.
COPY .mvn/ .mvn


# Copies the mvnw Maven wrapper executable and the pom.xml file from local PC to the /app/ inside the Docker container.
COPY mvnw pom.xml ./


# Copies the entire src/ directory from local PC to the /app/src/ directory inside the Docker container.
COPY src ./src


# Executes the Maven wrapper (mvnw) command inside the Docker container. 
# It runs the install Maven lifecycle phase 
# The -DskipTests option skips running any tests during the build process. 
# This command will download dependencies, compile the source code, and package the application into a JAR file.
RUN ./mvnw install -DskipTests


# Lastly, it runs the spring-boot:run using the Maven wrapper(mvnw). 
# This command starts the Spring Boot application in the Docker container.
CMD ["./mvnw", "spring-boot:run"]