---
title: 我的python开发环境管理实践
author: Jason Lee
tags: python
abbrlink: 6f4edb74
date: 2023-06-21 08:33:38
categories:
---

## 前言

前段时间做项目，摸索出了一套比较稳定且适合自己的 python 环境管理方案，适用于 win10/11。

## venv 的使用

我在之前很长一段时间里用的是 anaconda 作为包管理器。但是一些缺点让我放弃了它：首先 anaconda 太庞大了，其次它的 conda 库经常找不到一些库或者网络速度极慢。后来我转到了 venv（它的全称我忘了，很容易和另一个包管理器混淆）。venv 和 conda 一样，虚拟环境被包含在一个文件夹中，里面有一个脚本文件用于激活。

我会在电脑的 C 盘下直接开辟一个名为 venv 的文件夹用于存储所有虚拟环境，这样便于记住和在命令行工具中输入路径激活。打开 cmd，并切换到文件夹下，新建环境的命令如下：

```
python -m venv <envname>
```

这样就创建了一个文件夹，内部目录为：

![16873086912601687308690642.png](https://cdn.jsdelivr.net/gh/li199-code/blog-imgs@main/16873086912601687308690642.png)

其中，Lib 装了环境，Scripts 有激活和退出环境的脚本。以 powershell 为例，输入脚本路径，就激活了环境：

```
C:\venv\helloalgo\Scripts\activate.ps1
```

退出：`deactivate`. 通过`pip list`，新环境预装的包为：

![16873091022651687309101499.png](https://cdn.jsdelivr.net/gh/li199-code/blog-imgs@main/16873091022651687309101499.png)

可以说什么都没有，具有很大的灵活性了，完全由用户掌控。

## vscode 和 pycharm 选择创建好的 venv

如果是一些小脚本，单独运行的那种，我会选择 vscode；如果用到了 django 等创建一个项目，则用 pycharm。

首先说说 vscode。右下角选择 venv 解释器路径：

![16873102812591687310281154.png](https://cdn.jsdelivr.net/gh/li199-code/blog-imgs@main/16873102812591687310281154.png)

然后是 pycharm,同样是右下角，add new interpreter->existing->选择解释器位置：

![16873105482641687310547564.png](https://cdn.jsdelivr.net/gh/li199-code/blog-imgs@main/16873105482641687310547564.png)

这时候要新建一个 terminal，就会自动将环境挂载上。

## 总结

针对小脚本和大项目的不同场景下，基于 venv+vscode/pycharm 的 python 环境管理方案。
