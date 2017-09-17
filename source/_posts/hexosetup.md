title: Hexo的安装方法
tags:
	Hexo
---
> Hexo使用cmd命令形式安装，首先在电脑中新建一个文件夹，例如在C盘下新建一个Blog文件夹
> 
> 打开cmd.exe 输入cd c:\blog
> 
> 然后输入npm i -g hexo 进行安装
> 
> 安装完成后可以输入hexo -v 查看版本
> 
<!--more-->
> 输入hexo init 进行初始化
> 
> 初始化完成后就可以在Blog文件夹下看到：
> -   ● node_modules：是依赖包
> -   ● public：存放的是生成的页面
> -   ● scaffolds：命令生成文章等的模板
> -   ● source：用命令创建的各种文章
> -   ● themes：主题
> -   ● _config.yml：整个博客的配置
> -   ● db.json：source解析所得到的
> -   ● package.json：项目所需模块项目的配置信息
> 生成静态页面
> hexo generate（hexo g也可以）
> 本地启动
> 启动本地服务，进行文章预览调试，命令：
> hexo server
> 
> 然后在网页中输入:http://localhost:4000 能看到Hexo主页
> 