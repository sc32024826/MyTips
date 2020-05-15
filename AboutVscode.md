### 1.新安装完vscode terminal 可能会有字体问题,表现为字宽错误

解决的办法是 在file- preferences - settings
搜索 "terminal font family" 输入字体 "monospace" 

### 2. sftp 配置

```json
{
     "name": "PowerSky",
     "host": "106.54.20.38",
     "protocol": "sftp",
     "port": 22,
     "username": "root",
     "privateKeyPath": "~/.ssh/tencent",
     "remotePath": "/home/www/root",
     "uploadOnSave": true,
     "ignore": [
         ".vscode",
         ".git",
         ".DS_Store",
         "__pycache__",
         ".idea",
         "venv",
         "polls/__pycache__",
         "polls/migrations",
         "PowerSky/__Pycache__",
         "uwsgi.log",
         "uwsgi.pid",
         "uwsgi.status",
         "CollectStatic"
     ]
 }
```


