# Use OpenJDK 17 slim image
FROM openjdk:17-jdk-slim

WORKDIR /app

# Copy everything to container
COPY . .

# Make mvnw executable
RUN chmod +x ./mvnw

# Build the project, skipping tests for faster build
RUN ./mvnw clean package -DskipTests

# Find the generated jar dynamically and run it
CMD java -jar $(ls target/*.jar | grep -v 'original' | head -n 1)
