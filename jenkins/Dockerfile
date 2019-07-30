FROM jenkins/jenkins:lts

MAINTAINER Oliver Castro <olivertamboboycastro@gmail.com>

USER root

RUN apt -y update \
    && apt install -y ca-certificates apt-transport-https \
    && wget -q https://packages.sury.org/php/apt.gpg -O- | apt-key add - \
    && echo "deb https://packages.sury.org/php/ stretch main" | tee /etc/apt/sources.list.d/php.list
RUN apt update \
    && apt install -y php7.1 rsync


RUN apt install -y php7.1-curl \
    php7.1-dom \
    php7.1-bcmath \
    php7.1-gd \
    php7.1-intl \
    php7.1-mbstring \
    php7.1-soap \
    php7.1-mcrypt \
    php7.1-mysql \ 
    php7.1-zip


RUN apt install -y rubygems
RUN gem install capistrano -v 3.6.1
RUN gem install capistrano-magento2
RUN gem install bundle

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && mv composer.phar /usr/local/bin/composer



