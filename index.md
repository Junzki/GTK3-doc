---
layout: page
title: "GTK+ 3 Chinese Reference Manual"
tagline: Supporting tagline
---
{% include JB/setup %}

**注意： 最后更新于2014/11/2, 目前网站正在建设中，全站内容仅为测试页面所用。**

---

##GTK+ 3中文参考手册

###前言

该参考手册适用于GTK+3的3.14.1版本，最新版本的参考手册可以去[这里](http://developer.gnome.org/gtk3/)在线查看。如果你在寻找GTK2的手册，可以移步到[这里](http://developer.gnome.org/gtk2/)查看。

###第一章 GTK+概览

GTK+是用来创造图形界面的库，它可以运行在许多类UNIX系统，Windows和OS X。GTK+按照GNU LGPL许可证发布，这个许可证对程序来说相对宽松。GTK+有一个基于C的面向对象的灵活架构，它有对于许多其他语言的版本 ，包括C++，Objective-C， Guile/Scheme, Perl, Python, TOM, Ada95, Free Pascal和Eiffel。
GTK+依赖于以下库：

>*    GLib
A general-purpose utility library, not specific to graphical user interfaces. GLib provides many useful data types, macros, type conversions, string utilities, file utilities, a main loop abstraction, and so on. 
>*    GObject
A library that provides a type system, a collection of fundamental types including an object type, a signal system. 
>*    GIO
A modern, easy-to-use VFS API including abstractions for files, drives, volumes, stream IO, as well as network programming and DBus communication.
>*    cairo
Cairo is a 2D graphics library with support for multiple output devices. 
>*    Pango
Pango is a library for internationalized text handling. It centers around the PangoLayout object, representing a paragraph of text. Pango provides the engine for GtkTextView, GtkLabel, GtkEntry, and other widgets that display text. 
>*    ATK
ATK is the Accessibility Toolkit. It provides a set of generic interfaces allowing accessibility technologies to interact with a graphical user interface. For example, a screen reader uses ATK to discover the text in an interface and read it to blind users. GTK+ widgets have built-in support for accessibility using the ATK framework. 
>*    GdkPixbuf
This is a small library which allows you to create GdkPixbuf ("pixel buffer") objects from image data or image files. Use a GdkPixbuf in combination with GtkImage to display images. 
>*    GDK
GDK is the abstraction layer that allows GTK+ to support multiple windowing systems. GDK provides window system facilities on X11, Windows, and OS X. 
>*    GTK+
The GTK+ library itself contains widgets, that is, GUI components such as GtkButton or GtkTextView. 


####第一节 开始使用GTK+

这一节包括一些帮助你开始学习GTK+编程的教程。该节假设你已经安装好了GTK+，依赖库和C编译器[^1]。如果你需要编译GTK+本身，查看手册中编译GTK+的部分。

[^1]:此意即为在Windows下配置GTK+3的开发环境，方法见附录1

```c
/* hello world demo */
#include <stdio.h>
int main(int argc, char **argv)
{
    printf("Hello, World!\n");
    for(int i=2;i<2;i++)
    {
        printf("hi");
    }
    return 0;
}
```

###附录1 在Windows下配置GTK+3的开发环境

这是我进行配置的经验，环境为Windows8.1。因为可选择的开发工具众多，配置有所差异，下面的配置过程仅供参考。
必须安装的工具有：C编译器，GTK+及其依赖库。安装步骤如下：

####安装集成开发环境Code::blocks

GTK+不像Qt，没有自己专门的集成开发环境(IDE)，这一直饱受诟病。目前跨平台较好的IDE中，Code::blocks对GTK+支持较好，所以我选用Code::blocks。
从官网上找到系统对应的版本，在Windows下，最好选择with Mingw的版本(Mingw为C编译器),然后安装即可。如果不喜欢英文界面，可以搜索汉化包放在指定路径使界面显示为中文，不过汉化不完全，还是习惯英文界面吧。

**注意：**这一步实际上安装了编辑器，编译器，调试器等核心组件。不喜欢IDE的可以使用自己的Vim，Emacs编辑器等，添加C编译器和调试器(推荐Mingw)。

####安装GTK+

在Windows下，GTK+的安装参照官网方法：
本机为32bit，首先[下载GTK+的All in bundle](http://www.gtk.org/download/win32.php)，然后解压到某目录，比如`C:\GTK\GTK3`下，即可将GTK+及其依赖库安装完成。

####配置环境变量

将`C:\GTK\GTK3\bin`添加到系统的环境变量Path中，如下图：

![Screenshot](/assets/images/set_path.png)

