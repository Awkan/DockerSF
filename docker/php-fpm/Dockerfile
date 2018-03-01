FROM ubuntu:16.04

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get -y upgrade && apt-get install -y software-properties-common
RUN export LANG=C.UTF-8;add-apt-repository -y ppa:ondrej/php && apt-get update
RUN apt-get install -y \
    php-apcu php-common php-fdomdocument php-xml php7.1-cli php7.1-common php7.1-curl php7.1-fpm php7.1-gd php7.1-intl php7.1-json php7.1-mbstring php7.1-mysql php7.1-opcache php7.1-readline php7.1-soap php7.1-xml \
    curl git zip

RUN usermod -s /bin/bash www-data

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    chmod +x /usr/local/bin/composer && \
    composer global require hirak/prestissimo

COPY fpm-pool.conf /etc/php/7.1/fpm/pool.d/www.conf
COPY php.ini /usr/local/etc/php/php.ini
RUN touch /var/log/php7.1-fpm.log && chown www-data:www-data /var/log/php7.1-fpm.log
RUN mkdir -p /run/php/ /var/www/.composer/
RUN chown www-data:www-data -R /run/php/ /var/www/.composer/

CMD ["/usr/sbin/php-fpm7.1", "-F"]
