[TOC]

# git 学习笔记 

## git通用

### 查看当前HEAD指向哪儿

```shell
cat .git/HEAD
```

### 放弃本地修改，直接用远程代码覆盖本地

1.git fetch --all

2.git retset --hard origin/master

## github

### 如何添加sshkey到github

1. `ssh-keygen -t rsa -C "github注册邮箱"`，这个步骤会在`用户主目录`下生成`.ssh目录`
2. 将这个目录下的`id_rsa.pub`中的内容全部复制出来，用于在github上新建sshkey时添加内容
3. github上新建sshkey
4. `ssh -T git@github.com`测试是否添加成功



## git for windows

### MINGW64 git status中文乱乱码

1. git config --global core.quotepath false
2. 关闭窗口
3. 重新打开窗口