FROM php:7.3-fpm

WORKDIR /var/www/apps

COPY ./php.ini /usr/local/etc/php/php.ini

RUN apt update -y && \
   apt-get upgrade -y && \
   apt install -y autoconf make g++ gcc tzdata bash git nodejs zip npm unzip curl software-properties-common  

RUN docker-php-ext-install -j$(nproc) bcmath pdo_mysql mysqli && \
  pecl install xdebug && \
  docker-php-ext-enable xdebug

RUN cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# Composeインストール
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# nodejs 12インストール
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -

RUN apt-get clean && \
  rm -rf /var/lib/apt/lists/*
