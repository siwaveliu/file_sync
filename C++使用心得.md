---
title: C++使用心得 
tags: C++,心得
grammar_cjkRuby: true
---
# 使用vs2017作为C++工具时碰到的一些问题
## .pch
使用vs2017创建C++项目时，会自动创建pch.h和pch.cpp。结合搜索的信息，它们的作用和MFC的stdafx.h、stdafx.cpp类似，
在pch.h引入不经常变换的代码会显著的提高编译速度。编译pch.cpp会生成.pch文件，里面应该是放入的已经编译的所有pch中的代码。
这样在其它cpp文件引入pch.h的时，每次编译文件都是直接从.pch中取(前提是pch中的代码都是未变的，这部分是个人理解)。
由于该特性，所以vs2017的工程要求**pch.h文件引入在所有的#include xxx的前面。**

## 错误C2248“ATL::CA2WEX<128>::CA2WEX”: 无法访问 private 成员(在“ATL::CA2WEX<128>”类中声明)
在vs2017中*CA2WEX(_In_ const CA2WEX&) throw();	CA2WEX& operator=(_In_ const CA2WEX&) throw();* 已经是私有化了，
需要使用*LPWSTR m_psz;*  