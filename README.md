# Git submodule使用指南（一）

### 当主项目不包含子工程的情况

##### 第一步

在本地主项目直接clone子工程：

`git  submodule add git@github.com:bighb/liba.git `

新增成功之后，运行`git status`会在父仓库发现增加了2个变化

1. new file: .gitmodules
2. new file: someSubmodule（实际上并不是一个file）

当前子工程内容可能不是最新的，执行`git submodule update`也不会是最新的子工程代码

##### 第二步

执行更新命令：

`git submodule update --remote`

此时主包会更新子工程最新内容

### 当主项目包含子工程的情况

##### 第一步

执行子工程初始化命令：

```
git submodule init
git submodule update
```

此时子工程内容可能不是子工程最新代码，需要执行第二步

##### 第二步

当前子工程代码更新至最新

`git submodule update --remote`

