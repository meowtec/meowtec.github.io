---
layout: post
title:  "在网页中播放你的命令行记录"
date:   2016-9-1 11:18:00 +0800
categories: blog
---
在我们做一些技术分享，编写文档、教程时，经常需要对命令行操作进行录制，然后贴到网页上。
一般大家都会使用 GIF 或者视频，而这两者方式要么文件体积较大，要么画质不清晰。
<!--more-->

### ttyrec/ttyplay
ttyrec 是 Linux 保存终端输出流的一个工具，使用它，就可以把终端录制下来。

```tty
src: /static/ttyrecs/tty-intro.rec
```

Mac 下可以使用 homebrew 安装。

```
ttyrec tty-record.rec
```

需要结束时，使用 exit 退出录制

```
exit
```

然后使用 ttyplay 播放。

```
ttyplay tty-record.rec
```

### ttyplayer.js

我基于 xtrem.js 开发了一个网页端的 [ttyplayer.js](https://meowtec.github.io/ttyplayer.js/)，支持暂停和播放速度控制，未来还可能支持播放进度切换。
使用 ttyplayer，读者在观看的时候还可以随时把命令复制出来，非常方便。

项目地址：[https://github.com/meowtec/ttyplayer.js](https://github.com/meowtec/ttyplayer.js)

#### ttyplayer 基本使用
把 dist 目录下的 ttyplayer.min.css 和 ttyplayer.min.js 两个文件引入你的项目，然后初始化播放器：

``` javascript
new TTYPlayer({
  parent: document.getElement('player-parent')
}).load('/your.rec')
```

如果你使用 jekyll 或者其他使用 markdown 写文章的平台，可以再引入 ttyplayer.autoload.js 这个文件，通过下面的语法加载播放器：

<pre>
<code>&#96;&#96;&#96;tty
src: /static/ttyrecs/tty-intro.rec
&#96;&#96;&#96;</code>
</pre>
