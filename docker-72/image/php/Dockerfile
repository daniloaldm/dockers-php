FROM php:7.2-fpm

RUN docker-php-source extract \
    && apt-get update && apt-get install -y \
    libxml2-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    libcurl3-dev \
    libicu-dev \
    libxml2-dev \
    libxslt-dev \
    && docker-php-ext-install curl \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-ext-install intl \
    && docker-php-ext-install bcmath \
    && docker-php-ext-install mbstring \
    && apt-get install -y libmcrypt-dev \
    && pecl install mcrypt-1.0.1 \
    && docker-php-ext-enable mcrypt \
    && docker-php-ext-install hash \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install simplexml \
    && docker-php-ext-install soap \
    && docker-php-ext-install xml \
    && docker-php-ext-install xsl \     
    && docker-php-ext-install zip \
    && docker-php-ext-install json \  
    && docker-php-ext-install iconv \    
    && docker-php-ext-install opcache \  
    && docker-php-ext-install mysqli \  
    && docker-php-ext-enable mysqli \ 
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && docker-php-source delete \
	&& php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer
