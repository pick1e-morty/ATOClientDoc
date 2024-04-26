---
layout: wiki
wiki: hexo-ato # 这是项目id，对应 /data/wiki/hexo-stellar.yml
title: 安装及配置
---

ATO Client 使用 Python3 进行开发，基于 PyQt5 构建图形界面，目前提供了免安装版仅需下载压缩包并解压即可立即使用。


## 安装
1. 从 [Release](https://gitee.com/picklemorty/ATOClient/releases/latest) 页面下载 `ATO-v*.*.*_x64_Portable.7z`
2. 解压 `ATO-v*.*.*_x64_Portable.7z`
3. 在解压出来的 `ATO` 文件夹中，找到并双击运行 **ATO.exe**



## 填写设备配置

1. 配置文件路径在ATO-_internal-AppData-月台配置.xlsx
2. 打开后可以看到类似下面的数据


|月台号|设备厂商|IP|通道序号|TCP端口|用户名|密码|
|----|----|----|----|----|----|----|
|YT666|大华|192.66.66.66|32|37777|admin|admin|
|YT233|海康|192.66.66.67|8|8000|admin|admin|


3. 目前仅支持大华和海康两家的设备操作
4. 大华的TCP端口号获取路径在 主页面-左上角管理-网络设置-端口-TCP端口(默认是37777)
5. 如果你的大华HCVR设备系统为4.0版本及以上将支持TCP共用(HTTP)80端口(没看明白可以忽略)
6. 海康的TCP端口号获取路径在 主页面-横幅中的配置-网络-端口-服务端口(即为TCP端口，默认为8000)
7. 用到哪个填写哪个的配置，不用全部填上哈

