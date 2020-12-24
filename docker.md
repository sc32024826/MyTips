### 查看运行的镜像:docker ps



### 查看本地镜像:docker images



### 安装镜像:docker pull 镜像名:标签



### 标记标签:docker tag name:tag namespace/name:tag



### 推送镜像:docker push namespace/name:tag



### 删除本地镜像:docker rmi 镜像id -f (强制删除)



#### 运行镜像: docker run --name  自定义的名字 -p 宿主机端口:容器端口 -d 容器名 -v 文件夹映射

以上-p 表示 分配端口  

-d 表示 后台运行 

-v 文件夹映射: 宿主机目录:容器目录

--rm 停止后移除