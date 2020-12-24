#### 移除已经在远程仓库中的文件  分 四步

`git rm --cached -r filename`
`git add .`
`git commit -m ""`
`git push XXX branch`

#### 创建分支    -b 表示 创建并切换到新分支

` git checkout -b 分支名`

##### 相当于 同时运行两条命令

`git branch 分支名`
`git checkout 分支名`

##### 列出所有分支

`git branch`

##### 带有星号的分支为当前分支

##### 将分支合并到当前分支下

`git merge 分支名`

##### 删除已经被合并的分支

`git branch -d 分支名`删除远程分支

##### 删除远程分支
`git push origin --delete 分支名

###### 放弃本地修改，直接覆盖之

`git reset --hard`
`git pull ogrin    master`

### 多个remote 同步push

在仓库中显示隐藏文件 `.git`,其中有个`config`文件 打开 添加

```[remote "all"]
[remote "all"]
	url = git@github.com:sc32024826/uniapp.git
	url = ssh://git@gitlab.servers.mchains.cn:30234/ShanYing.uniapp.git
```

`push`的时候 `git push all master`


