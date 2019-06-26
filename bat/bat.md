# bat 基础
## 显示信息 echo
### 1、输出提示信息
```
echo abc
echo efg
```
执行显示
```
C:\XXX>echo abc
abc
C:\XXX>echo efg
efg
```
<font color=red>此时批处理文件运行会显示相应的命定行代码</font>
### 2、关闭命令回显
将`@`放在命令前面即可
### 3、打开回显或关闭回显功能
格式：echo [on|off]
### 4、输出空行，即相当于输入一个回车
当你输入如下
```
echo 
::这里使用Enter换行
```
会出现以下情况
```
ECHO 处于打开状态
```
这时其实是没有达到换行效果的
解决方式：
```
echo.
```
<font color=red>注意命令中的"."，要紧跟在ECHO后面，中间不能有空格，否则“.”将被当作提示信息输出到屏幕。另外“.”可以使用`.:;"/]+\`这些任意符号代替</font>
### 5、答复命令中的提问
格式：ECHO 回复|命令表达式
作用：通过管道命令 | 把“回复”作为输入传导给后面的“命令表达式”，并作为“命令表达式”的输入。
```
@echo off
rd /s C:\abc
pause
```
执行显示
```
c:\abc，是否确认（Y/N）?
```
批处理命令也可以省略改为
```
@echo off
echo Y|rd /s c:\abc
pause
```
### 6、建立新文件或增加文件内容
格式：echo 文件内容>文件名
```
@echo off
echo .>myfile.txt
pause
```
在当前目录下建立了一个myfile.txt文件，文件的内容为`.`
## 注释语句 rem
rem为注释命令，一般用来给程序加上注解，该命令后的内容不被执行，但能回显。
另外`::`可以起到注释作用，而且更简洁，但有两点需要注意

第一、任何以冒号:开头的字符行在批处理	中都被视作标号，而直接忽略其后所有内容
有效标号：冒号后紧跟一个以字母数字开否的字符串，goto语句可以识别
无效标号：冒号后紧跟一个非字母数字的一个特殊符号，goto 无法识别的标号，可以起到注释
作用，所以 :: 常被用作注释符号，其实 : 也可起注释作用。
## 目录切换 cd
## 列文件名 dir
























