# Base image for Plurish UI

FROM php:8.2-fpm-bookworm

RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    zip \
    unzip \
    npm

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN npm i -g n && n 20 && npm i -g npm@latest

RUN docker-php-ext-install pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer \
    | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash \
        && apt-get install symfony-cli