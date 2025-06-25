# Use Maven with Java 17
FROM maven:3.8.3-openjdk-17

# Copy the entire project into the container (no space between ./ and opt/)
COPY ./ /opt/

# Set working directory
WORKDIR /opt

# Optional: Replace application.properties if needed
# RUN rm -rf src/main/resources/application.properties
# COPY application.properties backend/src/main/resources/application.properties

# Build the project and skip tests
RUN mvn clean package -DskipTests

# Set working directory to the build output folder
WORKDIR /opt/target

# Expose the port your app runs on
EXPOSE 8080

# Run the generated JAR file
CMD ["java", "-jar", "student-registration-backend-0.0.1-SNAPSHOT.jar"]
