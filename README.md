# dockerfile

自己编写的dockerfile文件
默认没有上传压缩包，如果需要clone下来，上传文件中需要的压缩包就可以使用了。

MySQL安装包下载地址：https://cdn.mysql.com//Downloads/MySQL-5.7/mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz
mongod安装包下载地址：https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-3.4.6.tgz
nginx安装包下载地址：http://nginx.org/download/nginx-1.10.1.tar.gz

最终目录如下
```
mongod/
├── Dockerfile
├── mongo.conf
├── mongodb-linux-x86_64-rhel70-3.4.6.tgz
└── mongodb-start.sh

mysqld/
├── Dockerfile
├── my.cnf
└── mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz

nginx/
├── Dockerfile
└── nginx-1.10.1.tar.gz
```