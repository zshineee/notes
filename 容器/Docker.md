# Docker

## 简介

Docker 是一个应用打包、分发、部署的工具，相当于轻量的**虚拟机**，只虚拟软件需要的运行环境。

**Images**

镜像是包含创建容器的说明的一个只读模板（相当于安装包）。

**Container**

容器是机器上的沙箱进程，是镜像的运行实例。

## 命令

### 创建一个新的容器并运行

提取镜像（如果本地没有），创建容器，并运行 `/bin/bash`；

```shell
docker run -it [镜像名称] -dp 80:80 /bin/bash
```

- **-i:** 以交互模式运行容器，通常与 `-t` 同时使用；
- **-t:** 为容器重新分配一个伪输入终端，通常与 `-i` 同时使用；
- **-d:** 后台运行容器；
- **-p:** 指定端口映射，格式为：主机（宿主）端口:容器端口；

### 构建镜像

```shell
docker build -t [镜像名称]
```

- **-t：**指定构建后镜像的名称；

- **-f：**dockerfile 一般位于构建上下文的根目录，也可以通过 `-f` 指定 dockerfile 的位置。

### 停止容器

```shell
docker stop [容器ID]
```

### 删除容器

```shell
docker rm [容器ID]
```

### 列出镜像列表

```shell
docker images
```

### 列出正在运行的容器

```shell
docker ps
```

- **-a：**列出所有容器（包含未运行的容器）

### 查看日志

``` shell
docker logs --tail=1000 [容器ID]
```

### 进入容器

``` shell
docker exec -it [容器ID] /bin/bash
```

## Dockerfile
