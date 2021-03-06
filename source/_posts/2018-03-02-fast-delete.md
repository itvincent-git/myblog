---
title: FastDelete-Windows下快速删除文件夹的工具
date: 2018-03-02 19:25:49
categories: windows
keywords: nodejs,windows,delete
tags: nodejs
---


FastDelete是一个快速删除文件夹的工具，基于nodejs里文件操作的强大性能。特别是文件夹里存在大量小文件的情况下，FastDelete能够比Windows的删除操作快上十倍。

> 最近项目发展得很快，代码越来越多，加上**AndroidStudio**构建时会在**build**目录下生成大量文件。有时需要清理一下**build**目录，或者把某些分支代码目录删除掉，节省宝贵的硬盘空间。不过问题来了，Windows下对于这种大量小文件的操作非常慢，现在删除一个分支竟然要2-3分钟的时间才行，所以才萌生了这个工具的想法。
>
> 一开始用命令行执行还是稍复杂了点，后来加上了**文件夹右键菜单**后，删除得更爽快了。



#### 使用前提

安装[NodeJS](https://nodejs.org/en/)


#### 下载代码
[点击下载zip](https://github.com/itvincent-git/fast-delete/archive/1.0.0.zip)

[进入github下载](https://github.com/itvincent-git/fast-delete)

#### 首次使用

执行 `install.bat`批处理文件。

- 它会下载依赖包到本地的**node_modules**目录下
- 自动生成并注册reg文件，弹窗中点击“是”添加上右键菜单



#### 右键菜单运行

- 在文件夹的右键菜单中，点击**极速删除**，即可删除该目录

  ![image](http://upload-images.jianshu.io/upload_images/8375846-09eab080a9c642bf?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



#### 命令行运行

- 在cmd中执行`node delete.js <deleteDir>`
