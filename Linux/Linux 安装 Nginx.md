###### 1.安装依赖和相关库：
`yum -y install gcc-c++ zlib-devel openssl-devel libtool`
###### 2.下载nginx安装包并解压：
`cd /usr/local`
`wget http://nginx.org/download/nginx-1.14.0.tar.gz`
`tar -zxvf nginx-1.14.0.tar.gz`
###### 3.配置和安装
`cd nginx-1.14.0`
`./configure --prefix=/usr/local/nginx`
`make && make install`
###### 4.启动Nginx：
`cd ../nginx/sbin`
`./nginx`
