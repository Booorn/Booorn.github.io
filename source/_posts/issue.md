title: Hexo添加评论或留言板
tags: [Hexo,留言板,评论]
toc: true
reward: true
---
#### 相关信息
> 首先提供一下我的博客的相关信息参考一下：  
搭建环境：Hexo+github  
使用主题：Yilia  
主题下载地址[：yilia主题下载 ](https://github.com/litten/hexo-theme-yilia.git )  
下载命令：$ git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia  
<!--more-->

#### 配置步骤
> 废话不多说，下面进入正题。  
评论和留言板实现的方法其实是一致的，使用Yilia主题的朋友应该会发现，主题下的_config.yml文件中有加上评论的配置，有像多说，网易云跟帖，畅言，github等。由于我搭建博客的时候，听说多说，网易云等已经不支持服务了，所以最后我决定使用github，这个貌似应该就不会停止服务了吧。   
操作方法：  
在上面提到的_config.yml文件中，配置github评论的是:  

```
#5、Gitment
gitment_owner: false      #你的 GitHub ID 
gitment_repo: ''          #存储评论的 repo
gitment_oauth:
  client_id: ''           #client ID
  client_secret: ''       #client secret
```

> 这部分。  
上面提到的gitment_owner、gitment_repo我们都知道，一个是填你的用户名，一个填你的仓库地址， 即xxxx.github.io。那么下面的id和secret怎么填写呢？这个时候就需要去github注册一个了，注册地址：https://github.com/settings/applications/new  
> 1. 该页面主要注意两项的填写：Homepage URL和Authorization callback URL，这两项请填上你的网站地址，其他两项任意填写。  
> 2. 填写完后点击register application，之后就会生成Client ID和Client Secret，没找到的请将页面向上滚动。然后拷贝贴进上文_comfig.yml文件对应位置。
> 3. hexo g
> 4. 在浏览器打开博客界面，便看到评论区，按照提示操作Login with GitHub 然后 Init，你的评论区便可以投入使用了。
>
> 注意，如果操作完成，打开界面有提示错误，请检查 Homepage URL和Authorization callback URL，或者gitment_owner、gitment_repo是否填写错误，本地测试会出现Comments Not Initialized 错误提示，这个时候hexo d，然后再在网页操作即可。

#### 其他方法
> yilia主题的这个配置方法，一旦配置，所有的文章下面都有评论栏。网络上也有其他的教程，是在具体的页面下加上:  

```
<div id="container"></div>
<link rel="stylesheet" href="https://imsun.github.io/gitment/style/default.css">
<script src="https://imsun.github.io/gitment/dist/gitment.browser.js"></script>
<script>
var gitment = new Gitment({
  owner: 'xxx',  //改你自己的名字
  repo: 'xxx',  //专门储存评论一个GitHub仓库
  oauth: {
    client_id: 'xxxx', //改为你自己的，下同
    client_secret: 'xxxx', 
  },
})
gitment.render('container')
</script>

```

> 教程请参考[：利用 GitHub 的 Issues 来搭建评论系统](https://imsun.net/posts/gitment-introduction/)   
我试过这种方法，发现我写的文章会出现在评论栏的下方，具体原因暂时还没有去排查，有兴趣的可以试试。