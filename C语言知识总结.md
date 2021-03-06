---
title: C语言知识总结 
tags: C,编程,嵌入式
grammar_cjkRuby: true
grammar_tableExtra: true
---
[toc]

# 字符串
## 字符数组与字符指针
```c
char data[] = "June 14"
char *date = "June 14"
```
两者虽然看起来类似，但是**不能互换**
* 在声明为数组时，就像任意数组元素一样，可以修改存储在date中的字符。在声明为指针时，date指向字符串字面量，而字符串字面量是不可修改的
* 在声明为数组时，date是数组名；在声明为指针时，date是指针变量，这个变量可以在程序运行期间指向其它字符串

## 字符串的读和写
显示字符串的一部分：%.*p*s，这里*p*是要显示的字符数量。
显示指定字段：%*m*s，会在大小为m的字段内显示字符串。（对于超过m个字符的字符串，printf函数会显示出整个字符串，而不会截断。）如果字符串
少于m个字符，则会在m字段内右对齐输出，如果要强制左对齐，可以在m前加一个减号。m和p组合使用%*m.p*s
puts(str)也是字符串输出函数，在写完字符串后，puts函数会额外添加一个换行符。
### scanf和gets的区别
* scanf("%s", str)会在开始跳过空白字符，遇到非空白字符开始读取，直到遇到空字符结束，最后会存储空字符到结尾。
* gets(str)函数不会在开始跳过空白字符
* gets(str)函数会持续读入直到遇到换行符，存入时，会把结尾的换行符替换成空字符。
* scanf("%*n*s", str) 会比较安全，指定读入的字符数，不然gets和scanf都无法检测数组何时被填满。gets函数天生就不安全，可以使用fgets函数替代

### 定义指向函数的指针
typedef void (*MTR_RecvCallbackType)(uint8_t *data, uint16_t len,APL_DataProtoType data_type);

