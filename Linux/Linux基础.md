###### 赋予权限
`chmod 777 *`
###### 查询服务
`ps -ef | grep +服务名`
###### 关闭进程
`kill -9 +进程号`
###### 查看端口号
`netstat -tunlp`
###### 筛选端口号查询
`netstat -tnlp | grep :80`
###### 准确查找端口号
`netstat -apn | grep 9090`
###### 关闭端口号
`sudo fuser -k -n tcp 9090`

