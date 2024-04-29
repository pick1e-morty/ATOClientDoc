---
layout: wiki
wiki: hexo-ato # 这是项目id，对应 /data/wiki/hexo-stellar.yml
title: 首页
---





<style>
#index_h1 {
  text-align:center;
  font-size: 24px;
}
#dec {text-align:center;}

.info {
    display: flex;
    justify-content: center;
}

.info img {
    margin: 0 10px;
    width: 15%;
    object-fit: cover;
}
</style>


<p id="logo">
<img width="25%" align="center" src="../resource/logo.png" alt="logo">
</p>

<p id=index_h1>
ATO Client
</p>



------


<p id="dec">
  一个快速监控取证的工具
</p>


<div class="info">

<img src="https://img.shields.io/badge/Python-3.8.18-blue.svg?color=00B16A" alt="Python 3.8.18"/>

<img src="https://img.shields.io/badge/PyQt-5.15.10-blue?color=00B16A" alt="PyQt 5.15.10"/>

<img src="https://img.shields.io/badge/Platform-Win64-blue?color=00B16A" alt="Platform Win64"/>

</div>



## 重要文件目录结构

```
  ATO
    ├─ATO.exe                   # 启动程序
    ├─pic                       # 图片下载及处理文件夹
    └─_internal
        ├─app
        │  ├─dh_netsdk_log      # 大华SDK操作日志
        │  ├─hk_netsdk_log      # 海康SDK操作日志
        │  └─main.log           # 主程序日志
        ├─AppData
        │  ├─config.ini         # 界面配置文件
        │  └─月台配置.xlsx       # 月台对应监控通道配置文件
        │
        └─UnifyNetSDK           # 统一厂商SDK接口的模块
           ├─dahua              # 如果你也有兴趣开发类似的项目可以看看
           └─haikang            # 项目地址:https://gitee.com/picklemorty/UnifyNetSDK

```

------


## 界面预览

{% swiper width:max %}

{% image ../resource/表格处理页面.png 表格处理页面截图 fancybox:true %}
{% image ../resource/下载录像页面.png 下载录像页面截图 fancybox:true %}
{% image ../resource/标记图片页面.png 标记图片页面截图 fancybox:true %}

{% endswiper %}



## ATO Client | ATO5 | v1.0.0 这些英文字符都是什么含义？

ATO Client 是这个代码项目的命名，其中Client是名副其实的客户端的意思。不过服务端可能还要等好久，计划是服务端运行一个yolo，可以自动标记图片。

ATO5 是这个软件的logo，其中5 的含义是这个项目已经 经过5次技术迭代了(高情商)。

v1.0.0 讲明白了上面那些，最后这个就是软件版本号了，ATO经过5次技术迭代的第一个版本。
