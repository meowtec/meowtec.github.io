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

<div
  class="player-container"
  data-termplayer-source="/static/ttyrecs/tty-intro.rec"
>
</div>

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
使用 ttyplayer，读者在观看的时候还可以随时把命令复制出来，很方便。

想知道使用方式，看这个网页的源码，或者[项目源码](https://github.com/meowtec/ttyplayer.js)就 OK.