FROM php:8.2-fpm-alpine

# ติดตั้ง dependencies ที่จำเป็น
RUN apk update && apk add --no-cache \
    bash \
    git \
    unzip \
    zip \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd \
    && docker-php-ext-install pdo pdo_mysql

# คัดลอกไฟล์ php.ini
COPY php.ini /usr/local/etc/php/

# ติดตั้ง Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html
