1 购买腾讯云  云服务器  优惠价格 首年99元  CentOS系统

2 分配安全组 包含22端口 用以ssh连接

3 绑定密钥对

4 ssh 连接: ssh -i ~/.ssh/密钥名称  root@ ip地址 

    ssh -i ~/.ssh/tencent root@106.54.20.38

5 安装python3
    安装python3 的依赖环境 
    ```yum -y install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel sqlite-devel zlib-devel libffi-devel MySQL-python mysql-devel```

###### 下载python3.7

```wget [https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz](https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz)```
wget [https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz]
```

    解压 tar -zxvf Python-3.7.4.tgz
    
    在/usr/loacl 下新建python3 文件夹
    回到python3的解压文件夹  ./configure --prefix=/usr/local/python3
    
    make
    make install
    
    ln -s /usr/local/python3/bin/python3 /usr/bin/python3
    
    vim ~/.bash_profile
    追加内容
    export PATH=$PATH:$HOME/bin:/usr/local/python3/bin
    
    为pip3 追加快捷命令
    ln -s /usr/local/python3/bin/pip3 /usr/bin/pip3
    
    安装 mysqlclient
    pip3 install mysqlclient

6 安装 django
    pip3 install django

    创建 django-admin 的快捷命令
    ln -s /usr/local/python3/bin/django-admin /usr/bin/
    
    在/home/www/ 下创建网站项目

7 上传项目文件
    setting.py 

8 安装 uwsgi 
    ```pip3 install uwsgi```

    快捷命令
    ln -s /usr/local/python3/bin/uwsgi /usr/bin/uwsgi3

9 安装 nginx

    yum -y install nginx 

10 更新sqlite3  参考 https://blog.csdn.net/qq_39969226/article/details/92218635
    wget https://www.sqlite.org/2019/sqlite-autoconf-3290000.tar.gz
    解压
    tar -zxvf sqlite-autoconf-3290000.tar.gz
    cd sqlite-autoconf-3290000
    ./configure --prefix=/usr/local
    make
    make install

Tips:
    如果出现server error 500, 应该是数据库的问题
