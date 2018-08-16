FROM httpd:2.4.34

COPY cert/*.key cert/*.cert /usr/local/apache2/cert/
COPY conf/httpd.conf        /usr/local/apache2/conf/
COPY htdocs/*               /usr/local/apache2/htdocs/

EXPOSE 80 443
