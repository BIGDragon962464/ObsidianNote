### 1. nginx反向代理的好处：
- 提高访问速度
- 进行负载均衡
- 保证后端服务安全
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202309061715979.png)

### 2. nginx反向代理的配置方式：
nginx.conf文件
```
server{
		listen 80;
		server_name localhost;

		location /api/{
					  proxy_pass http://localhost:8080/admin/;  #反向代理
		}
}
``` 

### 3. nginx负载均衡的配置方式：
nginx.conf文件
```
upstream webservers{
		server 192.168.100.128:8080;
		server 192.168.100.129:8080;
}

server{
		listen 80;
		server_name localhost;

		location /api/{
					  proxy_pass http://localhost:8080/admin/;  #负载均衡
		}
}
```
