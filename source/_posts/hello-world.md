---
title: Github Pages+Hexo 搭建博客之旅
summary: 利用github pages 和 hexo 半小时搭建简易博客
desc: 利用github pages 和 hexo 搭建博客
---

#### 1.Github Pages
Github Pages可以免费托管，所以把博客托管到github上。

首先，创建一个github仓库，仓库的命名格式为：yourusername.github.io，然后根据提示进行下一步。

![](https://user-gold-cdn.xitu.io/2018/2/25/161cbc6ad4c63e17?w=921&h=420&f=png&s=23585)

#### 2.Hexo搭建博客

1.首先要安装下node.js（官网下载）,如果已经安装可以跳过。

2.安装git（官网下载）

3.安装Hexo：
```
$ npm install -g hexo
```
检测是否安装成功
```
$ hexo version
```
4.本地静态hexo博客
* 命令生成模板：
```
$ hexo init blog
```
* 命令进入blog文件，输入以下命令：
```
$ npm install
```
* 运行hexo s命令查看是否搭建成功
```
$ hexo s
```

![](https://user-gold-cdn.xitu.io/2018/2/25/161cbd13ae05a71f?w=1242&h=586&f=png&s=289202)
#### 2.配置博客
** 1.用户信息 **配置
```
user_name: your name
user_avatar: your avatar
user_location: your location
user_description: about you introduction

// this info will show About page
user_contact: 
user_introduction:

// config you share info
weibo_username: 
zhihu_username: 
github_username:
twitter_username: 
facebook_username:  
linkedin_username:
```

** 2.部署He **xo博客
* 配置_config.yml的部署:
```
deploy:
  type: git
  repo: git@github.com:fed-hjx/fed-hjx.github.io.git
  branch: master #默认master
```
* 清除缓存
```
$ hexo clean
```
* 生成静态网页
```
$ hexo g
```
* 本地查看效果
```
$ hexo s
```
* 部署到git
```
$ hexo d
```
* [打开连接查看](https://fed-hjx.github.io/)
