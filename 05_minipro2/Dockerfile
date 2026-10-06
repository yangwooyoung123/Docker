FROM quay.io/centos/centos:10

RUN yum -y install httpd php php-fpm php-cli php-common php-mysqlnd php-opcache \
  && yum clean all

# COPY를 하면 복사후 따로 압축 해제를 해야하지만 ADD는 복사후 압축해제까지 해줌
VOLUME /var/www/html /var/log/httpd
ADD src.tar /var/www/html
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

EXPOSE 80/tcp

ENTRYPOINT ["/entrypoint.sh"]