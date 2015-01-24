FROM registry.[MYDOCKERREGISTRY].dev/ubuntu:14.04

MAINTAINER Peter van Wilderen "peter@yoast.com"

# Install Nginx
RUN apt-get -y install nginx

# Say Hello World
RUN mkdir /var/www && echo "<h1>Default NginX Docker page</h1>" >> /var/www/index.html

ADD default /etc/nginx/sites-enabled/default
ADD nginx.conf /etc/nginx/nginx.conf

# expose port 80
EXPOSE 80

CMD ["nginx"]