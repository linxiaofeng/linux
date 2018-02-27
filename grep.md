# grep

### 简介
grep（Global Regular Expression Print）主要用来对文件或标准输入中的**行**进行匹配。

### 语法
grep [OPTIONS] PATTERN [FILE]

主要有三种调用方式:

`grep(grep -G)` 将PATTERN译为标准正则处理

`egrep(grep -E)` 将PATTERN译为扩展正则处理

`fgrep(grep -F)` 将PATTERN译为固定字符串处理

### 参数
`-f FILE, --file=FILE` 从文件中获取PATTERN

`-i, --ignore-case` 无视PATTERN和输入中大小写的区别

`-v, --invert-match` 取不匹配的行

`-x, --line-regexp` 选取整行匹配的行

`-c, --count` 输出匹配的行的数量

`--color[=WHEN], --colour[=WHEN]` 匹配的地方突出颜色。WHEN可以是never, always, auto.

`-o, --only-matching` 只输出匹配的部分

`-s, --no-messages` 屏蔽文件不存在和不可读的错误信息

`-H --with-filename` 输出匹配行所在的文件，多个文件查询时为默认状态

`-h, --no-filename` 不输出匹配行所在的文件，单个文件查询时为默认状态

`-n, --line-number` 输出匹配行在文件中的行数

`-A NUM, --after-context=NUM` 打印匹配行及后续的NUM行数据

`-B NUM, --before-context=NUM` 输出匹配行及之前NUM行数据

`-C NUM, -NUM, --context=NUM` 输出匹配行之前及之后NUM行数据

`--exclude=GLOB` 排除名字符合GLOB的文件

`--exclude-from=FILE` 排除名字符合FILE中的任何匹配项的文件

`--exclude-dir=DIR` 排除递归查询中的目录

`--include=GLOB` 只查询名字符合GLOB的文件

`-R, -r, --recursive` 递归的查询目录及目录下的文件

### 正则表达式

`[:alnum:]` [0-9A-Za-z]

`[:alpha:]` [a-zA-Z]

`[:cntrl:]` 控制字符

`[:digit:]` [0-9]

`[:graph:]` 图形字符 `[:alnum:]` + `[:punct:]`

`[:lower:]` [a-z]

`[:upper:]` [A-Z]

`[:print:]` 可打印字符 `[:alnum:]` + `[:punct:]` + space

`[:punct:]` 标点字符 `! " # $ % & ' ( ) * + , - . / : ; < = > ? @ [ \ ] ^ _ \` { | } ~`

`[:space:]` 空格、tab

`[:xdigit:]` 十六进制数字 `0 1 2 3 4 5 6 7 8 9 A B C D E F a b c d e f`
