---
title: ID使用说明 
tags: 矽久,文档,版本V1.0
grammar_cjkRuby: true
grammar_mindmap: true
renderNumberedHeading: true
grammar_code: true
grammar_decorate: true
grammar_mathjax: true
---


[toc!?direction=lr]

___

|修订内容|版本号|修订人|
|-|-|-|
创建 |1.0| 刘博强

----

# 使用范围
ID包括生产ID，模块ID和芯片ID，目前生产ID长度是6字节，模块ID长度11字节，芯片ID长度是24字节。仅支持以上长度，不支持自定义ID长度。
该文档说明仅适用于我司芯片及固件。
# ID写入
必须通过我司的生产工装才可以写入生产ID、模块ID和芯片ID
# ID读取
符合《HPLC技术应用手册-中国电科院V2.7》要求，
1.可以通过HPLC的应用层协议——查询ID信息获取，具体格式参照《低压电力线宽带载波通信互联互通技术规范　第4-3部分：应用层通信协议》；
2.可以通过1376.2协议中03H-F12、10H-F7和10H-F112获取，具体格式参照《HPLC技术应用手册-中国电科院V2.7》中ID管理部分；
3.可以通过网络诊断报文读取；具体格式请参照《网络诊断报文.pdf》，该报文格式为厂家自定义，请勿外传。
