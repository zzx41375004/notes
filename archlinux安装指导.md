# 欢迎使用archlinux

# 前言

archlinux和debian类似，是一个linux内核操作系统。

## Linux相较于Windows的优点

1. *开源*
2. *更轻、更快、更强、更安全*
3. *强大便捷的包管理器*
4. *强大便捷的命令行*
5. *高手云集的开源社区，以及超多、超强的生产力工具*<br>
[vim，编辑器之神](https://www.bilibili.com/video/BV164411P7tw)<br>
[ranger，最好用的文件管理器](https://www.bilibili.com/video/BV1b4411R7ck)<br>
[dwm，最好用的“桌面”](https://www.bilibili.com/video/BV11J411t7RY)<br>
[lazygit，最好用的git前端](https://www.bilibili.com/video/BV1gV411k7fC)

对程序员而言，linux的工作效率显著高于windows。

## archlinux的不同之处

1. archLinux的哲学是“简洁、高效”。

2. 相较于ubuntu、centos等，arch是学习linux更好的方式。例如，arch并不配套桌面环境，因此用户第一次使用时需要自己选择网络管理器并在终端下配置网络，然后安装自己喜欢的桌面环境或者窗口管理器。

3. arch认为用户应当了解自己的操作系统，并能够自己动手解决问题，在这个过程中，用户可以学到大量的计算机知识和经验。

4. arch的软件仓库极为丰富，并采用滚动更新，你可以在这里找到最多、最全和最新的软件，并且大部分开源，本身亦是很好的学习素材。

# archlinux的安装

互联网上能找到大量的安装教程，这里提供几篇供参考。<br>
[archwiki官方文档](https://wiki.archlinux.org/index.php/Installation_guide_\(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87\))<br>
[单系统教程](https://www.bilibili.com/video/BV11J411a7Tp)<br>
[双系统教程1](https://www.bilibili.com/video/BV1Ki4y1u7d4)<br>
[双系统教程2](https://zhuanlan.zhihu.com/p/138951848)

我建议初学者或者有移动办公需求者, 可以将arch装在移动介质里，安装方法和内置硬盘基本一致，可参照[单系统教程](https://www.bilibili.com/video/BV11J411a7Tp)。<br>
这样做的好处有：
1. 避免重装windows
2. 充分发挥电脑硬件的性能
3. 这个介质里的arch本身亦可以作为一个arch的安装器
4. 你可以在不同的电脑上使用同一个操作系统
5. 如果你使用的介质是固态硬盘，那么使用体验和内置硬盘并无明显差异

为使介质里的arch获得更好的兼容性，请参考： [如何在U盘(闪存盘)上安装一个常规的 Arch](https://wiki.archlinux.org/title/Install_Arch_Linux_on_a_removable_medium_\(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87\))

主要的区别在于
1. 安装grub时，应加入--removable选项

```
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=Arch --removable
```

2. 修改 /etc/mkinitcpio.conf，将 HOOKS 中的block 和 keyboard 移动到 autodetect 前面。

```
HOOKS=(base systemd udev block keyboard autodetect modconf filesystems fsck)
```

为获得较好的读写速度，请使用写（注意是写）速度不低于30MB/s的移动介质， 例如雷克沙M45（此款只有大于64G的版本才能达到>30MB/s）或闪迪CZ74等。

# 使用arch的经验之谈

1. 笨重的桌面环境如gnome、kde并不好用，如果一定要用桌面环境，推荐使用精简的xfce

2. 桌面环境彼此并不冲突，可以同时安装多个，新手不妨尝试多种桌面，体验不同的设计哲学

3. 窗口管理器如dwm、i3wm等非常好用，设计哲学高效简洁，非常适合程序员，强烈推荐

4. linux中可以用virtualbox安装window7虚拟机，性能很好，足以满足word、excel等日常办公需要

5. 你可以同时安装多个网络管理器，例如NetworkManager和iwd，但是应当只启动一个管理器的服务，即systemctl enable唯一的网络管理器，其他服务程序类型亦同理

6. 开源的显卡驱动一般不会冲突，可以安装许多个，但是闭源驱动需谨慎选择

安装使用过程中有任何问题欢迎一起研究。


本文档将放在https://gitee.com/zzx2070276239/notes，并不定期更新。

欢迎使用archlinux！
