# this is my first Dockerfile
#Version 1.0 
#Author: niuhengbo


#Base images 
From centos
#MAINTAINER
MAINTAINER hengbo niu


#ADD 
ADD  nginx-1.10.1.tar.gz /usr/local/src

#RUN
RUN yum install -y wget gcc gcc-c++ make openssl-devel pcre pcre-devel
RUN useradd -s /sbin/nologin -M www

#WORKDIR
WORKDIR /usr/local/src/nginx-1.10.1
RUN  ./configure --prefix=/usr/local/nginx --user=www --group=www  --with-http_ssl_module --with-http_stub_status_module  &&make && make install
RUN echo "daemon off;" >> /usr/local/nginx/conf/nginx.conf
RUN echo "11111"

ENV PATH /usr/local/nginx/sbin:$PAHT
EXPOSE 80
CMD ["nginx"]
