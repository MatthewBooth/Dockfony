FROM debian:jessie
ARG WEBROOT_PATH
ARG SERVER_NAME

RUN apt-get update && apt-get install -y \
    nginx

ADD nginx.conf /etc/nginx/
ADD symfony.conf /etc/nginx/sites-available/

RUN ln -s /etc/nginx/sites-available/symfony.conf /etc/nginx/sites-enabled/symfony
RUN rm /etc/nginx/sites-enabled/default

RUN sed -i -e "s|root {{ webroot_target }};|root ${WEBROOT_PATH}/public;|g" -e "s|server_name {{ servername_target }};|server_name ${SERVER_NAME};|g" /etc/nginx/sites-enabled/symfony

RUN echo "upstream php-upstream { server app:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
