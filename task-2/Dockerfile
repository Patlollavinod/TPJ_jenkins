FROM ubuntu:latest

# Install Java
RUN apt-get update && \
    apt-get install -y openjdk-11-jdk && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install Apache webserver
RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install Tomcat
RUN apt-get update && \
    apt-get install -y tomcat9 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Deploy sample web application
COPY spring-petclinic-2.7.3.jar /var/lib/tomcat9/webapps/

# Expose Apache and Tomcat ports
EXPOSE 80
EXPOSE 8080

# Start Apache and Tomcat
CMD /usr/sbin/apache2ctl -D FOREGROUND && \
    /usr/share/tomcat9/bin/catalina.sh run
    ----------------------
    docker build -t myapp .
    docker run -p 80:80 -p 8080:8080 myapp

