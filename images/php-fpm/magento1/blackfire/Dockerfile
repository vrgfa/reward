ARG PHP_VERSION
FROM docker.io/rewardenv/php-fpm:${PHP_VERSION}-magento1
USER root

RUN yum install -y pygpgme \
    && curl -o - "http://packages.blackfire.io/fedora/blackfire.repo" | sudo tee /etc/yum.repos.d/blackfire.repo \
    && yum install -y blackfire-php \
    && yum clean all \
    && rm -rf /var/cache/yum

COPY blackfire/etc/php.d/*.ini /etc/php.d/

USER www-data
