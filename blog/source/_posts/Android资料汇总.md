---
title: Android资料汇总
date: 2017-08-22 16:57:59
type:
top:
comments:
categories: [工具资源, 资源, Android]
tags: [Android, 资料]
copyright:
reward:
---


## 插件

- **[android-selector](https://github.com/importre/android-selector-intellij-plugin)**
可以根据指定颜色生成 Selector Drawable 的插件

- **[GradleDependenciesHelperPlugin](https://github.com/siosio/GradleDependenciesHelperPlugin)**
Gradle 依赖自动补全插件

<!--more-->

- **[GsonFormat](https://github.com/zzz40500/GsonFormat)**
根据JSONObject格式的字符串,自动生成实体类参数

- **[Android Drawable Importer](https://github.com/winterDroid/android-drawable-importer-intellij-plugin)**
图标快捷批量导入

- **[AndroidWiFiADB](https://github.com/pedrovgs/AndroidWiFiADB)**
使用 WiFi 连接而不需要 USB 连接 Android 设备达到安装, 运行, 调试应用的目的

- **[adb-idea](https://github.com/pbreault/adb-idea)**
支持直接在AS面板中进行ADB操作,快捷键: * Mac OSX: Ctrl+Shift+A * Windows/Linux: Ctrl+Alt+Shift+A

- **[Android Methods Count](https://plugins.jetbrains.com/plugin/8076-android-methods-count)**
统计 Android 依赖库中方法的总个数, 避免应用方法数超过 65K 问题

- **[ButterKnife Zelezny](https://github.com/avast/android-butterknife-zelezny)**
ButterKnife是一个专注于Android系统的View注入框架,可以减少大量的findViewById以及setOnClickListener代码，可视化一键生成

- **[Android Parcelable code generator](https://github.com/mcharmas/android-parcelable-intellij-plugin)**
Android中的序列化有两种方式, 分别是实现 Serializable 接口和 Parcelable 接口, 但在 Android 中是推荐使用 Parcelable, 只不过我们这种方式要比Serializable方式要繁琐, 那么有了这个插件一切就ok了

- **[40个常用插件](https://ydmmocoo.github.io/2016/06/28/Android-Studio%E6%8F%92%E4%BB%B6%E6%95%B4%E7%90%86/)**

## 工具

- **[jadx](https://github.com/skylot/jadx)**
一个 Android 反编译神器, 不同于常见的 dex2jar, 这个反编译器生成代码的 try/catch 次数更少, View也不再是数字 id 了, 可读性更高

- **[Smali Viewer](http://blog.avlyun.com/show/%E3%80%8Asv%E7%94%A8%E6%88%B7%E6%8C%87%E5%8D%97%E3%80%8B/)**
sv 是一款免费 APK 分析软件, 对你感兴趣的 APP 分析看看它们都用了些什么, 对你学习借鉴有一定帮助

- **[Stetho](http://facebook.github.io/stetho/)**
Stetho 是 Facebook 出品的一个强大的 Android 调试工具,使用该工具你可以在 Chrome Developer Tools 查看 App 的布局, 网络请求(仅限使用 Volley, okhttp 的网络请求库), sqlite, preference, 一切都是可视化的操作,无须自己在去使用 adb, 也不需要 root 你的设备

- **[checkstyle-idea](https://github.com/jshiell/checkstyle-idea)**
Checkstyle-idea 是一款检查自己写的代码是否符合规范的插件, 该插件是根据 checkstyle.xml 文件来检查的, checkstyle.xml 文件可以由自己自己定义, 也可以使用一些大公司定义的规范, 如果不懂得如何定义, 可以查看 [官方文档](http://checkstyle.sourceforge.net/checks.html), 该插件的详细介绍以及使用, 可以看一下咕咚大侠写的 [文章](http://gudong.name/2016/04/07/checkstyle.html)

- **[LeakCanary](https://github.com/square/leakcanary)**
良心企业 Square 最近刚开源的一个非常有用的工具, 强烈推荐, 帮助你在开发阶段方便的检测出内存泄露的问题, 使用起来更简单方便, 而且我们团队第一时间使用帮助我们发现了不少问题, 英文不好的这里有雷锋同志翻译的中文版 [LeakCanary 中文使用说明](https://www.liaohuqiu.net/cn/posts/leak-canary-read-me/)

## 库

### 资源汇总库

- **[awesome-android-libraries](https://github.com/wasabeef/awesome-android-libraries)**
各种android库，包括网络，图片加载，日志，相机，多媒体等等

- **[views](https://github.com/madongqiang2201/views)**
Android酷炫自定义控件(View)汇总

- **[android-open-project](https://github.com/Trinea/android-open-project)**
各种开源库

- **[awesome-android-ui](https://github.com/wasabeef/awesome-android-ui)**
android UI/UX 汇总库

- **[Android_Data](https://github.com/Freelander/Android_Data)**
android各种资源汇总

- **[Android-Dev-Favorites](https://github.com/ruijun/Android-Dev-Favorites)**
Android开发者的收藏夹

### 资源细分库

- **[okhttp-OkGo](https://github.com/jeasonlzy/okhttp-OkGo)**
OkHttpUtils-2.0.0升级后改名OkGo，全新完美支持RxJava，比Retrofit更简单易用。该库是封装了okhttp的标准RESTful风格的网络框架，支持大文件上传下载，上传进度回调，下载进度回调，表单上传（多文件和多参数一起上传），链式调用，可以自定义返回对象，支持Https和自签名证书，支持超时自动重连，支持cookie的持久化和自动管理，支持五种缓存模式缓存网络数据，支持301和302重定向，扩展了统一的上传管理和下载管理功能

- **[Curzibn/Luban](https://github.com/Curzibn/Luban)**
Luban，也称鲁班。该库作者一针见血的提出当前图片压缩处理的一些问题：单纯对图片进行裁切，压缩已经有很多文章介绍。但是裁切成多少，压缩成多少却很难控制好，裁切过头图片太小，质量压缩过头则显示效果太差。所以，他通过微信朋友圈发送近100张不同分辨率图片，对比原图与微信压缩后的图片逆向推算出来的压缩算法，具体的算法实现在项目中有详细说明介绍。使用上，支持普通调用方式外，也支持RxJava！

- **[Compressor](https://github.com/zetbaitsu/Compressor)**
它可以满足动则几MB的图片高保真的压缩到几十KB的效果。

- **[android-viewbadger](https://github.com/jgilfelt/android-viewbadger)**
消息数目小红点

- **[PagerBottomTabStrip](https://github.com/tyzlmjj/PagerBottomTabStrip)**
PagerBottomTabStrip 是一个基本按谷歌Material Design规范完成的安卓底部导航栏控件

- **[PhotoEdit](https://github.com/jarlen/PhotoEdit)**
图片编辑处理（添加文字，涂鸦，马赛克等等）

- **[sweet-alert-dialog](https://github.com/pedant/sweet-alert-dialog)**
优美的对话框样式

- **[BannerLayout](https://github.com/dongjunkun/BannerLayout)**
简洁实用的自动轮播广告栏

- **[RecyclerViewCardGallery](https://github.com/huazhiyuan2008/RecyclerViewCardGallery)**
RecyclerView实现Card Gallery效果，替代ViewPager方案

- **[FantasySlide](https://github.com/mzule/FantasySlide)**
一个 DrawerLayout的扩展,具有帅气的动画与创新的交互。一次手势完成滑出侧边栏与选择菜单

- **[CommentListTextView](https://github.com/hnsugar/CommentListTextView)**
一个TextView实现朋友圈多条评论效果 朋友圈 微博 评论 comment

- **[ImagePicker](https://github.com/martin90s/ImagePicker)**
选择头像，选择多张图，支持超大图片

- **[CircleImageView](https://github.com/hdodenhof/CircleImageView)**
圆形头像库

- **[NineGridView](https://github.com/jeasonlzy/NineGridView)**
类似QQ空间，微信朋友圈，微博主页等，展示图片的九宫格控件，自动根据图片的数量确定图片大小和控件大小，使用Adapter模式设置图片，对外提供接口回调，支持任意的图片加载框架,如 Glide,ImageLoader,Fresco,xUtils3,Picasso 等，支持点击图片全屏预览大图。

- **[ImagePicker](https://github.com/jeasonlzy/ImagePicker)**
完全仿微信的图片选择，并且提供了多种图片加载接口，选择图片后可以旋转，可以裁剪成矩形或圆形，可以配置各种其他的参数

- **[material-icon-lib](https://github.com/code-mc/material-icon-lib)**
Material风格矢量图标库

- **[Android-skin-support](https://github.com/ximsfei/Android-skin-support)**
Android换肤框架

- **[AndroidUtils](https://github.com/WuXiaolong/AndroidUtils)**
Android常用工具类

- **[BaseRecyclerViewAdapterHelper](https://github.com/CymChad/BaseRecyclerViewAdapterHelper)**
一个强大并且灵活的RecyclerViewAdapter

- **[logger](https://github.com/orhanobut/logger)**
简单，漂亮和强大Log日志

## 模拟器相关

- **国内安卓模拟器连接端口**

逍遥模拟器127.0.0.1:21503

夜神模拟器127.0.0.1:62001


## 学习资源

- <http://www.jianshu.com/p/5d26ae5e03f9>
- <https://github.com/suzeyu1992/repo>
- <https://github.com/android-cn/android-dev-cn> 国内开发者信息
