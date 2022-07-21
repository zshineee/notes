# Docker安装

https://docs.docker.com/engine/install/ubuntu/

## 1.卸载旧版本

```shell
 sudo apt-get remove docker docker-engine docker.io containerd runc
```

## 2.设置仓库

1. 更新 `apt` 包索引并安装包，以允许 `apt` 通过 `HTTPS` 使用仓库

   ```shell
    sudo apt-get update
    sudo apt-get install ca-certificates curl gnupg lsb-release
   ```

2. 添加 `Docker `的官方 `GPG` 密钥

   ```shell
    sudo mkdir -p /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   ```

3. 使用以下命令设置仓库

   ```shell
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

## 3.安装 Docker 引擎

```shell
 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

通过运行 `hello-world` 映像来验证 `Docker Engine` 是否正确安装

```shell
 sudo docker run hello-world
```

