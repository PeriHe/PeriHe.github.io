---
layout:     post
title:      "[Test]-css兼容篇"
date:       2017-08-30 17:27:00
author:     "PeriHe"
header-img: "img/post-bg-blog.jpg"
tags:
    - 兼容
---

> 虽然很多公司不再对低版本ie兼容，因以前稍微学过，这里整理一下笔记。

本篇针对IE6和IE7的兼容，解决办法大都采用避免不兼容的写法 或者 使用css hack；

css hack ：针对不同的浏览器写不同的css样式的过程，就叫做css hack ！在开发过程中有其他办法尽量尽量尽量不使用hack！

 \9   IE10及之前的浏览器识别；

+ *  IE7及以前

_    IE6及以前 

1、HTML5标签不兼容问题

解决方案一：用js创建标签，并转成block；

解决方案二：引入支持html5的插件。

2、块元素包含块元素导致的问题：避免不能包含的元素（p,td,h）包含；

3、margin-top传递：触发BFC，haslayout；上下margin叠压：尽量使用同一方向的margin；

4、IE6不支持inline-block：加*display:inline;*zoom:1;

5、IE6最小高度为19px，如果想设置更小高度:加overflow:hidden;

6、当元素设置浮动后再设置margin会产生双倍margin值：加*display：inline；

7、li里元素都浮动时，每个li下方都会产生4px的间隙：加*vertical-align：top；

8、两个浮动元素中间有注释或内联元素并且和腹肌宽度相差不超过3px时，导致多复制一个文字：避免条件发生；

9、父级元素的overflow：hidden时，包不住子级的relative：加position：relative给父级；

10、父级元素是奇数，绝对定位的元素的right和bottom值会有1px的偏差：不用奇数；

11、绝对定位元素和浮动元素并列绝对定位元素消失：不并列；

12、input空隙：加*float：left给input元素；

13、PNG-24兼容性问题；

解决方案一：引入js插件（不能处理body上的图片）；

解决方案二：原生滤镜filter；