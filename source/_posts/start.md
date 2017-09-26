---
title: 开篇
tags: test,hexo
categories: 
  - others

thumbnail: /gallery/blue-water1.jpg

photos:
- https://www.hdwallpapers.net/previews/starry-night-over-corsica-986.jpg
- https://www.hdwallpapers.net/previews/water-plant-close-up-979.jpg
- /gallery/hydric-hammock.jpg
---
摘要
<!-- more -->

## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/deployment.html)



### Markdown

More info: [Markdown](http://blog.zhangruipeng.me/hexo-theme-hueman/2014/12/25/Markdown/)

More info: [Writing](https://hexo.io/docs/writing.html)


### internal links 

``` bash
{% post_path start %}
// /2017/08/11/start/
{% post_link start %}
// <a href="/2017/08/11/start/">开篇</a>
{% post_link start 自定义标题 %}
// <a href="/2017/08/11/hello-world/">自定义标题</a>

{% asset_path example.jpg %}
// /2017/08/11/hello-world/example.jpg
{% asset_link example.jpg %}
// <a href="/2017/08/11/hello-world/example.jpg">example.jpg</a>
{% asset_link example.jpg Example %}
// <a href="/2017/08/11/hello-world/example.jpg">Example</a>
{% asset_img example.jpg %}
// <img src="/2017/08/11/hello-world/example.jpg">
```
{% post_path start %} <br/>
{% post_link start %} <br/>
{% post_link start 自定义标题 %} <br/>

{% asset_path example.jpg %} <br/>
{% asset_link example.jpg %} <br/>
{% asset_link example.jpg Example %} <br/>
{% asset_img example.jpg %}


### Gallery example

#### You can also add photos between text to create another gallery like this:
``` bash
![hydric hammock](/gallery/hydric-hammock.jpg "hydric hammock")
```
![hydric hammock](/gallery/hydric-hammock.jpg "hydric hammock")



#### To add a photo gallery placeholder to your post, just add the following lines to your front-matter:

``` bash
photos:
- https://www.hdwallpapers.net/previews/starry-night-over-corsica-986.jpg
- https://www.hdwallpapers.net/previews/water-plant-close-up-979.jpg
- /gallery/hydric-hammock.jpg
```


#### Finally, you can also use Justified Gallery to display you photos in a grid:

``` bash
<div class="justified-gallery">
![hydric hammock](/gallery/hydric-hammock.jpg "aa hydric hammock")
![hydric hammock](/gallery/hydric-hammock.jpg "bb hydric hammock")
![hydric hammock](/gallery/hydric-hammock.jpg "aa hydric hammock")
![hydric hammock](/gallery/hydric-hammock.jpg "bb hydric hammock")
</div>
```

<div class="justified-gallery">
![hydric hammock](/gallery/hydric-hammock.jpg "aa hydric hammock")
![hydric hammock](/gallery/hydric-hammock.jpg "bb hydric hammock")
![hydric hammock](/gallery/hydric-hammock.jpg "aa hydric hammock")
![hydric hammock](/gallery/hydric-hammock.jpg "bb hydric hammock")
</div>


