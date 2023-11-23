# MemosSync插件同步问题解决

我现在的笔记流程中用于记录闪念笔记的方式是通过在 nas 上面自建 Memos 的方式
界面是这样的：
![[自建Memos界面.png]]

这个自建 memos 不仅可以网页访问，iPhone 和 Android 端也有一个名叫 MoeMemos 的 APP，所以随身记录非常方便。

那么接下来的一个需求就是通过 memos 本身的 api 同步到 Obsidian

我在 memos 的 tg 群中得到了两个方案，一个是 Obsidian 的第三方插件 [Memos Sync](https://github.com/hyoban/obsidian-memos-plugin)，另外一个就是叫做 [Kirika](https://github.com/hyoban/kirika/releases) 的桌面客户端（包括 pc 和 mac），我选择了比较方便的 OB 插件版本，一开始使用很正常，能导入类似下面这样的一条记录一个文件的形式
![[MemosSync导入文件截图.png]]

但更新了一个 OB 版本之后我遇到了这个问题：unable to verfy the first certificate
![[MemosSync同步问题.png]]
在咨询了插件作者之后，发现不是插件本身的问题，而是我的 nas 证书出现了问题
在查询了很多 [^1] 资料之后，我找到了解决方法
![[MemosSync服务器中间证书.png]]
我的服务器证书中未正确发送中间证书，也就是我可以把中间证书直接和服务器证书合并，然后重新上传上去，再重启 nginx 就可以了，尝试了一下确实有作用了，成功同步！
![[MemosSync同步成功.png]]

[^1]: [Error: unable to verify the first certificate. How to fix? | NodeBB Community](https://community.nodebb.org/topic/14920/error-unable-to-verify-the-first-certificate-how-to-fix)
[node.js - Error: unable to verify the first certificate in nodejs - Stack Overflow](https://stackoverflow.com/questions/31673587/error-unable-to-verify-the-first-certificate-in-nodejs)
[nginx 1.18配置有chain中间证书的ssl服务 - 简书](https://www.jianshu.com/p/18decb471817)
