---
layout:     post
title:      "Hello 2019"
subtitle:   " \"Hello World, Hello Blog\""
date:       2019-11-8 17:11:04
author:     "JerryLiu"
header-img: "img/post-bg-universe.jpg"
catalog: true
tags:
    - 生活
---

## Ubuntu 使用笔记

### 1. Ubuntu 安装软件

#### 1. apt -get

```bash
sudo apt-get install xxxxxx

apt-get 参数说明：
apt-get remove xxx 卸载软件 xxx
apt-get update  更新软件数据库
apt-get upgrade 系统升级
```

#### 2. dkpg 安装 deb 包

```
sudo dkpg -i package.deb
```

#### 3. make install 源代码安装

```
3.1 执行configure文件配置环境
3.2 编译 sudo make
3.3 安装 sudo make install
```

### 2. Ubuntu 安装 Pycharm

官网下载链接：
https://www.jetbrains.com/pycharm/download/#section=linux

==注意事项：==
Ai 培训 Linux PC Python 环境都在 root 账户下，PyCharm 也必须安装到 root 账户下，不然不能使用其 root 环境；

解压下载压缩文件，copy 文件夹到 root 账户下，运行脚本：

```
sh ./Pycharm/bin/pycharm.sh
```

弹出可视化安装步骤，一步一步完成即可。

Pycharm 配置：
1、`Darcula` 黑色主题
2、快捷键映射 `Eclipse` 
3、添加翻译插件 `A8 Translate` ，使用快捷键 `Alt + T`
4、配置显示字体大小 font

### 3. Ubuntu 常用快捷键

`Ctrl + Alt + T` : 		打开新的终端
`Ctrl + Shift + T`： 新标签页打开新的终端

### 4. Vi 编辑器

Vi 编辑模式，删除键与方向键上下左右健乱码：

```
sudo vi /etc/vim/vimrc.tiny

set compatibale —>  set nocompatible
新加 set backspace = 2
```

直接install vim，可以规避上述问题：

```
sudo apt-get install vim
```

### 5. Git

```
sudo apt-get install git 
sudo apt-get install bash-compleion 「Tab 提示」
```

### 6. 搜索命令 grep/ack-grep/ag「推荐」

Ubuntu Linux 命令安装

```shell
sudo apt-get install silversearcher-ag
```

Mac 命令安装

```shell
brew install the_silver_searcher
```

ag 常用文本搜索，命令使用：

```
ag "string-to-search"
```

### 7. sudo 删除密码输入

终端执行：`sudo vi /etc/sudoers`

修改`%sudo ALL=(ALL:ALL) ALL` -> `%sudo ALL=(ALL:ALL) ALL`

### 8. Ubuntu 常用设置

#### 8.1 VMWare 虚拟机 Ubuntu 通过主机 shadowsocks 代理上网

PC windows 10 运行 shadowsockets ，「允许局域网连接」

使用桥接方式运行虚拟机   「虚拟机与局域网处于同一个局域网」

ubuntu -> NetWork -> NetWork proxy -> Manual -> 地址填写宿主win10 ip，代理端口「1080」

#### 8.2 Ubuntu 设置分辨率为1920*1080

1. sudo vim /etc/profile ,文件末尾添加

```shell
xrandr --newmode "1920x1080_60.00" 173.00 1920 2048 2248 2576 1080 1083 1088 1120 -hsync +vsync
xrandr --addmode Virtual1 "1920x1080_60.00"
```

2. 编译执行刚配置的 profile 文件source /etc/profile
3. 系统设置修改分辨率为 1920 * 1080

#### 8.3 设置别名alias

新增终端打开 Explorer 命令 .zshrc 文件中新增

```shell
# add open Explorer ubuntu alias by LiuDongBing
alias open="nautilus"
```

### 9. 终端 Terminal 常用设置 

#### 9.1 Terminal  Tab 键补全忽略大小写

编辑~/.inputrc, 无责新建 touch .inputrc

```shell
# auto complete ignoring case
set show-all-if-ambiguous on
set completion-ignore-case on
```



