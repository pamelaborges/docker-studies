FROM debian

RUN apt-get update && apt-get install -y apache2 && apt-get install curl
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

ENV APACHE_LOCK_DIR="/var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

ADD index.html /var/www/html/
HEALTHCHECK --interval=3m --timeout=3s \
	CMD curl -f http://localhost/ || exit 1

LABEL description="Server"
LABEL version="2.0.0"

WORKDIR /var/www/html/

VOLUME /var/www/html/

EXPOSE 80 8080

ENTRYPOINT ["/usr/sbin/apachectl"]
CMD ["-D", "FOREGROUND"]
