FROM Ubuntu:latest 
# This is my base image on which deployment is done
LABEL author="dev karishma"
#This is label to add metadata to image
RUN apt-get update && \
    apt-get install apache2 unzip -y && \
#We are updating the image, installing the apache2 server and unzip utility

ADD https://templatemo.com/download/templatemo_578_first_portfolio /var/www/html/
#in here we have downloaded a sample webapp from internet and added to our apache server root directory

RUN rm -rf /var/www/html/index.html && \
    unzip /var/www/html/templatemo_578_first_portfolio.zip -d /var/www/html/ && /
    mv /var/www/html/templatemo_578_first_portfolio/* /var/wwww/html/
#in here we have removed the default index.html file of apache server and unzip the downloaded webapp 
#moved all the content to apache server root directory

#WORKDIR    /var/www/html/

EXPOSE 80
# We are exposing port 80 to access your webapp

CMD [ "apache2ctl", "-D", "FOREGROUND" ]
