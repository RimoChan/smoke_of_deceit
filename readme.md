# 把代码藏起来！

事情是这样的，前几天，我发现我的Vtuber教程仓库里的Markdown渲染不出来了。

当时我以为是GitHub的bug，但是我发现其他的仓库里Markdown渲染就是正常的。于是我对比了一下，才想起我不知道什么时候往这个仓库里塞了一个奇怪的`.gitattributes`。

它的内容是这样的——

```
*.* linguist-language=python
```

也就是说，GitHub在网页上渲染代码时，不仅会根据后缀，也会根据`.gitattributes`的`linguist-language`指示。

这里面显然有一个特例是Markdown，它并不是语义着色，而是把代码编译成HTML……那这样一来，岂不是就可以把代码假装成Markdown，让别人在网页上找不到代码！


## 如何操作


1. 新建一个`.gitattributes`文件，加上一行`*.* linguist-language=Markdown`，把所有代码都变成Markdown。

2. 在你的普通代码中利用神奇的注释操作，让它恰好同时是一个合法的那个原本的语言的文件和一个空的Markdown文件。

具体可以参考`.gitattributes`和`smoke.py`这两个文件。对了，如果你在网页上直接打开`smoke.py`，应该已经看不到里面的代码了，要点raw按钮才能看到。

<sub>(不过我也没想到怎么把开头的`#`去掉……)</sub>


## 用法

没什么用，也许可以骗一骗女生？
