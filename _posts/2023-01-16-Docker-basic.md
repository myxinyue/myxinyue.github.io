---
layout: post
title: Docker简单介绍
categories: [docker，容器]
description: Docker简单介绍
keywords: 
---



Docker 是一个开源的应用容器引擎，让开发者可以打包他们的应用以及依赖包到一个可移植的镜像中，然后发布到任何流行的 Linux或Windows 机器上，也可以实现[虚拟化](https://so.csdn.net/so/search?q=虚拟化&spm=1001.2101.3001.7020)。容器是完全使用沙箱机制，相互之间不会有任何接口。

 

完整的Docker有以下几个部分组成：

DockerClient客户端
Docker Daemon守护进程
Docker Image镜像
DockerContainer容器

 

Docker 使用客户端-服务器 (C/S) 架构模式，使用远程API来管理和创建Docker容器。Docker 容器通过 Docker 镜像来创建。

容器与镜像的关系类似于面向对象编程中的对象实例与类。

容器=对象实例
镜像=类

 

docker 的镜像概念类似虚拟机的镜像。是一个只读的模板，一个独立的文件系统，包括运行容器所需的数据，可以用来创建新的容器。

docker利用容器来运行应用：docker容器是由docker镜像创建的运行实例。

docker容器类似虚拟机，可以执行包含启动，停止，删除等。每个容器间是相互隔离的。容器中会运行特定的运用，包含特定应用的代码及所需的依赖文件。可以把容器看作一个简易版的linux环境（包含root用户权限，进程空间，用户空间和网络空间等）和运行在其中的应用程序。

![img](/images/posts/2023-01-16-Docker-basic/1665306-20220725113634564-667998410.png)

 

 

（  docker create <image -id > ：为指定的镜像添加一个可读写层，构成一个新的容器；）

 

在Docker的生命周期中，最核心的两个部分，一个是镜像 Images，一个是容器 Containers。

镜像运行起来就是容器。

容器服务运行的过程中，基于原始镜像做了改变，比如安装了程序，添加了文件，也可以提交回去 (commit)成为镜像。

 

docker仓库是用来包含镜像的位置，docker提供了一个注册服务器（register）来保存多个仓库，每个仓库又可以包含多个具备不同tag的镜像，

docker运作中使用的默认仓库是docker hub公共仓库。

仓库支持的操作类似git，当用户创建了自己的镜像之后就可以使用push命令将它上传到共有或者私有的仓库。这样下次再另外一台机器上使用这个镜像的时候只需要从仓库里面pull下来就可以了。





