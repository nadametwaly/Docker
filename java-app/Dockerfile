FROM maven:3.8-openjdk-17 AS build
WORKDIR /app
COPY pom.xml  .
RUN mvn dependency:go-offline -B 
COPY . .
RUN mvn package -DskipTests
RUN cp target/*.jar app.jar
CMD ["java", "-jar", "app.jar"]