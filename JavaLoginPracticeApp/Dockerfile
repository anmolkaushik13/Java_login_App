# FROM eclipse-temurin:17-jdk-alpine
# WORKDIR /app
# COPY target/*.jar app.jar
# EXPOSE 8080
# ENTRYPOINT ["java","-jar","app.jar"]


# Build stage
# FROM maven:3.9.9-eclipse-temurin-17 AS build
# WORKDIR /app
# COPY pom.xml .
# RUN mvn dependency:go-offline
# COPY src ./src
# RUN mvn package -DskipTests

# # Runtime stage
# FROM eclipse-temurin:17-jdk-alpine
# WORKDIR /app
# COPY --from=build /app/target/*.jar app.jar
# EXPOSE 8080
# ENTRYPOINT ["java","-jar","app.jar"]


FROM tomcat:10.1-jdk17-temurin

# Default apps hata do (clean)
RUN rm -rf /usr/local/tomcat/webapps/*

# WAR copy karo
COPY target/JavaLoginShowcase-1.0.0.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["catalina.sh", "run"]
