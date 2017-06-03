FROM php:7.1.1-fpm

RUN docker-php-ext-install pdo_mysql \
 && docker-php-ext-install mysqli \
 && docker-php-ext-install json \
 && docker-php-ext-install opcache \
 && docker-php-ext-install zip

RUN apt-get update
 && apt-get install -y libmagickwand-6.q16-dev --no-install-recommends \
 && apt-get install -y zlib1g-dev \
 && ln -s /usr/lib/x86_64-linux-gnu/ImageMagick-6.8.9/bin-Q16/MagickWand-config /usr/bin \
 && pecl install imagick \
 && echo "extension=imagick.so" > /usr/local/etc/php/conf.d/ext-imagick.ini \
 && echo "extension=php_zip.dll" > /usr/local/etc/php/conf.d/ext-zip.ini
