###### node - koa2 学习笔记

NPM是随同NodeJS一起安装的包管理工具，能解决NodeJS代码部署上的很多问题，常见的使用场景有以下几种：

1. 允许用户从NPM服务器下载别人编写的第三方包到本地使用。

2. 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。

3. 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用。

##### 可以用nvm 进行node版本进行管理

###### 下载 nvm 安装包 ：https://github.com/coreybutler/nvm-windows/releases

##### 安装koa

```
npm install koa2
```

##### 安装 Node 模块时，如果指定了 --save 参数，那么此模块将被添加到 package.json 文件中 dependencies 依赖列表中。 然后通过 npm install 命令即可自动安装依赖列表中所列出的所有模块。

###### 使用 koa应用生成器生成 app

koa2 myapp

###### 启动项目

npm start

###### supervisor 监控应用下所有文件，一旦文件被修改就重新载入程序文件 这就实现了部署

npm install -g supervisor

###### 使用 supervisor 代替node 命令启动应用

supervisor app.js
