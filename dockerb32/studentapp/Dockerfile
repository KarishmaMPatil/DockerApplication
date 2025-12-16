FROM ubuntu:22.04

LABEL name=" dev karishma"

RUN apt-get update -y && \
   apt-get install unzip openjdk-11-jdk -y 

ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.113/bin/apache-tomcat-9.0.113.zip /opt/

WORKDIR /opt

RUN unzip apache-tomcat-9.0.113.zip && \
    rm apache-tomcat-9.0.113.zip

ADD https://s3-us-west-2.amazonaws.com/studentapi-cit/student.war /opt/apache-tomcat-9.0.113/webapps/

ADD https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar /opt/apache-tomcat-9.0.113/lib/

COPY context.xml /opt/apache-tomcat-9.0.113/conf/


EXPOSE 8080

RUN chmod +x /opt/apache-tomcat-9.0.113/bin/catalina.sh

CMD ["/opt/apache-tomcat-9.0.113/bin/catalina.sh", "run"]