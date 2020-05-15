##### 本地环境 Windows 7 Service Pack 1,未激活

##### 服务器版本 ubuntu 18

###### 生成私钥跟公钥,公钥为XX.PUB -t 表示生成的密钥类型 -C 表示密钥描述 -f 可选 密钥名称

`ssh-keygen -t rsa -C "shencheng_1014@aliyun.com"`

###### 查看公钥内容

`cat id_rsa.pub`

###### 或者

`vim id_rsa.pub`

###### 以上 参考链接 : https://blog.csdn.net/Beamon__/article/details/90700921

###### 在服务器端 通过 pull 拉取 网站代码时 一直报错 Permission denied (publickey)

最后解决办法是 删除密钥  重新生成新的密钥 添加至github 

##### 测试 与 github的ssh连接是否 可用 -vT 表示输出日志 -T 表示不输出日志

`ssh -vT git@github.com`

`mysql> update mysql.user set authentication_string=password('18705735690') where user='root' and Host ='localhost';`

##### PyCharm 激活方法    测试时间 2019年8月27日10:01:13

https://blog.csdn.net/nc514819873/article/details/89081251

##### 将公钥 提交到 服务器版本18.223.119.125    -i 表示使用某位置的公钥  此例中使用 ~/Downloads/AmazonKey.pem

`scp -i ~/xxx/xxx id_rsa.pub ubuntu@XXX.XXX.XXX.XX:.`

##### touch 创建

`touch authorized_keys`

##### cat 显示 文件

##### 写入文件

`cat id_rsa.pub >> ~/.ssh/authorized_keys`

##### 重命名 + 移动命令 file 表示需要移动的文件 newfile 表示需要移动的新路径或者新命名

`mv file  newfile`

##### .shh/config 配置

```
Host aws
 HostName ec2-18-223-119-125.us-east-2.compute.amazonaws.com
 Port 22
 User ubuntu
 IdentityFile ~/Downloads/AmazonKey.pem
```

##### linux 系统 改变文件 所有者 chown  新的用户  文件

`chown ubuntu .ssh`

##### nginx 相关命令

重启 `sudo nginx -s reload`
关闭    ` sudo nginx -s stop`
`/etc/init.d/nginx start`
`/etc/init.d/nginx stop`
`/etc/init.d/nginx reload`

##### uwsgi

`uwsgi --ini uwsgi.ini `            # 启动
`uwsgi --reload uwsgi.pid  `        # 重启
`uwsgi --stop uwsgi.pid`            # 关闭

##### 读取uwsgi实时状态

`uwsgi --connect-and-read uwsgi/uwsgi.status`

##### 执行1时报错2:

1 `source ~/.local/bin/virtualenvwrapper.sh`
2` /usr/bin/python: No module named virtualenvwrapper`

错误原因：

Ubuntu安装了2.7和3.x两个版本的python,在安装时使用的是

`sudo pip3 install virtualenvwrapper`
在我运行的时候默认使用的是python2.x,但在python2.x中不存在对应的模块

解决办法:
`export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3`

##### 退出虚拟环境

`deactivate`

##### 解决 sqlite3 低版本问题

`export LD_LIBRARY_PATH="/usr/local/lib"`

##### uwsgi 配置

```
[uwsgi]
socket = 127.0.0.1:8001
chdir = /home/www/root
module = PowerSky.wsgi
master = true
processes = 1
threads = 2
vacuum = true
chmod-socket = 664
max-requests = 2000

daemonize = %(chdir)/uwsgi/uwsgi.log
stats = %(chdir)/uwsgi/uwsgi.status
pidfile = %(chdir)/uwsgi/uwsgi.pid
```

##### 在centos 上安装python3

###### 1.下载安装文件 格式为tgz

`wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz`

###### 2.解压

`tar -zxvf Python-3.7.4.tgz`

###### 3.进入文件夹

`cd Python-3.7.4`

###### 4.编译和安装 前两行确保安装之后会从新的目录中查找sqlit3

`LD_RUN_PATH=/usr/local/lib ./configure LDFLAGS="-L/usr/local/lib" CPPFLAGS="-I/usr/local/include"  --prefix=/opt/python3.5`
`LD_RUN_PATH=/usr/local/lib make`
`make`
`sudo make install`


