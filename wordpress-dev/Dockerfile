FROM registry.[MYDOCKERREGISTRY].dev/ubuntu:14.04

MAINTAINER Peter van Wilderen "peter@yoast.com"

# Install Nginx / PHP5 and Mysql
RUN apt-get -y install nginx && \
	apt-get -y install php5 && \
	apt-get -y install mysql

	# mysqladmin -u root PASSWORD "dockertest"

# Say Hello World
RUN mkdir /var/www && echo "<h1>Test de Docker</h1>" >> /var/www/index.html

ADD default /etc/nginx/sites-enabled/default
ADD nginx.conf /etc/nginx/nginx.conf

# expose port 80
EXPOSE 80

CMD ["nginx"]