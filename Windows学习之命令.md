# PowerShell

## alias

[PowerShell自定义命令](https://www.cnblogs.com/zbseoag/p/13379076.html)

~~~
1.开启允许命令行执行脚本的权限
右键 PowerShell 选择以管理员身份运行，输入命令：  set-executionpolicy -executionpolicy unrestricted 
2.创建 prefile 文件，输入命令： New-Item -Type file -Force $profile ，这时会创建一个 C:\Users\zzx\Documents\PowerShell\Microsoft.PowerShell_profile.ps1 的 PowerShell  脚本文件。
3. PowerShell 中可以执行与 linux shell 同名的命令，是通过定义命令的别名实现的。 输入 alias 命令，结果可见 cd 实际上是 Set-Location 命令的别名
4.我们可以脚本格式导出这些命令，输入： 
Export-Alias -Path "d:\alias.ps1" -As Script
~~~

# 键盘映射

交换CapsLock于Esc

[教程](https://www.jianshu.com/p/942c3521f2c4)

[详细教程](https://www.bilibili.com/read/cv8001022/)

~~~
首先打开注册表（Win + R 输入 regedit 并运行），并且进入目录：
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout
在该目录下右键点击新建二进制值，名称为 Scancode Map，并打开
接下来按照如下格式[2]输入自己需要更改的键位：
00 00 00 00 00 00 00 00（固定格式）
XX XX XX XX（修改后的按键扫描码（在前）+ 原按键的扫描码（在后））
XX XX XX XX（另一个要替换的按键，同上）
~~~
![](https://i0.hdslb.com/bfs/article/bd17c1ff9c6ae603ec6959f469a6125f32cd13e9.png@1534w_1200h.webp)
