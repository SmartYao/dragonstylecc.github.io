---
title: Android Studio个人设置
categories:
  - Android
tags:
  - Android
  - Android studio
abbrlink: 624209520
date: 2017-09-06 17:21:59
type:
top:
comments:
copyright:
reward:
---


> Android Studio 的个人设置只是在初次安装的时候会根据个人喜好配置，每当换电脑或者重搭开发环境时都要重新设置，因为设置项很多，所以配置起来很麻烦，而且网上找的资料不一定全，好在 Android Studio 为我们提供了非常方便的导入导出设置功能。不过有时候导入导出还是会有异常，比如这次我将 AS 2.3 的配置导入到 AS 3.0的时候就出现了很多毛病，所以写这篇日志方便自己以后手动配置。

# 修改缓存文件位置

修改 Android Studio 根目录下 `bin\idea.properties `
（找到要修改的选项，去掉前面的#，也就是注释符号，然后修改后面的配置路径）。
```java
idea.config.path=D:\.AndroidStudio\config

idea.system.path=D:\.AndroidStudio\system

idea.plugins.path=D:\AndroidStudio\plugins

idea.log.path=D:\.AndroidStudio\system\log
```
<!--more-->
在gradle的安装目录，编辑 `bin\gradle` 文件，然后找到如下语句:
```
# Add default JVM options here. You can also use JAVA_OPTS and GRADLE_OPTS to pass JVM options to this script
```
在这句话的下面加上如下这一句:
```
GRADLE_OPTS=-Dgradle.user.home=/yourpath/gradle/gradle_cache
```

# 常用设置

