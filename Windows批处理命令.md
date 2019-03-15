---
title: Windows批处理命令
tags: 新建,模板,小书匠
grammar_cjkRuby: true
---
### 使用forfiles
#### 删除"C:\D\SiBox\log"文件夹7天前的*.st文件
forfiles /p "C:\D\SiBox\log"  /s /m *.st /d -7 /c "cmd /c del @path"
#### 显示"C:\D\SiBox\log"文件夹7天前的*.st文件
forfiles /p "C:\D\SiBox\log"  /s /m *.st /d -7 /c "cmd /c echo @path"