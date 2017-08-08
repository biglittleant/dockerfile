# Docker for CentOS

#Base image
FROM centos

#Who
MAINTAINER biglittleant

#EPEL
ADD epel.repo /etc/yum.repos.d/

#Base pkg
RUN yum install -y openssh-clients openssl-devel openssh-server wget mysql-devel vim git  tree net-tools sudo psmisc && yum clean all

# For SSHD
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key
RUN echo "root:123456" | chpasswd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
