---
layout:     post
title:      "[Test]-Git与github"
date:       2017-08-10 10:12:29
author:     "PeriHe"
header-img: "img/post-bg-blog.jpg"
catalog: true
tags:
    - 工具
---

>这里是学习过程中使用到的Git与github的总结

git三层结构

工作区working directory

暂存区staging index

版本库git directory(Repository)

Git文件的四种状态

untracked未被追踪

Modified在工作区修改了未添加到暂存区

Staged   添加到了暂存区未添加到版本库

Committed数据被安全的存储在本地库中

Git的安装
下载..

$ git --version ：查看git版本

几个简单的控制台命令使用：

$ cd D://www/20160218/  ：进入

$ mkdir blog                         ：创建文件夹

$ ls                                          ：文件夹列表 

Git基本命令
常用操作：

$ git init ：初始化git仓库，会添加.git文件

$ git config ：git config --global user.name HaaappyLi          : 配置用户名

                         git config --global user.email hpl@hepeili.cn  ：配置邮箱

                         git config --list                                                          : 查看配置结果

$ git status：查看文件状态

$ git add ：git add filename  ：将文件添加到暂存区

                     git add .                 ：将工作目录下的所有修改的文件添加到暂存区

$ git commit ：git commit –m ‘description’   ：将暂存区的文件添加到版本库

                            git commit –am ‘description’ ：跳过git add添加到暂存区命令（直接将工作区所有已跟踪文件提交，未跟踪（untracked）的命令不能使用）

$ git log： 查看提交历史

删除操作

$ git rm filename

$ git mv oldname newname

撤销操作

$ git commit --amend：撤销上次提交并将暂存区文件重新提交

原理: git commit --amend 会用一个新的 commit 更新并替换最近的 commit。

$ git checkout --filename：拉取暂存区的文件并将其替换工作区的文件也即撤销对工作区文件的修改。

原理: git checkout 会把工作区文件修改到之前记录的某个状态。你可以提供一个你想返回的分支名，默认的是 HEAD。

记住git checkout -- [file] 是一个危险的命令，这很重要。 你对那个文件做的任何修改都会消失 - 你只是拷贝了另一个文件来覆盖它。 除非你确实清楚不想要那个文件了，否则不要使用这个命令。

$ git reset HEAD filename：拉取最近一次提交到版本库中的这个文件到暂存区，该操作不影响工作区。

HEAD:头指针，指向最新的提交，可以将HEAD换成版本号来拉取任何一个版本。

git reset HEAD filename拉到暂存区再git chechout撤销工作区文件

原理: git reset会把你的代码库历史返回到指定的 SHA 状态。就像是这些提交从来没有发生过。默认保留工作区文件。

$ git reset --option 版本号：option 有 hard,soft,mixed

注：在调用时加上 --hard 选项可以令 git reset 成为一个危险的命令（可能导致工作目录中所有当前进度丢失！）；不加选项地调用 git reset 并不危险，工作区文件并不会被修改。  它只会修改暂存区域。

github基本使用
以下为初学时阅读英文文档的总结：

第一步：创建仓库
仓库可以包含项目所需的所有东西，建议在创建的时候勾选README，并里面填写项目相关信息。
1.右上角+
2.命名
3.写项目简介
4.选择 Initialize this repository with a README

第二步：创建分支
仓库默认只有一个master分支。
我们用分支来做各种尝试和编辑，然后将结果提交到master分支。
当你在master下创建你一个分支时，就会在新分支上产生一个master的副本，如果之后其他人更新了master，你也可以拉取这些更新到你的分支。
修复bug和功能，完成后合并到master。

第三步：提交更改
保存更改称为commit，每一次commit都有相关的提交信息，用于解释为什么做更改，以便其他人理解。
1.点击要更改的文件
2.点击小铅笔
3.更改内容
4.写更新原因和描述
5.提交

HTTPS和SSH的区别

在git中clone项目有两种方式：HTTPS和SSH，它们的区别如下： 
HTTPS：不管是谁，拿到url随便clone，但是在push的时候需要验证用户名和密码；
SSH：clone的项目你必须是拥有者或者管理员，而且需要在clone前添加SSH Key。SSH 在push的时候，是不需要输入用户名的，如果配置SSH key的时候设置了密码，则需要输入密码的，否则直接是不需要输入密码的。

拉取提交流程：

1、使用git clone https://github.com/xxxxxxx/xxxxx.git克隆到本地

2、对拉取的项目进行编辑

3、git add . 

4、git commit -m "提交说明"

5、git push origin master 将本地更改推送到远程master分支。

标签: 工具