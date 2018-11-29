# linux自启动相关

### sysvinit
linux操作系统启动时，首先从BIOS开始，进入boot loader，由bootloader载入内核，进行内核初始化。内核初始化后，启动pid为1的init进程。init进程为系统的第一个进程，负责产生其他用户进程。常见的三种init系统为：sysvinit、upstart和systemd。

#### Run level
sysvinit使用run level来定义“预定的运行模式”。sysvinit会检查`/etc/inittab`中的`initdefault`项，来决定进入何种运行模式。
常见的运行模式有0到6和S。
+ 0 关机

+ 1 单用户模式

+ 2 多用户模式，无network

+ 3 多用户模式

+ 4 用户自定义

+ 5 多用户模式，带图形界面

+ 6 重启

#### 运行顺序
确认运行模式后，执行以下步骤：
1. /etc/rc.d/rc.sysinit

2. /etc/rc.d/rc 和 /etc/rc.d/rcX.d/

3. /etc/rc.d/rc.local

