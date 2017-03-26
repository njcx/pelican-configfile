Title:  X、X11、Xfree86、Xorg、GNOME、KDE之间的关系
Date: 2017-03-25 10:20
Modified: 2017-03-25 10:20
Category: Linux
Tags: linux, xorg
Slug: my-super-post
Authors: nJcx
Summary: linux 详解
##第一篇测试

一、linux本身没有图形界面，linux现在的图形界面的实现只是linux下的应用程序实现的。
二、X是协议，不是具体的某个软件。
三、X和XFree86的关系.
有了协议就需要具体的软件来实现这个协议.实现X协议的软件也并不只有 XFree86，XFree86只是实现X协议的一个免费X服务器软件.商业上常用MOTIF，现在还有XORG，还有很多很小的由爱好者写的小的X服务 器软件.
四、X和X11R6又是什么关系?

协议版本和实现协议的软件的版本

五、X服务器和WM(window manager 窗口管理器)之间是什么关系.

窗口管理器的作用就是最大化，最小化，移动，关闭窗口等.而这些不是X服务器来负责完成的.

六、关于KDE和GNOME

KDE 和GNOME是LINUX里最常用的图形界面操作环境，他们不仅仅是一个窗口管理器那么简单， KDE是K Desktop Environment 的缩写.他不仅是一个窗口管理器，还有很多配套的应用软件和方便使用的桌面环境，比如任务栏，开始菜单，桌面图标等等.

GNOME是GNU Network Object Model Environment 的缩写.和KDE一样，也是一个功能强大的综合环境.

另外在其它UNIX系统中，常常使用CDE作为这样一个环境.

其它的小型窗口管理器有:
window maker，after step，blackbox，fvwm，fvwm2，等等都是常用的优秀窗口管理器.REDHAT9中有 window maker 但是默认不安装，大家可以装来试试.只要xinit再wmaker&就可以用windowmaker了.

七、linux图形界面层次关系总结

linux本身-->X服务器<-[通过X协议交谈]->窗口管理器(综合桌面环境)-->X应用程序.

Xfree86服务器的实现包括两个部分，一部分是和显卡直接打交道的低层，一部分是和X应用程序打交道的上层。上层负责接收应用程序的请求和鼠标 键盘的动作。而和显卡直接打交道的底层负责指挥显卡生成图形，其实就是显卡驱动。上层接收到应用程序的请求后，将请求内容做适当处理，然后交给显卡驱动来 指挥 显卡完成画图的动作.另外，上层的捕捉键盘和鼠标动作的部分会向应用程序提供鼠标和键盘的状态信息，应用程序接收到这些信息后决定是否再有相应的动作.

平时说的VESA，VGA ，fbdev等其实就是针对不同模式显卡的驱动程序.
VESA(Video Electronics Standards Association)
VGA (Video Graphics Array)
fbdev (FrameBuffer Device)
等

linux字符界面在高分辨率下，启动时会有一个小企鹅logo，这个logo就是用framebuffer功能写上屏幕的.
