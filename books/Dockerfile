FROM registry.redhat.io/ubi8/ubi
MAINTAINER Andre Bos a.bos@dji.minjus.nl
# DocumentRoot for Apache
ENV DOCROOT=/var/www/html
RUN yum --disableplugin=subscription-manager -y install httpd && yum --disableplugin=subscription-manager -y install npm && yum --disableplugin=subscription-manager clean all &&  echo "Hello from the httpd-parent container!" > ${DOCROOT}/index.html
RUN sed -i 's/Listen 80/Listen 8080/' /etc/httpd/conf/httpd.conf && chgrp -R 0 /var/log/httpd /var/run/httpd && chmod -R g=u /var/log/httpd /var/run/httpd
EXPOSE 8080
CMD httpd -D FOREGROUND
