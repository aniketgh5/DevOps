FROM maven:3.9.9-eclipse-temurin-21-jammy AS BUILD_IMAGE
RUN git clone https://github.com/hkhcoder/vprofile-project.git
RUN cd vprofile-project && git checkout containers && mvn install


FROM tomcat:10-jdk21
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]

# This Dockerfile builds a Java web application using Maven and deploys it to a Tomcat server.
# The application is cloned from a GitHub repository, built with Maven, and the resulting WAR file is copied to the Tomcat webapps directory.
# The Tomcat server is then started, exposing port 8080 for access to the application.
# To build the Docker image, run:
# docker build -t vprofile-app .
# To run the Docker container, use:
# docker run -d -p 8080:8080 vprofile-app
# The application can then be accessed at http://localhost:8080
# Note: Ensure that Docker is installed and running on your machine before executing the above commands.
# The Dockerfile uses a multi-stage build to first compile the Java application with Maven and then deploy it to a Tomcat server.
