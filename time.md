# linux time

## date
����ϵͳ��ǰʱ��

```
#��ȡ��ǰʱ��
$ date
Thu Nov 29 15:00:47 CST 2018

# ���ض���ʽ�����ǰʱ��
$ date +'%Y-%m-%d %H:%M:%S'
2018-11-29 15:01:31

# ����ϵͳʱ��
$ date -s '20180101 01:01:01'
Mon Jan  1 01:01:01 CST 2018

#���ʱ��
$ date -d 'next Monday'
Mon Dec  3 00:00:00 CST 2018
```

## hwclock
hwclock�������ڷ��ʷ�������Ӳ��CMOSʱ��
```
# ��ȡϵͳӲ��ʱ��
$ hwclock
Thu 29 Nov 2018 03:19:01 PM CST  -0.756886 seconds

# ���ò���ϵͳ�����ʱ�䣬��ϵͳӲ��ʱ��ͬ��
$ sudo hwclock -s

# ����ϵͳӲ��ʱ�䣬�����ϵͳ�����ʱ��ͬ��
$ sudo hwclock -w

# ����ϵͳӲ��ʱ��
hwclock --set --date '20180101 00:00:00'
```

## ntp
��ntp������ͬ��ʱ��

```
# ��װntp����������
sudo yum install ntp

# ��ntp��������Ϊȱʡ����
sudo chkconfig ntp on

# �޸���������������-g -x����������ntp������ϵͳʱ�����ϴ�ʱҲ����������
sudo vi /etc/sysconfig/ntpd

# ����ntp����
sudo service ntpd restart
```

## ʱ��
```
# ��ϵͳʱ����Ϊ�Ϻ�ʱ�� (�༴CSTʱ��)
$ ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```