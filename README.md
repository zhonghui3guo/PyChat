PyChat
======

A P2P IM for Gnome3 with chat history, files/images transfer, screenshot and video/voice chat. It's written in Python 2.7.

Dependences:
> Python2.7<br>
> gnureadline<br>
> pycrypto<br>
> pygame<br>
> Gnome3<br>
> gnome-terminal<br>
> gnome-screenshot<br>
> zenity<br>
> wmctrl<br>
> xdotool<br>
> pynotify and [notify-suite][notify-suite]<br>
> libpulseaudio<br>
> speex<br>
> pygtk<br>

Port Bind：63331~63336

这是我为了解决在校园网内Linux下无法和女朋友聊天写了一个小小的IM。主要功能如下：
> 1. 聊天内容及历史记录气泡显示，输入@h或者@history查看历史记录。显示效果并没有使用ncurses，而是自己用console codes写的，如果发现任何bug请联系作者。需要注意的是：Ctrl+C关闭窗口才会保存完整的历史记录，直接点击close窗口按钮会使历史记录丢失，现已关闭窗口的关闭按钮和最大化按钮，阻止调整窗口大小；<br>
> 2. 聊天消息采用udp传送，文件传输、视频聊天和语音聊天采用tcp传送，需要双方均有可互联的IP。聊天消息采用AES加密，消息传送有送达验证，用心跳信号验证网络是否通畅；<br>
> 3. @l或者@leave设置离开状态；@h或者@history查看历史记录；@f或者@file传送文件，可传送多个文件，可选择接受其中部分文件，传输过程以进度条显示；@i或者@image传送图片，与传送文件类似，但是在传输完成后会自动打开，图片存在~/Pictures/PyChat下；@s或者@screenshot屏幕截图并传送，图片存在~/Pictures/PyChat/ScreenShot下；@v或者@video视频聊天，图像尺寸为320x240，需要网速约400KB/s；@y或@yy语音聊天，关闭语音聊天再次输入即可，需要网速50KB/s；<br>
> 4. 新消息到达、未读消息、断线/重连，均会有提示音和系统消息气泡提示，任何严重的异常均会弹错误对话框并致使程序退出，返回码1。<br>

使用前请根据自己使用的是服务端还是客户端来修改desktop文件。

注意：
> 1. 本IM只为一对一聊天设计，如有需求多人聊天，应该很容易修改；<br>
> 2. 偷懒没有做图标，用的cheese的图标，对此表示歉意。使用前请修改desktop文件和代码中图标引用；<br>
> 3. 本来只是个100+行的小东西，不知不觉加了这些，代码相当不规范，且没有注释，不过总计也就1000行，应该还是很好读的；<br>
> 4. 由于没采用配置文件，每次配置修改会直接修改py代码文件，所以如有需要编译成pyc或者pyo，先改客户端mian函数的代码。<br>

最后特别声明，本人不是计算机科班出身，Python真正零基础，不会的全靠文档+谷歌+度娘。做这个IM总计耗时也没过50小时，如果觉得东西写的丑，帮忙重写的感激不尽。

Any problem, please mail to <guangmuzhu@gmail.com>.

[notify-suite]:https://github.com/guangmuzhu/notify-suite
