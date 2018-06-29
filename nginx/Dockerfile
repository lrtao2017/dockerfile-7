# NGINX 1.14.0
# 20180629

FROM centos7.5:yum

MAINTAINER lrtao2010@yeah.net

RUN yum clean all && yum install gcc pcre pcre-devel zlib zlib-devel make -y 

RUN mkdir -p /usr/local/nginx/

ADD nginx-1.14.0.tar.gz /usr/local/

WORKDIR /usr/local/nginx-1.14.0/
RUN ./configure --prefix=/usr/local/nginx && make && make install
ADD nginx.conf /usr/local/nginx/conf

WORKDIR /opt/
ENTRYPOINT /usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
