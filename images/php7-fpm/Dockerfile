FROM php:7.2-fpm-alpine
	
# install PHP extensions
RUN apk add --no-cache --virtual .build-deps \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev

ENV MEMCACHED_DEPS zlib-dev libmemcached-dev cyrus-sasl-dev
RUN apk add --no-cache --update libmemcached-libs zlib
RUN set -xe \
    && apk add --no-cache --update --virtual .phpize-deps $PHPIZE_DEPS \
    && apk add --no-cache --update --virtual .memcached-deps $MEMCACHED_DEPS \
    && pecl install memcached \
    && echo "extension=memcached.so" > /usr/local/etc/php/conf.d/20_memcached.ini \
    && rm -rf /usr/share/php7 \
    && rm -rf /tmp/* \
    && apk del .memcached-deps .phpize-deps

RUN docker-php-ext-install \
	mysqli \
	pdo_mysql \
	pdo \
	gd \
	opcache

RUN apk add --no-cache --update \
        php7-session \
        php7-dom \
        php7-xml \
        php7-xmlreader \
        php7-ctype \
        php7-ftp \
        php7-json \
        php7-curl \
        php7-sockets \
        php7-zlib \
        php7-mcrypt \
        php7-bz2 \
        php7-phar \
        php7-openssl \
        php7-posix \
        php7-zip \
        php7-calendar \
        php7-iconv \
        php7-imap \
        php7-soap \
        php7-dev \
        php7-pear \
        php7-redis \
        php7-mbstring \
        php7-xdebug \
        php7-exif \
        php7-xsl \
        php7-bcmath
	
# set recommended PHP.ini settings
# see https://secure.php.net/manual/en/opcache.installation.php
RUN { \
        echo 'opcache.memory_consumption=128'; \
	echo 'opcache.interned_strings_buffer=8'; \
	echo 'opcache.max_accelerated_files=4000'; \
	echo 'opcache.revalidate_freq=2'; \
	echo 'opcache.fast_shutdown=1'; \
	echo 'opcache.enable_cli=1'; \
} > /usr/local/etc/php/conf.d/opcache-recommended.ini

# Cleanup
RUN apk del --purge \
        *-dev
	
VOLUME /var/www/html

CMD ["php-fpm"]

EXPOSE 9000