---
layout: post
title: 误删本地未Push远程分支恢复方法
category: PHP
tags: 误删,本地未Push,分支,git,恢复
keywords: 误删,本地未Push,分支,git,恢复
description: 
---



你有没有误删没 push 到远端仓库分支的经历，过后为敲了几天的代码懊悔不已，只能凭着记忆还原代码，其实强大的 Git 提供了一个方法：

在项目目录输入`git reflog`查看 commit 记录，找到最后提交的代码 commit SHA1值。

就可以根据 SHA1 值，创建一个新的分支来恢复代码`git branch <brandName> <sha1> `。

试试吧。
