# Obsidian图片增强插件——Awesome image obsidian


# Obsidian 图片增强插件——Awesome image obsidian

```ad-info
title:插件信息
插件名称：Awesome image obsidian 
插件作者：AwesomeDog
插件说明：提供笔记中查看图片的基本操作
插件项目地址：[点我跳转](https://github.com/AwesomeDog/obsidian-awesome-image)
```

Awesome image 其实是在 Image Tookit 的基础上魔改的插件，所以魔改的话就是建立在 Image Tookit 已有的核心功能基础上增加或优化了一些功能，我们这里就先简要介绍它的基础功能，就不展开说了
![[Pasted image 20230730095142.png]]

这两个插件的主要功能就是上面的这条工具栏，它是一个图片增强插件，你在 ob 打开图片之后会看见这个工具条
第一个按钮：缩放至 100%
第二个按钮：放大图片
第三个按钮：缩小图片
第四个按钮：全屏
第五个按钮：刷新
第六个按钮：向左旋转
第七个按钮：向右旋转
第八个按钮：水平翻转
第九个按钮：垂直翻转
第十个按钮：图片反色
第十一个按钮：复制图片到剪贴板

详细说明可以参照 [Obsidian 插件：Image toolkit 提供笔记中查看图片的基本操作](https://pkmer.cn/Pkmer-Docs/10-obsidian/obsidian%E7%A4%BE%E5%8C%BA%E6%8F%92%E4%BB%B6/obsidian-image-toolkit/)。

这里着重说 Awesome image 和 Image Tookit 区别的地方
![[Pasted image 20230730101202.png]]
就是上面图片的这四个功能
1. **On paste processing** （开启粘贴图片时的功能）
	- 这个选项默认是关闭的，你如果想要使用下面三个功能，那一定要把这个选项开启 ![[Pasted image 20230730103156.png]]
2. **Ignore folders**（排除的文件夹）
	- 这个选项是可以排除一些像. obsidian 一样的隐藏的功能性或一些你不想被此插件功能影响的文件夹，这里面填写的文件夹不受此插件影响，包括搜索和重命名。填写的时候每一行填写一个文件夹
3. **Include**（包含的文件）
	- 这个选项可以限定此插件影响的文件名称，这里可以用正则表达式填写文件名称，包括文件名和后缀，如果你想让此插件影响特定的文件类型或文件名可以使用此功能结合正则表达式来限定
4. **Media folder**（图片保存文件夹）
	- 这个选项是让我们设置图片的保存的文件夹的，你可以手动新建一个文件夹然后在此填写具体路径，也可以使用插件默认设置，如果使用默认设置，在你粘贴图片时，插件会自动新建一个 assets/img 目录用于保存本地图片

以下功能是和 Image Tookit 完全一样的可以参照 [Obsidian 插件：Image toolkit 提供笔记中查看图片的基本操作](https://pkmer.cn/Pkmer-Docs/10-obsidian/obsidian%E7%A4%BE%E5%8C%BA%E6%8F%92%E4%BB%B6/obsidian-image-toolkit/)。
Awesome image：
![[Pasted image 20230730095142.png]]
![[Pasted image 20230730095205.png]]
![[Pasted image 20230730095221.png]]
![[Pasted image 20230730095242.png]]

