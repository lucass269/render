# render
Render免费云服务器
永久云服务器申请连接：https://dashboard.render.com/

#注意：bash的文件名必须是 Dockerfile
``` bash
# 使用 Ubuntu 22.04 作为基础镜像
FROM ubuntu:22.04

# 安装 Shellinabox
RUN apt-get update && \
    apt-get install -y shellinabox && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# 设置 root 用户的密码为 'root'
RUN echo 'root:frepai' | chpasswd

# 暴露 22 端口
EXPOSE 22

# 启动 Shellinabox
CMD ["/usr/bin/shellinaboxd", "-t", "-s", "/:LOGIN"]
```

VPS申请完成之后，需要安装最基础的软件包，因为我们申请的是底层的unbutu操作系统，操作性非常强，需要什么就安装什么！

更新系统：

``` Bash
apt update
```
安装基础软件包

``` Bash
apt install sudo curl wget nano screen git
```
安装neofetch工具

``` Bash
sudo apt install neofetch
```
清空终端窗口

``` Bash
clear
```
调用显示系统信息命令

``` Bash
neofetch
```
