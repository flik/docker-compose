FROM centos:centos7

RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN yum-config-manager --enable remi-php71 -y

# INSTALL APACHE AND PHP PACKAGES (Apache 2.4 & PHP 7.0)
RUN	yum -y update \
	&& yum --setopt=tsflags=nodocs -y install \
	php \
	php-mcrypt \
	php-cli \
	php-gd \
	php-curl \
	php-mysql \
	php-devel \
	php-mysql \
	php-pdo \
	php-mbstring \
	php-zip \
        php-soap \
	php-gd \
	php-xml \
        php-mysqlnd \
        php-pecl-zip \
        freetype \
        fontconfig \
        php-json \
	unzip \
        httpd \
        httpd-tools \
        apr \
        apr-util \
	&& rm -rf /var/cache/yum/* \
	&& yum clean all

# RUN mkdir -p /var/www/html/public
# ENV APP_HOME /var/www/html

# change ownership of our applications
# RUN chown -R www-data:www-data $APP_HOME

COPY index.php /var/www/html/index.php

CMD ["/usr/sbin/httpd", "-DFOREGROUND"]
