# linux time

## date
操作系统当前时间

```
#获取当前时间
$ date
Thu Nov 29 15:00:47 CST 2018

# 以特定格式输出当前时间
$ date +'%Y-%m-%d %H:%M:%S'
2018-11-29 15:01:31

# 设置系统时间
$ date -s '20180101 01:01:01'
Mon Jan  1 01:01:01 CST 2018

#输出时间
$ date -d 'next Monday'
Mon Dec  3 00:00:00 CST 2018
```

## hwclock
hwclock命令用于访问服务器的硬件CMOS时间
```
# 获取系统硬件时间
$ hwclock
Thu 29 Nov 2018 03:19:01 PM CST  -0.756886 seconds

# 设置操作系统的软件时间，与系统硬件时间同步
$ sudo hwclock -s

# 设置系统硬件时间，与操作系统的软件时间同步
$ sudo hwclock -w

# 设置系统硬件时间
hwclock --set --date '20180101 00:00:00'
```

## ntp
与ntp服务器同步时间

```
# 安装ntp服务的软件包
sudo yum install ntp

# 将ntp服务设置为缺省启动
sudo chkconfig ntp on

# 修改启动参数，增加-g -x参数，允许ntp服务在系统时间误差较大时也能正常工作
sudo vi /etc/sysconfig/ntpd

# 启动ntp服务
sudo service ntpd restart
```

## 时区
```
# 将系统时区改为上海时间 (亦即CST时区)
$ ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```