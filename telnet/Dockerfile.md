FROM httpd:2.4
LABEL nl.amis.smeetsm.httpd.name="Apache Httpd" nl.amis.smeetsm.httpd.version="2.4"
 
#COPY ./www/ /usr/local/apache2/htdocs/
ARG PORT
RUN sed -ri "s/^Listen 80/Listen $PORT/g" /usr/local/apache2/conf/httpd.conf
ENTRYPOINT ["httpd-foreground"]
