# nginx

### 1.基础配置

```yaml
server{
	listen 80;     #监听端口 
	server_name localhost;
	location /{    #拦截
		proxy_pass http://XX.XX.XX.XX:端口号  #代理
	}
}
```

### 2.负载均衡

```
upstream group1{
	server 192.168.1.2  weight=1 #权重
	server 192.168.1.3	weight=10
}
server{
	listen 80;     #监听端口 
	server_name localhost;
	location /{    #拦截
		proxy_pass http://group1  #代理
	}
}
```









