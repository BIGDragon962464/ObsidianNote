###### 安装Mysql
`docker pull mysql:8.0`
###### 运行 Mysql 容器：
`docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -d mysql:8.0`
> MYSQL_ROOT_PASSWORD=root 	Mysql数据库root的密码

###### 进入Mysql容器
`docker exec -it 658072f495d7 /bin/bash`
![image.png](https://cdn.nlark.com/yuque/0/2023/png/26726568/1681633883386-0dae38be-b175-4e6f-a649-034408f418f7.png#averageHue=%230b0604&clientId=ue95f5d59-7290-4&from=paste&height=113&id=u187796f6&originHeight=141&originWidth=1054&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=18639&status=done&style=none&taskId=u8de33f38-4805-4521-831f-39b9b54db60&title=&width=843.2)
###### 登录Mysql
`mysql -uroot -proot`

###### MySQL修改密码
`set password for root@localhost = password('root');`
