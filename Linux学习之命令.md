# Linux学习

# Fira Code字体
[how to install Fira Code](https://github.com/tonsky/FiraCode/wiki/Installing)

# 查找

~~~
find / -name httpd.conf　　#在根目录下查找文件
find /etc -name httpd.conf　　#在/etc目录下文件httpd.conf
find /etc -name ‘srm’　　#使用通配符*(0或者任意多个)。表示在/etc目录下查找文件名中含有字符串‘srm’的文件
find . -name ‘srm*’ 　　#表示当前目录下查找文件名开头是字符串‘srm’的文件
~~~

# 联网

~~~
arch:
ip link //查看网卡
wpa_supplicant -c <配置文件> -i wlan0 &
dhcpcd //分配ip
~~~

# wpa_supplicant 与dhcpcd

~~~
CW使用的网络管理工具
~~~



# 添加用户

~~~
useradd -m -G wheel zzx //-m创建家目录，-G分配用户组，组名是wheel
~~~



# 安装Arch Linux

[Arch wiki](https://wiki.archlinux.org/index.php/EFI_system_partition)

~~~
mkfs.fat -F32 /dev/xxx
~~~

[知乎某教程](https://zhuanlan.zhihu.com/p/138951848)

~~~
pacman -S grub efibootmgr networkmanager network-manager-applet dialog wireless_tools wpa_supplicant os-prober mtools dosfstools ntfs-3g base-devel linux-headers reflector git sudo
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=Arch
~~~

[虚拟机没有网卡解决方案](https://tieba.baidu.com/p/7254164136)

[虚拟机安装archlinux以及图形界面](https://www.jianshu.com/p/619274de1935)

## 设置代理

[privoxy配置与使用，终端貌似可以用](https://www.jianshu.com/p/a164fac07b4a?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)

~~~
安装shadowsocks-libev
可以使用shadowsocks-qt5进行配置
~~~

# Pacman

[pacman卸载](https://zhidao.baidu.com/question/1433680113110804739.html)

~~~
pacman -Rs //删除指定软件包，及bai其所有没有被其du他已安zhi装软件包使用的依赖关系：
~~~

# 交换Esc和Caps（键盘映射）

[教程](https://qastack.cn/superuser/566871/how-to-map-the-caps-lock-key-to-escape-key-in-arch-linux)

~~~
1、setxkbmap -option caps:escape
~~~

# 调节亮度

~~~
可以用echo > /sys/class/backlight/intel_backlight/brightness
~~~

# 作业

~~~
git clone -b fm https://github.com/professordeng/xv6-expansion.git
sudo code --user-data-dir="~/.vscode-root"	//root权限打开VScode
~~~

## 问题

## 大作业

### 修改位置记录

proc.c

~~~
modify:
alloproc,pinit,fork,exit,wakeup
add:
getPtableIndex
~~~

~~~
1、bootasm.S的出口是哪儿，如何进入bootmain.c?
2、main.c中的mapmain静态声明：
static void mpmain(void)  __attribute__((noreturn));
是什么意思？
这是与GCC关联的，就是把__attribute__ ((noreturn))放在自己定义的函数后面，记得在“；”前面。这样可以改变函数的属性，代表这个自己编写的函数在进行GCC编译的时候声明没有返回值。
3、MP是什么意思？
~~~



# 解压

~~~
https://www.baidu.com/link?url=lTsk1A5kZhhq1SjF8v_IyR7dqI2QalLNUxyG5BojvKQwE71oWsYiYMM-n-gZvTFvZG3qhcQJNQTuWiv4OYoXGq&wd=&eqid=e09a89a6000606d7000000035fde0a3a
~~~

~~~
tar –zxvf xv6-public-xv6-rev9.tar.gz
z:support gzip format
x: extract
v: progress visible
f: point out the file
~~~

```
linux下最常用的打包程序就是tar了，使用tar程序打出来的包我们常称为tar包，tar包文件的命令通常都是以.tar结尾的。生成tar包后，就可以用其它的程序来进行压缩。
1．命令格式：
tar[必要参数][选择参数][文件] 

2．命令功能：
用来压缩和解压文件。tar本身不具有压缩功能。他是调用压缩功能实现的 

3．命令参数：
必要参数有如下：
-A 新增压缩文件到已存在的压缩
-B 设置区块大小
-c 建立新的压缩文件
-d 记录文件的差别
-r 添加文件到已经压缩的文件
-u 添加改变了和现有的文件到已经存在的压缩文件
-x 从压缩的文件中提取文件
-t 显示压缩文件的内容
-z 支持gzip解压文件
-j 支持bzip2解压文件
-Z 支持compress解压文件
-v 显示操作过程
-l 文件系统边界设置
-k 保留原有文件不覆盖
-m 保留文件不被覆盖
-W 确认压缩文件的正确性

可选参数如下：
-b 设置区块数目
-C 切换到指定目录
-f 指定压缩文件
--help 显示帮助信息
--version 显示版本信息
```

# Git

[廖雪峰的git教程](https://www.liaoxuefeng.com/wiki/896043488029600/898732792973664)

```
https://www.runoob.com/manual/git-guide/
```

```
git clone -b <name> <path>	//b means branch 
git add <filename>?
git add *
git commit -m "代码提交信息"
```

## 创建版本库

~~~
git init	//将此文件夹中作为git仓库
git add	...	//添加文件
git commit -m "备注"	//存档，‘-m’添加你想写的备注
~~~

## 查看工作区状态

~~~
git status
git diff
~~~

## 版本回退

~~~
git log	//查看存档，可加参数--pretty=oneline
//commit id是SHA1计算出来的一个很大的数字
//HEAD表示当前版本，上一个版本：HEAD^，上上个：HEAD^^
//HEAD~100, 前100个版本
git reset --hard HEAD~100	//回退100个版本
git reset --hard <commit id>	//id四位即可
git reflog	//查看命令记录，会显示历史存档的commit id
~~~

## 工作区与暂存区

~~~
工作区是文件夹目录，版本库是.git目录（不是工作区）
~~~

## 撤销修改

~~~
git checkout --<file>	//丢弃文件的修改，回到暂存区或者版本库的状态
‘--’ 很重要，若没有则变成“切换到另一个分支”
git reset HEAD <file>	//把暂存区的修改撤销掉（unstage），重新放回工作区
~~~

## 删除文件

~~~
git rm <file>
git checkout --<file>	//从版本库恢复文件
~~~

## 添加远程库

~~~
git remote add origin <ssh或者http地址>	//关联远程仓库
~~~

Github创建一个空仓库之后，会给提示；
添加ssh密钥方法见：https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

~~~
git push -u origin master	//把本地库的内容推送到远程
~~~

用`git push`命令，实际上是把当前分支`master`推送到远程。

由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

~~~
git push origin master
~~~

从现在起，只要本地作了提交，就可以通过命令把本地`master`分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！

## 创建分支与切换

~~~
$ git checkout -b dev
Switched to a new branch 'dev'
$ git switch -b dev
//和checkout一样，更科学
$ git branch -d dev	//删除dev分支
$ git checkout -b dev origin/dev
swtich and clone a branch from origin/dev , named it dev
~~~

`git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

~~~
$ git branch dev
$ git checkout dev	//切换到dev分支
Switched to branch 'dev'
~~~

然后，用`git branch`命令查看当前分支：

~~~
$ git branch
* dev
  master
~~~

`git branch`命令会列出所有分支，当前分支前面会标一个`*`号。

## 解决冲突

### unpopulated_submodule

[course](https://zhuanlan.zhihu.com/p/134130089)

~~~
git rm -rf --cached <file>
~~~

# 修改分支名称

~~~
git branch -m oldname newname	//modify local, if you want to modify origin name, just push
~~~





# 程序中调用shell

```
system()	\\system(“find / -uname \”*mmcblk*\””)
popen()		\\FILE  *fp=popen("bash /home/book/shell/test.sh","r");
exec函数族		
\\char *argv[]={"find","/sys/block/","-name","\"*mmcblk*\"",NULL};
\\ret=execvp("find",argv);
```

```
//popen很好用
#include <stdio.h>
#include <signal.h>
#include <unistd.h>
#include <string.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/wait.h>
#include <sys/utsname.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <dirent.h>

#define BUF_SIZE 10000

int main()
{
	int pid,fd_pipe,ret;
	printf("entering main process\n");
    FILE * p_file = NULL;

    p_file = popen("sudo find /sys/block/ -name \"*loop*\" ","r");
    if(!p_file){
        perror("popen");
    }
    char buf[BUF_SIZE];
    while(fgets(buf,BUF_SIZE,p_file)!=NULL){
        fprintf(stdout, "%s", buf);
    }

    pclose(p_file);


	return 0;
}
```

# 流处理

~~~
while(fgets(buf,BUF_SIZE,p_file)!=NULL)
~~~

# 查看Ubuntu的版本和codename

~~~
lsb_release -a
~~~

# root权限打开vscdode

~~~
sudo code --user-data-dir="~/.vscode-root"
~~~



# 更改文件夹的权限

~~~
sudo chown -R [当前用户] [需要操作的文件夹路径(绝对路径)]
~~~

# 安装中文输入法

[archwiki教程](https://wiki.archlinux.org/index.php/Fcitx_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))

<https://blog.csdn.net/css360/article/details/109245449>

~~~
ubuntu:
sudo apt install fcitx	//先安装fcitx这个语言工具
然后设置键盘，可以输入im-config
sudo apt-get -y install fcitx-pinyin	//安装fcitx-pinyin(有双拼)
arch:
安卓fcitx、fcitx-configtool和一些包，在图形界面中添加中文输入法，注意不是键盘布局
~~~

其它输入法

~~~
sudo apt install fcitx-googlepinyin
fcitx-config-gtk3	//配置？干啥用的？
~~~

# xterm

[配置字体大小，背景等](https://www.cnblogs.com/ScriptXoX/p/9997633.html)

# bash

~~~ 
//.inputrc
set completion-ignore-case on
set show-all-if-ambiguous on
set match-hidden-files off
~~~

# SSH

## windows terminal 配置ssh

[windows terminal连接远程ssh并传输文件](https://www.jianshu.com/p/7c66c6a5950d)

~~~
在profiles列表里增加如下片段
{
    "guid": "{c2b7c779-0f4f-4476-bfa5-313b42c9851a}",
    "hidden": false,
    "name": "CentOS",
    "commandline": "ssh root@anydomain.com -p anyport",
    "icon": "ms-appdata:///Local/centoslogo-32.png"
}
~~~

~~~
好用的远程连接软件
1、MobaXterm:自动文件通信，黏贴板共享；
2、Putty:开源，免费。
~~~

```
ps -ef|grep ssh	//查看ssh服务
service sshd start //启动ssh
service sshd stop
service sshd restart
service sshd status
//有时是ssh
sudo apt-install sshd 或 sudo apt-get install openssh-server
```

## 与windows交互

[putty如何连接xlaunch_使用 Xming 和 PuTTY 配置 X11](https://blog.csdn.net/weixin_29725791/article/details/112024085)

~~~
通过X11
首先windows要安装服务程序（Xming：local:0.0，也可以用Moba的X11服务程序）,
Putty中开启X11，填写正确地址写
~~~



# APT

~~~
apt-get install
apt-get purge //remove
~~~



# 重命名文件夹

<https://www.linuxidc.com/Linux/2015-01/111116.htm>

~~~
mv A B
~~~

# figlet

~~~
figlet zzx	
//show "zzx" in command line
~~~

~~~
r !filget zzx
//read "zzx" to vim file (ex. vimrc)
~~~



# vim

## 更改光标颜色

~~~
"插入模式时是红色
au InsertLeave * hi Cursor guibg=red
"离开插入模式时是绿色
au InsertEnter * hi Cursor guibg=green
~~~



## 安装与配置

### windows安装

[在Windows中安装vim](https://www.cnblogs.com/Eric-jx/p/10491922.html)

[Win10中CapsLock与Esc键对调](https://www.jianshu.com/p/942c3521f2c4)

## Linux安装

~~~
缺省配置文件在/etc/vim/
用户配置文件在/home/name/.vimrc
~~~

## 命令与快捷键

~~~
h key-notation	//查看帮助信息
help i_CTRL-J	//查看CTRL-I的键位
:w !sudo tee %	//以root用户保存
~~~

~~~
<Up>            cursor-up                       cursor-up cursor_up
<Down>          cursor-down                     cursor-down cursor_down
<Left>          cursor-left                     cursor-left cursor_left
<Right>         cursor-right                    cursor-right cursor_right 
<S-Up>          shift-cursor-up
<S-Down>        shift-cursor-down
<S-Left>        shift-cursor-left
<S-Right>       shift-cursor-right
<C-Left>        control-cursor-left
<C-Right>       control-cursor-right
~~~

### 分屏操作

~~~
#取消其它分屏，只保留当前分屏	:only 
#或者 [CTRL] W o
#退出当前所在分屏 :q

|CTRL-W_+|	CTRL-W +	   increase current window height N lines
|CTRL-W_-|	CTRL-W -	   decrease current window height N lines
|CTRL-W_:|	CTRL-W :	   same as |:|, edit a command line
|CTRL-W_<|	CTRL-W <	   decrease current window width N columns
|CTRL-W_=|	CTRL-W =	   make all windows the same height & width
|CTRL-W_>|	CTRL-W >	   increase current window width N columns
|CTRL-W_H|	CTRL-W H	   move current window to the far left
|CTRL-W_J|	CTRL-W J	   move current window to the very bottom
|CTRL-W_K|	CTRL-W K	   move current window to the very top
|CTRL-W_L|	CTRL-W L	   move current window to the far right
|CTRL-W_P|	CTRL-W P	   go to preview window
|CTRL-W_R|	CTRL-W R	   rotate windows upwards N times
|CTRL-W_S|	CTRL-W S	   same as "CTRL-W s"
|CTRL-W_T|	CTRL-W T	   move current window to a new tab page
|CTRL-W_W|	CTRL-W W	   go to N previous window (wrap around)
|CTRL-W_]|	CTRL-W ]	   split window and jump to tag under cursor
|CTRL-W_^|	CTRL-W ^	   split current window and edit alternate
				   file N
|CTRL-W__|	CTRL-W _	   set current window height to N (default:
				   very high)
|CTRL-W_b|	CTRL-W b	   go to bottom window
|CTRL-W_c|	CTRL-W c	   close current window (like |:close|)
|CTRL-W_d|	CTRL-W d	   split window and jump to definition under
				   the cursor
|CTRL-W_f|	CTRL-W f	   split window and edit file name under the
				   cursor
|CTRL-W_F|	CTRL-W F	   split window and edit file name under the
				   cursor and jump to the line number
				   following the file name.
|CTRL-W_g_CTRL-]| CTRL-W g CTRL-]  split window and do |:tjump| to tag under
				   cursor
|CTRL-W_g]|	CTRL-W g ]	   split window and do |:tselect| for tag
				   under cursor
|CTRL-W_g}|	CTRL-W g }	   do a |:ptjump| to the tag under the cursor
|CTRL-W_gf|	CTRL-W g f	   edit file name under the cursor in a new
				   tab page
|CTRL-W_gF|	CTRL-W g F	   edit file name under the cursor in a new
				   tab page and jump to the line number
				   following the file name.
|CTRL-W_gt|	CTRL-W g t	   same as `gt`: go to next tab page
|CTRL-W_gT|	CTRL-W g T	   same as `gT`: go to previous tab page
|CTRL-W_h|	CTRL-W h	   go to Nth left window (stop at first window)
|CTRL-W_i|	CTRL-W i	   split window and jump to declaration of
				   identifier under the cursor
|CTRL-W_j|	CTRL-W j	   go N windows down (stop at last window)
|CTRL-W_k|	CTRL-W k	   go N windows up (stop at first window)
|CTRL-W_l|	CTRL-W l	   go to Nth right window (stop at last window)
|CTRL-W_n|	CTRL-W n	   open new window, N lines high
|CTRL-W_o|	CTRL-W o	   close all but current window (like |:only|)
|CTRL-W_p|	CTRL-W p	   go to previous (last accessed) window
|CTRL-W_q|	CTRL-W q	   quit current window (like |:quit|)
|CTRL-W_r|	CTRL-W r	   rotate windows downwards N times
|CTRL-W_s|	CTRL-W s	   split current window in two parts, new
				   window N lines high
|CTRL-W_t|	CTRL-W t	   go to top window
|CTRL-W_v|	CTRL-W v	   split current window vertically, new window
				   N columns wide
|CTRL-W_w|	CTRL-W w	   go to N next window (wrap around)
|CTRL-W_x|	CTRL-W x	   exchange current window with window N
				   (default: next window)
|CTRL-W_z|	CTRL-W z	   close preview window
|CTRL-W_bar|	CTRL-W |	   set window width to N columns
|CTRL-W_}|	CTRL-W }	   show tag under cursor in preview window

~~~



### 替换字符串

~~~
To substitute new for the first old in a line type    :s/old/new
To substitute new for all 'old's on a line type       :s/old/new/g
To substitute phrases between two line #'s type       :#,#s/old/new/g
To substitute all occurrences in the file type        :%s/old/new/g
To ask for confirmation each time add 'c'             :%s/old/new/gc
~~~

### 行移动

~~~
CTRL-G  displays your location in the file and the file status.
G  moves to the end of the file.
number  G  moves to that line number.
gg  moves to the first line.
~~~

### 查找

~~~
Typing  /  followed by a phrase searches FORWARD for the phrase.
Typing  ?  followed by a phrase searches BACKWARD for the phrase.
After a search type  n  to find the next occurrence in the same direction or  N  to search in the opposite direction.
CTRL-O takes you back to older positions, CTRL-I to newer positions.
~~~

### Lesson 4

~~~
1. CTRL-G  displays your location in the file and the file status.
G  moves to the end of the file.
number  G  moves to that line number.
gg  moves to the first line.
2. Typing  /  followed by a phrase searches FORWARD for the phrase.
Typing  ?  followed by a phrase searches BACKWARD for the phrase.
After a search type  n  to find the next occurrence in the same direction
or  N  to search in the opposite direction.
CTRL-O takes you back to older positions, CTRL-I to newer positions.
3. Typing  %  while the cursor is on a (,),[,],{, or } goes to its match.
4. To substitute new for the first old in a line type    :s/old/new
To substitute new for all 'old's on a line type       :s/old/new/g
To substitute phrases between two line #'s type       :#,#s/old/new/g
To substitute all occurrences in the file type        :%s/old/new/g
To ask for confirmation each time add 'c'             :%s/old/new/gc
~~~



### Lesson 5

~~~
 1.  :!command  executes an external command.
      Some useful examples are:
         (Windows)        (Unix)
          :!dir            :!ls            -  shows a directory listing.
          :!del FILENAME   :!rm FILENAME   -  removes file FILENAME.
2.  :w FILENAME  writes the current Vim file to disk with name FILENAME.
3.  v  motion  :w FILENAME  saves the Visually selected lines in file FILENAME.
4.  :r FILENAME  retrieves disk file FILENAME and puts it below the cursor position.
5.  :r !dir  reads the output of the dir command and puts it below the cursor position.
~~~

### Lesson 6

~~~
1. Type  o  to open a line BELOW the cursor and start Insert mode.
Type  O  to open a line ABOVE the cursor.
2. Type  a  to insert text AFTER the cursor.
Type  A  to insert text after the end of the line.
3. The  e  command moves to the end of a word.
4. The  y  operator yanks (copies) text,  p  puts (pastes) it.
5. Typing a capital  R  enters Replace mode until  <ESC>  is pressed.
6. Typing ":set xxx" sets the option "xxx".  Some options are:
'ic' 'ignorecase'       ignore upper/lower case when searching
'is' 'incsearch'        show partial matches for a search phrase
'hls' 'hlsearch'        highlight all matching phrases
You can either use the long or the short option name.
7. Prepend "no" to switch an option off:   :set noic
~~~

### Lesson 7

~~~
修改配置文件
Vim has many more features than Vi, but most of them are disabled by
default.  To start using more features you have to create a "vimrc" file.
1. Start editing the "vimrc" file.  This depends on your system:
:e ~/.vimrc             for Unix
:e $VIM/_vimrc          for Windows
2. Now read the example "vimrc" file contents:
:r $VIMRUNTIME/vimrc_example.vim
3. Write the file with:
:w
The next time you start Vim it will use syntax highlighting.
You can add all your preferred settings to this "vimrc" file.
For more information type  :help vimrc-intro
~~~

~~~
1. Type  :help  or press <F1> or <HELP>  to open a help window.
2. Type  :help cmd  to find help on  cmd .
3. Type  CTRL-W CTRL-W  to jump to another window.
4. Type  :q  to close the help window.
5. Create a vimrc startup script to keep your preferred settings.
6. When typing a  :  command, press CTRL-D to see possible completions.
Press <TAB> to use one completion.
~~~

## firfore

~~~
Basic usage

- h, j, k, l: scroll left, down, right, up, and right
- j, k: scroll vertically
- h, l: scroll horizontally
- Ctrl+U, Ctrl+D: scroll pages by half of screen
- Ctrl+B, Ctrl+F: scroll pages by a screen
- 0, $: scroll a page to leftmost/rightmost
- gg, G: scroll to top/bottom

- gg, G: scroll to top and bottom
- d: delete current tab
- u: reopen close tab
- K, J: select prev or next tab
- r: reload current tab
- zp: toggle pin/unpin current tab
- zd: duplicate current tab

- f: start following links in the page
- H: go back in histories
- L: go forward in histories
- [[, ]]: find prev or next links and open it
- gu: go to parent directory
- gU: go to root directory

- :: open console
- o, t, w: open a page in current tab, new tab, or new window
- O, T, W: similar to o, t, w, but that contains current URL
- b: Select tabs by URL or title
- zi, zo: zoom-in/zoom-out
- zz: Set default zoom level
- y: copy URL in current tab
- Shift+Esc: enable or disable the add-on in current tab.
~~~



# windows子系统

[win10是最好的“Linux发行版”（一）——子系统、终端、包管理器](https://www.bilibili.com/video/BV11o4y1o7x7?t=1087)

[解决wsl 环境变量PATH混乱的办法](https://blog.csdn.net/u013566243/article/details/110592547)

~~~
\\wsl$\Ubuntu
//windows下进入ubuntu文件系统：
~~~

# 更改用户默认shell

~~~
chsh -s <shell路径>	//例如chsh -s /bin/zsh
~~~

修改默认文本编辑器

~~~
echo export EDITOR=/usr/bin/vim >> ~/.bashrc
echo export EDITOR=/usr/bin/vim >> ~/.zshrc
~~~









































