#this is docker-mysql images
#Version 1.0
#Author: niuhengbo

#Base images
from centos
#MAINTAINER
MAINTAINER hengbo niu

#ADD
ADD mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz /usr/local/


#RUN
RUN yum install ncurses-devel  gcc-c++ perl-Data-Dumper libaio -y  -y && useradd  -u 2000 mysql -s /sbin/nologin -M && ln -s /usr/local/mysql-5.7.17-linux-glibc2.5-x86_64/ /usr/local/mysql && rm -f /usr/local/mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz

#WORKDIR
WORKDIR /usr/local/mysql
ADD  my.cnf /usr/local/mysql/
RUN  mkdir -p /usr/local/mysql/data \
     && chown mysql.mysql -R /usr/local/mysql \
     && chown mysql.mysql -R /usr/local/mysql-5.7.17-linux-glibc2.5-x86_64 \
     && /usr/local/mysql/bin/mysqld --initialize-insecure --user=mysql --basedir=/usr/local/mysql --datadir=/usr/local/mysql/data \
     && touch /usr/local/mysql/mysqld.log \
     && chown mysql.mysql /usr/local/mysql/mysqld.log

ENV  PATH /usr/local/mysql/bin/:$PATH

# Define default command.
CMD  ["/usr/local/mysql/bin/mysqld_safe","--defaults-file=/usr/local/mysql/my.cnf","--basedir=/usr/local/mysql","--datadir=/usr/local/mysql/data","--user=mysql"]

# Define mountable directories.
VOLUME ["/usr/local/mysql/data/"]

# Expose ports.
EXPOSE 3306
