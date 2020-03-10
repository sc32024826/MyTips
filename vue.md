### 使用脚手架生成vue项目

1. 使用图形化界面生成:`vue ui`

2. 使用命令行生成:`vue create "appName"`

### 运行vue项目

`npm run serve`

### 解决alt+shift+f 格式化导致vue报错 双引号

在根目录新建`.prettierrc`文件

```javascript
{
    
    "semi": false,       //行尾是否使用分号

    "singleQuote": true  //字符串使用单引号

}
```

### 解决格式化代码之后 vue中 代码缩进为2空格

在`settings.json`文件中添加

`"vetur.format.options.tabSize": 4`

##### Vue 项目启动抛出 Expected indentation of 2 spaces but found 1 tab

在根目录新建`.eslintrc.js`

```javascript
module.exportes = {
    'rules':{
        'no-tabs':'off'
    }
}
```






