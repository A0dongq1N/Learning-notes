# Docker

## 安装

### docker for windows

1. 下载docker,官网下载慢，可以去这里下载(https://oomake.com/download/docker-windows)
2. windows开启`hype-v`,在`控制面板-程序-获得程序-启用或关闭windows功能`
3. 安装后程序会引导你重启

## 基础命令

### 容器声明周期管理

### 容器操作

#### 查找镜像

`--no-trunc`的意思是完整显示`DESCRIPTION`

```shell
PS C:\Users\jeremyqin> docker search scrapy  --no-trunc
NAME                                        DESCRIPTION                                                                                          STARS               OFFICIAL            AUTOMATED
vimagick/scrapyd                            An open source and collaborative framework for extracting the data you need from websites.           60                                      [OK]
scrapinghub/scrapinghub-stack-scrapy                                                                                                             27                                     
istresearch/scrapy-cluster                  This Scrapy project uses Redis and Kafka to create a distributed on demand scraping cluster.         18                                     
aciobanu/scrapy                             An open source and collaborative framework for extracting the data you need from websites.           13                                      [OK]
trcook/docker-scrapy                        dockerized scrapy built on alpine linux.                                                             12 
```



#### 拉取镜像到本地

```

```



### 容器rootfs命令

### 镜像仓库

### 本地镜像管理

### info|version



## 3 常见问题

#### 3.1 问题

```powershell
error during connect: Get http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.26/containers/json: open //./pipe/docker_engine: The system cannot find the file specified. In the default daemon configuration on Windows, the docker client must be run elevated to connect. This error may also indicate that the docker daemon is not running.
```

- 解决办法

  出现这个问题，就是docker的`客户端`没有启动，很傻逼的问题

#### 3.2 问题（待解决）

```powershell
Error response from daemon: invalid registry endpoint https://docker.oa.com/v1/: Get https://docker.oa.com/v1/_ping: x509: certificate signed by unknown authority. If this private registry supports only HTTP or HTTPS with an unknown CA certificate, please add `--insecure-registry docker.oa.com to the daemon's arguments. In the case of HTTPS, if you have access to the registry's CA certificate, no need for the flag; simply place the CA certificate at /etc/docker/certs.d/docker.oa.com/ca.crt
```

#### 3.3 问题

```powershell
### PS C:\Users\jeremyqin> docker pull vimgick/scrapyd
Using default tag: latest
Error response from daemon: pull access denied for vimgick/scrapyd, repository does not exist or may require 'docker login'
```

- 解决方法：

  利用自己的`dockerhub`账号密码登录即可

#### 3.4 问题

```powershell
Error response from daemon: manifest for letsdeal/scrapy:latest not found
```

- 解决方法：

  