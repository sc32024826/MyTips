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

还需要注意根目录下的editconfig文件内容是否与设置冲突

修改rule 规则之后 需要重启 npm run dev

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

### Vue packages version mismatch:

需要把不匹配的包的版本号弄成一致,而不是更新包就可以,或者把两个包都更新到最新,且版本号一致

### 报错:

### versionRequirement: packageConfig.engines.node

### TypeError: Cannot read property 'node' of undefine

原因是```package.json```中缺少了生命引擎版本的配置

添加:

```js
"engines": {
    "node": ">= 6.0.0",
    "npm": ">= 3.0.0"
  }
```

### 禁用console.log()的几种方法

> 1.```uglifyjs-webpack-plugin```
> 
> 2.```terser-webpack-plugin```  实测成功
> 
> ```json
> const TerserPlugin = require('terser-webpack-plugin');
> module.exports = {
>     configureWebpack: config => {
>         config
>             .optimization = {
>             minimizer: [
>                 new TerserPlugin({
>                     terserOptions: {
>                         compress: {
>                             drop_console: true
>                         }
>                     }
>                 })
>             ]
>         }
>     }
> }
> ```
> 
> 
> 
> 3.```babel-plugin-transform-remove-console```


