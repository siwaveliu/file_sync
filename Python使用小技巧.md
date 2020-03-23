---
title: Python使用小技巧
tags: Python,pip,安装
grammar_cjkRuby: true
---

# 给不同版本的Python安装pip install
- 先cd到对应python目录
- 然后使用 *python -m pip install numpy* # 此时python不能表示其它版本——被添加到环境变量中


# 字节数组转字符串
"".join("{:02x}".format(x) for x in addrTmp)
"".join("%02x" % x for x in addrTmp)
