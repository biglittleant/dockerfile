#this is mongo Dockerfile
#Version 1.0
#Author: niuhengbo

#Base images
From centos
#MAINTAINER
MAINTAINER hengbo niu

#ADD BASE FILE
ADD mongodb-linux-x86_64-rhel70-3.4.6.tgz  /usr/local/src/
RUN mkdir /data/app -p && mv /usr/local/src/mongodb-linux-x86_64-rhel70-3.4.6 /data/app/mongod

#CHANGE TO WORKDIR
WORKDIR /data/app/mongod
RUN mkdir /data/app/mongod/{db,logs,config} && rm -f /usr/local/src/mongodb-linux-x86_64-rhel70-3.4.6.tgz
ADD mongo.conf config/

# Define mountable directories.
VOLUME ["/data/app/mongod/db"]
CMD ["/data/app/mongod/bin/mongod","--config","/data/app/mongod/config/mongo.conf"]

# Expose ports.
EXPOSE 27017
