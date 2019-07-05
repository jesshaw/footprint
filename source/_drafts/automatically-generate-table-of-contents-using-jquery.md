---
title: 为markdown生成的html自动添加动态导航
tags: markdown, html
categories: 
  - html

thumbnail: /gallery/blue-water1.jpg

---
markdown通常是#标签与生成h标题，当文件内容过大时，通常需要添加导航，用以快速定位到内容。markdown在展示时，通常是html格式，因此在html可以动态添加导航，减少重复劳动。
<!-- more -->

## 首选引入jquery实现
```html 
<script
  src="http://code.jquery.com/jquery-2.2.4.min.js"
  integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44="
  crossorigin="anonymous"></script>
```

## 接着添加导航的实现逻辑
```html 
<script type="text/javascript">
$(document).ready(function() {
	var nav = $("<div id='nav'></a>");
	$("body").prepend(nav);
    $("h1, h2, h3, h4, h5").each(function(i) {
        var current = $(this);
        nav.append("<a href='#" + current.prop("id") + "' title='" + current.prop("tagName") + "'>" + current.text() + "</a>");
    });
});
</script>
```

## 添加相应样式
```html 
#nav {
  top: 0;
    width: 200px;
    height:100%;
    position: fixed;
    left: 0;
    overflow: auto;
}

#nav a {
    display: block;
    color: #0094FF;
}

#nav a[title=H1] {
    font-size: 22px;
}

#nav a[title=H2] {
    font-size: 20px;
    padding-left: 10px;
}

#nav a[title=H3] {
    font-size: 18px;
    padding-left: 20px;
}

#nav a[title=H4] {
    font-size: 16px;
    padding-left: 30px;
}

#nav a[title=H5] {
    font-size: 14px;
    padding-left: 40px;
}

</style>
```