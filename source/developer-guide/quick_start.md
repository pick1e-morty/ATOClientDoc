---
layout: wiki
wiki: hexo-ato # 这是项目id，对应 /data/wiki/hexo-stellar.yml
title: 快速上手
---

## 搭建开发环境

1. 创建虚拟环境:

{% box child:codeblock color:green %}
```
conda create -n ato_env python=3.8
conda activate ato_env
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
```
{% endbox %}

其中 unifynetsdk 模块需要从 https://gitee.com/picklemorty/UnifyNetSDK/releases 中手动下载并安装


2. 打开开发模式标志变量:

在app/utils/project_path.py文件中有一个DEBUG变量需要设置为True


3. 运行 ATO Client:
   
{% box child:codeblock color:green %}
```
cd app
conda activate ato_env
python ATO.py
```
{% endbox %}

