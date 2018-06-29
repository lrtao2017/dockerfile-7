# Add and modify Alibaba Cloud yum source 
# 20180628

FROM scratch

MAINTAINER lrtao2010@yeah.net

ADD centos-7-docker.tar.xz /

LABEL org.label-schema.schema-version = "1.0" \
    org.label-schema.name="CentOS Base Image" \
    org.label-schema.vendor="CentOS" \
    org.label-schema.license="GPLv2" \
    org.label-schema.build-date="20180531"

#修改时区
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

#修改yum源
RUN mkdir /etc/yum.repos.d/bak && mv /etc/yum.repos.d/*.repo /etc/yum.repos.d/bak
COPY *.repo /etc/yum.repos.d/
RUN yum clean all

CMD ["/bin/bash"]
