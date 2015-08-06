---
layout: post
category: "Python"
title: "Linux下Python安装"
tags: ["Linux,Python"]
---

Linux下一般都有预装Python，但是版本都较低，有时需要安装相对较高的版本。  

###下载
首先，需要到官网下载所需要的Python版本：<https://www.python.org/downloads>，这里我下载的是：Python-3.4.3.tgz  

###安装
####解压：  

    tar -xzvf Python-3.4.3.tgz  

####编译&安装：  
  在编译前先在/usr/local建一个文件夹python3（作为python的安装路径，以免覆盖老的版本）：  

    mkdir /usr/local/python3  

  进入到 Python-3.4.3 目录，执行如下命令生成Makefile文件，Makefile主要是被下一步的 make 命令所使用，并使用 --prefix 命令来制定安装路径：  

    ./configure --prefix=/usr/local/python3  

  执行 make 进行编译：  

    make  

  安装：  

    make install  

  将原来/usr/bin/python链接改为别的名字：  

    mv /usr/bin/python /usr/bin/python_old  

  再建立新版本python的链接：  

    ln -s /usr/local/python3/bin/python3 /usr/bin/python  

安装完成，输入python，可以看见当前python的版本信息。  