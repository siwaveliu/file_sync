---
title: 面试题-FAE
tags: 矽久,文档,版本
grammar_cjkRuby: true
grammar_mindmap: true
renderNumberedHeading: true
grammar_code: true
grammar_decorate: true
grammar_mathjax: true
---

[toc!?direction=lr]
####
堆和栈在内存中的区别是什么(数据结构方面以及内存方面)堆和树的区别；
####
执行语句“ k=7>>1; ”后，变量 k 的当前值是
####
若有宏定义：#define MOD(x，y) x％y
则执行以下语句后的输出结果是
int a=13，b=94；
printf(″％d ″，MOD(b，a+4))；
#### 
```c?linenums
int f(char *s, char *t)
{
	char *p1, *p2;
	for(p1 = s; *p1; p1++)
	  for(p2 = t; *p2; p2++)
        if(*p1 == *p2) break;
	  if(*p2 == '\0') break;
	return p1 - s;
}
```
(a)f("abcd", "babc")的值是多少？
(b)f("abcd", "bcd")的值是多少？
(c)当传递两个字符串s和t时，函数f的返回值一般是什么？
####
请描述一下电容的特性？电感特性？磁珠特性？
####
示波器的采样率、存储深度、采样时间之间的关系?
####
常见的LC模拟滤波器类型？滤波器的常用指标？