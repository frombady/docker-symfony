FROM php:8.1-fpm

RUN apt update && apt install -y \
    libpq-dev \
    wget \
    zlib1g-dev \
    libmcrypt-dev \
    libzip-dev \
    openssl \
    libpq-dev  \
    git \
    vim  \
    net-tools  \
    coreutils \
    libpng-dev \
    libz-dev \
    zlib1g-dev \
    libmemcached-dev \
    acl \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_pgsql pgsql opcache gd sockets

# xdebug
RUN pecl install xdebug-3.1.0 memcached redis \
    && docker-php-ext-enable xdebug memcached redis

RUN cd /tmp && git clone https://github.com/ImageMagick/ImageMagick.git ImageMagick-7.0.11 && cd /tmp/ImageMagick-7.0.11 \
  && ./configure && make && make install && ldconfig /usr/local/lib && rm -rf /tmp/ImageMagick-7.0.11

RUN rm -rf /tmp/pear

RUN echo "set mouse-=a" >> ~/.vimrc
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /symfony