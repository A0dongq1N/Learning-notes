[TOC]

# git 学习笔记 

## git通用

### 查看当前HEAD指向哪儿

```shell
cat .git/HEAD
```



## github

### 如何添加sshkey到github

1. `ssh-keygen -t rsa -C "github注册邮箱"`，这个步骤会在`用户主目录`下生成`.ssh目录`
2. 将这个目录下的`id_rsa.pub`中的内容全部复制出来，用于在github上新建sshkey时添加内容
3. github上新建sshkey
4. `ssh -T git@github.com`测试是否添加成功