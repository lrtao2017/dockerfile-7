# Python3.7.0 perl5.28.0
# 20180703

FROM centos7.5:Python-3.7.0

MAINTAINER lrtao2010@163.com

RUN yum clean all  && yum install -y gcc \ 
                   && mkdir /usr/local/perl
 
ADD perl-5.28.0.tar.gz /usr/local/
 
WORKDIR /usr/local/perl-5.28.0/
 
RUN ./Configure -des -Dprefix=/usr/local/perl
#RUN yum install make -y
RUN make && make test && make install
 
RUN ln -s /usr/local/perl/bin/perl /usr/bin/perl 
RUN ln -s /usr/local/perl/bin/cpan /usr/bin/cpan 
 
RUN (echo y;echo o conf urllist pop http://www.cpan.org/;echo o conf urllist push http://mirrors.aliyun.com/CPAN/;echo o conf commit)|cpan 
 
#安装模块并测试 
#RUN perl -MCPAN -e 'install Net::Server' 
#RUN perl -MNet::Server -e1 
 
WORKDIR /opt/ 
 
CMD ["/bin/bash"] 
