FROM ubuntu:latest

# Java Installation
RUN apt-get update && apt-get install -y openjdk-11-jdk

# Apache Installation
RUN apt-get install -y apache2 && apt-get install -y wget

# Tomcat9 Installation
RUN wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz && \
    tar xzf apache-tomcat-9.0.55.tar.gz && \
    rm apache-tomcat-9.0.55.tar.gz && \
    mv apache-tomcat-9.0.55 /usr/local/tomcat9
COPY .  SampleWebApp.war /usr/local/tomcat9/webapps/
EXPOSE 8080
CMD service apache2 start && /usr/local/tomcat9/bin/catalina.sh run
