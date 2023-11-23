# Prism主题高亮样式通用CSS片段

有一天看群友对 Prism 主题的高亮样式感兴趣了，当时有时间就去 Prism 主题的 [项目主页](https://github.com/damiankorcz/Prism-Theme) 逛了逛，顺便把它的高亮样式移植了下来。
Prism 主题的高亮样式长这样：
![[Prism主题高亮样式-1.png]]
在 Prism 主题中高亮的用法是这样的：

```code
<mark class="mint mark-filled mark-text-color">This highlighted text is Mint</mark>
```

可以用以下参数
边框背景参数：
- mark-default
- mark-border
- mark-filled
- mark-borderandfilled
字体样式参数
- mark-text-default
- mark-text-color
替换上面案例代码中的的 class 中的内容，以显示不同高亮效果

我觉得这种方法比较麻烦，所以在 CSS 片段中加入了 StyleSetting 设置选项，直接可以在设置中设置高亮的样式，只不过是全局通用样式，而不是针对某个高亮单独设置样式

![[Prism主题高亮样式设置.png]]

效果是这样的
![[Prism高亮设置.gif]]
将以下片段放入到 ob 库的. obsidian/snippets 文件夹中，然后加载此 CSS 片段就可以了

[Prism Mark Highlight System.css]( https://www.aliyundrive.com/s/Xffysji3Fef )
提取码: zk95
