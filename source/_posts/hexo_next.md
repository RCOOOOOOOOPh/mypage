---
title: How to use Hexo and Next theme
categories:
- Web
---

# Hexo:

## Initialize a new blog folder

```bash
$ hexo init
```

then generate:

```bash
$ hexo g
```

## Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

## Run server

``` bash
$ hexo server
```

or using

```bash
$ hexo s
```

then you can view your page at local server http://localhost:4000.

More info: [Server](https://hexo.io/docs/server.html)

## Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

## Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)

## Connect to github

https://zhuanlan.zhihu.com/p/105715224

First, set SSH key

https://zhuanlan.zhihu.com/p/103391101

(later will write a separate page for it because it's importannt)

then add this to _config.yml:

```yaml
deploy:
  type: git
  repository: https://github.com/{yourname}/{yourname}.github.io.git  #repository address
  branch: master
```

then install hexo-deployer-git:

```bash
$ npm install hexo-deployer-git --save
```

then 

```bash
$ hexo clean
$ hexo g
$ hexo d
```

then it will be deployed to github.

## Front-Matter

https://hexo.io/zh-cn/docs/front-matter.html#%E5%88%86%E7%B1%BB%E5%92%8C%E6%A0%87%E7%AD%BE

## Add a categories page

https://victoryofymk.github.io/2018/10/23/Hexo%E5%88%9B%E5%BB%BA%E5%88%86%E7%B1%BB%E9%A1%B5%E9%9D%A2/

run

```bash
$ hexo new page categories
```

then there will be a new folder blog_directory\source\categories, and a file index.md inside.

add type: "categories" to the index.md file

## Add a tags page

similar as categories page, run

```bash
$ hexo new page tags
```

then add type: "categories" to the index.md file under blog_directory\source\tags