FROM php:7.0
MAINTAINER Michael Oldroyd <docker@michaeloldroyd.co.uk>

RUN apt-get update \
  && apt-get install -y git zlib1g-dev libxml2-dev \
  && docker-php-ext-install zip \
  && docker-php-ext-install pdo_mysql \
  && docker-php-ext-install sockets \
  && docker-php-ext-install bcmath \
  && docker-php-ext-install soap \
  && curl -sS https://getcomposer.org/installer \
  | php -- --install-dir=/usr/local/bin --filename=composer

RUN composer global require phing/phing pear/archive_tar --prefer-dist

ENV PATH /root/.composer/vendor/bin:$PATH

WORKDIR /var/www

CMD echo "Ready for Build Tasks!"