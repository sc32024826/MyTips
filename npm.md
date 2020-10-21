#### 清除未被使用的模块

npm prune

#### CNPM

```shell
alias cnpm="npm --registry=https://registry.npm.taobao.org \
--cache=$HOME/.npm/.cache/cnpm \
--disturl=https://npm.taobao.org/dist \
--userconfig=$HOME/.cnpmrc"
```

#### gitbash工具 使用 `vue create XXX` 命令时无法使用方向键选择的解决方法

在`~/.bashrc `文件中 添加 `alias vue='winpty vue.cmd'` <font color=#FF0000>注意等号附近不能有空格</font>

 

