1. 开启服务
```shell
更多windows服务
```

2. 安装wsl
```shell
wsl --update --web-download
```

3. 在store里安装ubuntu（记得关代理）

00000. 换源之前安装llvm！！！！

4. 换源(:%d删除全部,记得关代理)
```shell
sudo vim /etc/apt/sources.list
```
```shell
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
```

```shell
sudo apt update
```
5. 卸载
```shell
wsl --unregister Ubuntu-22.04
```