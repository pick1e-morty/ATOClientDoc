---
layout: wiki
wiki: hexo-ato # 这是项目id，对应 /data/wiki/hexo-stellar.yml
title: 下载监控页面
---

{% image /resource/下载录像页面.png 下载录像页面截图 fancybox:true %}


# 介绍

目前程序是{% emp beta %}状态，也就是{% emp 公开测试 %}，这意味着程序现在是非稳定运行的状态，所以下载错误的问题可能会些微频繁。还望海涵。



## 设备状态 控件组

### 开始下载 按钮

暂不支持中途停止下载，点击按钮前请仔细考虑。


不出意外的话你应该只能看到程序按照顺序的显示

1. 初始化成功 / 失败
2. 打开日志成功 / 失败
3. 登录成功 / 失败
4. 登出成功 / 失败
5. 关闭日志成功 / 失败
6. SDK释放资源成功 / 失败

上面的6种状态码是由我定义的，也就是在代码确保之内的状态。

{% quot 如果你看到了不是上面六个之一的状态码 icon:default %}

那就大概率跟我的代码没关系了。请自行分辨报错设备的厂家名称，然后在下方导航栏中跳跃至对应的厂商SDK错误定义页面，并查找错误码所代表的含义。


{% navbar active:/123 [点击跳转](/123) [大华网络SDK错误码](/developer-guide/dahua_netsdk_exception) [海康网络SDK错误码](/developer-guide/haikang_netsdk_exception) %}


或者你也可以在 首页 中提到过的 厂商SDK设备操作日志中查询更加详细的情况
```
  ATO
    └─_internal
        └─app
           ├─dh_netsdk_log      # 大华SDK操作日志
           ├─hk_netsdk_log      # 海康SDK操作日志
           └─main.log           # 主程序日志

```

## 下载状态 控件组

这个表格组件最重要的就是最后一列，这一列会具体显示某个文件下载是否成功，如果失败了也会给出错误原因。

常见的三种状态码有

1. 下载成功
2. 下载超时
3. 下载失败

如上所述，如果你看到了不是上面三个之一的状态，请自行分辨报错设备的厂家名称，然后在下方导航栏中跳跃至对应的厂商SDK错误定义页面，并查找错误码所代表的含义。


{% navbar active:/123 [点击跳转](/123) [大华网络SDK错误码](/developer-guide/dahua_netsdk_exception) [海康网络SDK错误码](/developer-guide/haikang_netsdk_exception) %}


或者你也可以在 首页 中提到过的 厂商SDK设备操作日志中查询更加详细的情况
```
  ATO
    └─_internal
        └─app
           ├─dh_netsdk_log      # 大华SDK操作日志
           ├─hk_netsdk_log      # 海康SDK操作日志
           └─main.log           # 主程序日志
```



## 因程序目前还在beta状态，所以下面两个组件都是为了提升下载成功几率所存在的。待程序稳定之后，下面两个组件应该会移除。

### 下载错误/缺失文件 控件组

在文件下载结束之后会扫描 ATO/pic/ 文件夹下的所有文件并保存一份路径副本，然后跟先前从 表格处理 页面中获取到的路径副本做对比，如果路径存在就说明下载成功了，反之。在对比完成之后就会把不存在的路径添加到一个临时变量中，它代表了下载失败的文件都有哪些，最后点击一下重新下载即可。

如果你觉得上面那段文字云里雾里的，也可以直接查看源代码。
{% copy https://gitee.com/picklemorty/ATOClient/blob/master/app/download_video_widget/dvw.py prefix:HTTPS %}

具体到方法名为: def afterDownload(self):



###  文件数量 控件组

实时监控显示 ATO/pic/ 文件夹下以 jpg 和 mp4 为后缀名的文件数量

#### MP4转JPG 按钮

如果你发现 mp4 文件数量列不为0，可以点一下这个按钮。

在文件下载结束之后，程序将自动运行一次本按钮同等代码。
程序会尝试把 ATO/pic/ 文件夹下所有以 mp4 为后缀名的文件转换为 jpg 文件。如果转换失败，会在界面中弹窗显示错误原因。

因为 mp4 转 jpg 的功能都是基于大华 playsdk 所编写的，所以所有的转换错误代码都可以在 大华播放SDK错误码 中查到

{% navbar active:/123 [点击跳转](/123) [大华网络SDK错误码](/developer-guide/dahua_playsdk_exception) %}





#### 删除所有文件 按钮

pass