## 导入导出配置包
我通常都是将我的配置包以时间命名放在云盘上。
![](http://ov11eqxw3.bkt.clouddn.com/0daoru.jpg/water.jpg)

## 配置黑色主题和菜单栏的字体和大小

![](http://ov11eqxw3.bkt.clouddn.com/1zhuti.jpg/water.jpg)

## 导入第三方主题
和导入配置的方式一样，该[主题](http://color-themes.com/?view=index)网站提供了各种各样IDE的主题样式。
> 上面网站下的主题我发现有时候注解的字体颜色很难辨认，所以我用的自带主题。

## 配置代码编辑区域字体和大小
![](http://ov11eqxw3.bkt.clouddn.com/2bianji.jpg/water.jpg)

## 配置控制窗口区域字体和大小
和上面配置代码编辑区一样，只是选择 Console Font 选项。

## 设置关闭自动更新
取消勾是关闭自动更新，但是本人喜欢去尝试新版本踩坑，所以没关闭自动更新。
![](http://ov11eqxw3.bkt.clouddn.com/3update.jpg/water.jpg)

## 设置关闭大小写敏感配置
设置为None是关闭大小写敏感，即代码提示时不区分大小写。
![](http://ov11eqxw3.bkt.clouddn.com/4daxiaoxie.jpg/water.jpg)

## 设置自动导包
两个勾都要打上。
![](http://ov11eqxw3.bkt.clouddn.com/5import.jpg/water.jpg)

## 设置代码行数显示
我现在用的新版本貌似默认勾选了的。
![](http://ov11eqxw3.bkt.clouddn.com/6line.jpg/water.jpg)

## 设置文件默认编码方式UTF-8
![](http://ov11eqxw3.bkt.clouddn.com/7encoding.jpg/water.jpg)

## 设置新建文件头
根据自己情况修改红框内容，不需要就直接删掉内容。
![](http://ov11eqxw3.bkt.clouddn.com/8header.jpg/water.jpg)

## 设置AS打开引导
设置AS打开后自己选择工程进入，禁止自动打开上次工程
![](http://ov11eqxw3.bkt.clouddn.com/9start.jpg/water.jpg)

## 禁止代码折叠
默认这三个选项是勾选上的，如果要禁止代码折叠，则需要取消这三处勾选。
![](http://ov11eqxw3.bkt.clouddn.com/10code.jpg/water.jpg)

## 取消快速运行Instant Run
默认是勾选的，取消掉。
![](http://ov11eqxw3.bkt.clouddn.com/11insrun.jpg/water.jpg)

## 驼峰选择
Android 开发中，我们通常会使用驼峰命名法对变量进行命名，但是当我们通过 Ctrl + Left / Right 键改变字符选择区域的时候 Android Studio 默认不支持‘驼峰’单词的选择。
![](http://ov11eqxw3.bkt.clouddn.com/12camelhumps.jpg/water.jpg)

## 命名前缀
我们通常会遵循 Android 官方关于编码风格的指导来进行字段命名。在 Android 源码中我们可以看到通常成员变量都是以‘m’开始。其实Android Studio 可以自动在帮我们生成字段名称的时候加上自定义的前缀，如:

- 非共有，非静态的成员变量以’m’开始
- 静态成员变量以’s’开始

![](http://ov11eqxw3.bkt.clouddn.com/13codestyle.jpg/water.jpg)

## 配置Log颜色
Android Studio自带主题Log显示颜色比较单一，可以自己配色。如果是第三方主题，先取消勾选 Use inherited attributes，然后就可以为各种级别设置颜色。推荐颜色设置：
```java
Assert:     #AA66CC
Debug:      #33B5E5
Error:      #FF4444
Info:       #99CC00
Verbose:    #FFFFFF
Warning:    #FFBB33
```
![](http://ov11eqxw3.bkt.clouddn.com/14logcolor.jpg/water.jpg)

## 设置SDK和JDK路径
一次选择选择菜单 File | Other Settings | Default Project Structures...
![](http://ov11eqxw3.bkt.clouddn.com/16sdkjdk.jpg/water.jpg)

## 工程模板
Android Studio 创建 Module 时并没有将 Android 开发中常用的文件目录全部生成，比如默认只生成了一个 drawable 文件夹，常用的 drawable-hdpi 等文件夹需要我们自己创建。

**配置方法1**

- 进入 Android Studio 安装目录
- 依次进入 plugins | android | lib | templates | gradle-projects | NewAndroidModule | root | res
- 在res文件夹下创建 drawable-hdpi 等文件夹(可选：从对应的 mipmap 文件夹中拷贝 iclauncher.png 到创建的 drawable文件夹中)
- 回到 NewAndroidModule 目录，用编辑器打 recipe.xml.ftl文件 加入以下配置
![](http://ov11eqxw3.bkt.clouddn.com/15module1.jpg/water.jpg)

**配置方法2**

- 进入 Android Studio 安装目录
- 依次进入 plugins | android | lib | templates | gradle-projects | NewAndroidModule
- 用编辑器打开 recipe.xml.ftl文件，并加入以下配置
![](http://ov11eqxw3.bkt.clouddn.com/15module2.jpg/water.jpg)

这两种方法的区别是，第一种方式可以在文件夹中加入相应的图片，但是配置稍显繁琐，第二种方式配置简单，但是只能创建目录，不能包含默认图片。

当然，通过类似的方式我们还可以在创建 Module 的时候做很多事情，比如：

- 在 colors.xml 文件中生成常用颜色
- 在 build.gradle 文件中生成自定义配置
- 在 .gitignore 文件中生成自定义忽略配置
- 等等…

## 活动模板
Android Studio 中默认提供了很多非常方便的活动模板(Live Templates)，例如，我们输入 sout 后按 enter 键， Android Studio 会自动帮我们写入 System.out.println();
![](http://ov11eqxw3.bkt.clouddn.com/sout.gif/water)

其实 sout 就是 AS 自带的一个活动模板。
![](http://ov11eqxw3.bkt.clouddn.com/17sout.jpg/water.jpg)
由此可以看出，活动模板就是我们常用代码的一个缩写。开发中有很多代码都会重复出现，因此自定义合适的活动模板能很大程度上避免我们很多重复的体力劳动。所以我们熟悉这些自带的活动模板还是能提高搬砖效率的，至于如何自定义依葫芦画瓢就行了，实在不行网上教程也挺多的。

# 安装常用插件

**[ButterKnife Zelezny](https://github.com/avast/android-butterknife-zelezny)**
专注于Android系统的View注入框架,可以减少大量的findViewById以及setOnClickListener代码，可视化一键生成
> 要配合 com.jakewharton:butterknife:8.8.1 依赖库使用，把该库添加到 build.gradle 脚本里即可。

**[GsonFormat](https://github.com/zzz40500/GsonFormat)**
根据JSONObject格式的字符串,自动生成实体类参数。

使用方法：快捷键Alt+S也可以使用Alt+Insert选择GsonFormat

**[android-selector](https://github.com/importre/android-selector-intellij-plugin)**
可以根据指定颜色生成 Selector Drawable 的插件

**[Android Code Generator](https://github.com/tmorcinek/android-codegenerator-plugin-intellij)**
根据布局文件快速生成对应的Activity，Fragment，Adapter，Menu。

**[Android Parcelable code generator](https://plugins.jetbrains.com/plugin/7332-android-parcelable-code-generator)**
JavaBean序列化，快速实现Parcelable接口。

**[Android Drawable Importer](https://github.com/winterDroid/android-drawable-importer-intellij-plugin)**
图标快捷批量导入

**[Android Methods Count](https://plugins.jetbrains.com/plugin/8076-android-methods-count)**
显示依赖库中得方法数（AS 3.0 不可用）

**[Android WiFi ADB](https://github.com/pedrovgs/AndroidWiFiADB)**
使用 WiFi 连接而不需要 USB 连接 Android 设备达到安装, 运行, 调试应用的目的

**[ADB idea](https://github.com/pbreault/adb-idea)**
支持直接在AS面板中进行ADB操作,快捷键: * Mac OSX: Ctrl+Shift+A * Windows/Linux: Ctrl+Alt+Shift+A

**[Lifecycle Sorter](https://plugins.jetbrains.com/plugin/7742-lifecycle-sorter)**
可以根据Activity或者fragment的生命周期对其生命周期方法位置进行先后排序，快捷键Ctrl + alt + K
