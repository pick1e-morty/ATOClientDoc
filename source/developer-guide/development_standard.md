---
layout: wiki
wiki: hexo-ato # 这是项目id，对应 /data/wiki/hexo-stellar.yml
title: 开发规范
---



## 命名规范
* **包名**和**文件名**使用蛇形命名法
* **类**使用大驼峰命名法
* **函数**和**变量**使用小驼峰命名法，与 PyQt 保持一致


## 项目结构

```
ATOClient
├── app
│   ├── ATO.py                  # 程序启动文件
│   ├── main_window             # 主窗体
│   ├── esheet_process_widget   # 表格处理页面组件
│   ├── download_video_widget   # 下载监控页面组件
│   │   └── netsdk              # sdk操作
│   ├── picture_process_widget  # 标记图片页面组件
│   ├── app_setting_widget      # 软件配置更改页面组件
│   ├── QMyALw                  # 4.0版本残留的页面，准备作为ATO Server的核心代码
│   ├── resource                # 程序要用到的图片文件等
│   ├── AppData
│   │   ├──月台配置.xlsx         # 月台对应监控通道配置文件
│   │   └──config.ini           # 窗体配置文件
│   └── utils                   # 综合工具箱，几乎所有窗体都会用到
├── ato_pak.json                # auto_py_to_exe，打包指令配置文件
├── hook.py                     # 打包后第一个要运行的py文件，pyinstaller --runtime-hook 
└── tests                       # 测试
```