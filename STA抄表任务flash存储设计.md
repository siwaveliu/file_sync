---
title: STA抄表任务flash存储设计
tags: 矽久,文档,版本
grammar_cjkRuby: true
grammar_mindmap: true
renderNumberedHeading: true
grammar_code: true
grammar_decorate: true
grammar_mathjax: true
---


[toc!?direction=lr]

# 存储空间
使用76KB空间(M_data)，位置是flash最后的76K。预计可支持15分钟频率抄表的3天时间，多出的4k为了统一擦除使用。
# 参数存储需求
一共支持20个数据大小。
记录每个数据项，回复长度和数据索引位置。
记录集中器时钟和电表时钟的秒级时间差，4字节。

# 每个时间点的数据格式
每个时间点使用256B大小，对应flash一个page。
前16B作为数据头保存一些必要信息。
之后的238B作为存储数据的空间，最后2B作为数据的crc16校验和
序号|时间戳|采集周期|保留|校验和|数据|数据校验和
|-|-|-|-|-|-|-|
2B|4B|1B|8B|1B|238B|2B
M_data中的位置，相当于76 * 1024/256|RTC的秒级时间|对应协议中的1~60，单位：分钟|为后续扩展|数据头的校验和|数据|数据校验和
# 构建必要函数
## 启动函数 
uint32_t APP_StaSelfMeterStart(void)
检查参数配置标记，检查时钟差T是否存在。
从索引 （2 * 1024 - 76) * 1024 位置开始，
每次步进0x100, 总步进次数 76 * 4.
搜索M_data中节点头data_header。校验header_sum,如果有效，记录时间戳time_stamp.继续检验下一个节点，如果无效或者获取的time_stamp小于记录时间，说明绕回时间点的最早时刻。判断当前位置是否为sector头，如果是，那么直接erase_sector。
#define 