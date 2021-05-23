FROM ubi7/ubi:7.7

MAINTAINER rhf rah14234@gmail.com

ENV PORT 8080

RUN yum install -y httpd

RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
    chown -R 48:48 /etc/httpd/logs/ && \
    chown -R 48:48 /run/httpd/

USER apache

Expose ${PORT}

Copy ./src/ /var/www/html/ 

CMD ["httpd", "-D", "FOREGROUND"]
