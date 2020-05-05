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

#### 运行报错Parsing error: The keyword 'import' is reserved

在`.eslintrc.js`中添加

```javascript
{
  "parserOptions": {
    "ecmaVersion": 7,
    "sourceType": "module"
  }
}
```

## Avoid using non-primitive value as key, use string/number value instead.

避免使用非基础变量作为循环的key,用string或number代替,在使用V-for时 需要注意:key需要使用基础变量,不能使用对象等

## 通过 Babel 和 webpack 使用 ES2015 模块，那么代码看起来更像

```javascript
import ComponentA from './ComponentA.vue'

export default {
  components: {
    ComponentA
  },
  // ...
}
```

### vue默认写法

```javascript
var ComponentA = { /* ... */ }

var ComponentB = {
  components: {
    'component-a': ComponentA
  },
  // ...
}
```

### 遇到个问题 vscode 设置好了末尾增加空行,但是format 自动清理空行

需要检查vscode的设置

```javascript
"files.insertFinalNewline": true,
```

还需要检查F1 - formatter config

```javascript
"files.insertFinalNewline": true,
```

### '$' is not defined

[https://blog.csdn.net/weixin_43945983/article/details/88294052](https://blog.csdn.net/weixin_43945983/article/details/88294052)

### 没有白屏的刷新页面方法

[https://blog.csdn.net/qi_dabin/article/details/81079632?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-2&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-2](https://blog.csdn.net/qi_dabin/article/details/81079632?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-2&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-2)


