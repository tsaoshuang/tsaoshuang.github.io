# Obsidian dataview 引用本地图片

# Obsidian dataview 引用本地图片
---
事情是这样的：
7 月 13 日我用 douban 插件抓取 Reading 页面书籍封面的时候遇到了无法抓取的问题
我的 yaml 引用图片直接是引用的豆瓣的网络图片，见下图 cover：字段
![[内文yaml.png|200]]
明明豆瓣链接已经抓取到，但是出现了以下图片无法显示的情况（mac 端和 pc 端都是这种情况）
![[内文callout无图片.png|200]]
所以我判断有可能是插件的问题，还有一种最大的可能是豆瓣网站做了站外防盗链措施，我通过浏览器进入抓取的图片网址也无法显示图片，这证明有可能就是豆瓣不定期抽风的问题。
我也联系了 obsidian douban 插件的作者反馈了无法抓取图片并且后台插件无法登录豆瓣的问题，我也抓取了 douban 插件运行时候的日志提示 403 错误。

>![[403错误 (1).png]]
*图片 403 错误*
>![[豆瓣无法登录.png]]
*无法登录豆瓣*

问题无法定位，如果是豆瓣本身的问题更是无法解决了。
所以我想，莫不如我把书库封面里面的网络图片都改为本地图片，或者让我的书库同时支持网络图片和本地图片。
下面是我之前的 dataview 代码，只支持网络图片的显示：
```
table "![](" + cover + ")" as Cover, 
author as "作者",startime as "阅读日期", score as "评分"
from #reading
where contains(type,"book")
where !contains(file.folder, "Extra/Templates")
sort file.ctime desc
```


于是我经过一系列查询，最终在 dataview 文档中找到了解决方案：

```
table embed(link(cover)) ,"![](" + cover + ")" as Cover, 
author as "作者",startime as "阅读日期", score as "评分"
from #reading
where contains(type,"book")
where !contains(file.folder, "Extra/Templates")
sort file.ctime desc
```


利用embed来显示本地图片也是收到了cuman大佬BT示例库的启发
![[Pasted image 20230715111320.png]]
我直接照搬了BT库中的代码发现并没有效果，可能是参数不全的缘故。

查询文档之后发现
![[Pasted image 20230715113406.png|400]]
要在 embed 之后加 (link (cover)) 就像下面这样：
==table embed(link(cover))==
link 参数代表的是要放一个链接，cover 变量引用的是 yaml 里面的 cover 字段后面本地图片路径（相对和绝对路径都可以）类似下图这样：
![[Pasted image 20230715111758.png]]
然后我们就得到了
![[9ac3b168247046cf3db4e03997dbc4b.png|400]]
但是我们会发现图片上方会多出本地图片的名字
![[Pasted image 20230715112317.png|400]]
那是因为我们上面那段 dataview 代码中表单里多了一项本地图片，而我此时是网络图片和本地图片混用的情况，而上方有本地图片名称显示的就是网络图片，这时我们如果有混用需求的话就要去掉上方的名称显示，我想了一个方法，就是加载 css 片段去掉网络图片显示时上方的本地图片名称。
大家可以复制以下代码到 css 片段中加载：
```
/*embed隐藏本地图片名称*/

.cards table.dataview span.internal-embed {

  display: none;

}
  

/*dataview视图 embed隐藏本地图片名称*/

.internal-embed:not(.image-embed) {

  display: none;

}
```

OK，搞定，上面的代码可能应用到不同主题会出现不同的小问题，大家可以在 pkmer 群中反馈。

%%出处
link:: 



%%
