# sed

sed(Stream Editor)用来自动编辑一个或多个文件，简化对文件的反复操作。

### 命令格式
> sed[options] 'command' file

> sed[options] -f scriptfile file

#### options
> -e\<script\>或--expression=\<script\>:以指定script来处理输入，可以同时指定多个script

> -f\<script\>或--file=\<script\>:以script文件中的内容来处理输入

> -n或--quiet或--silent:仅显示script处理后的结果

> -i:直接处理输入文件

#### command
> a\ 在当前行下边插入文本 `sed '/^test/a\new line' file`file文件中以test开头的行后插入一行"new line"

> i\ 在当前行前边插入文本

> c\ 把当前行改为新文本

> d 删除选择行 `sed '2,5d' file`删除file中的第二到五行，`sed '/^test/d' file` 删除file文件中以test开头的行

> s 替换指定字符 `sed 's/test/Test' file` file文件中用Test替换test

> n 读取下一个输入行，用下一个命令处理新行 `sed '/test/{n; s/aa/bb/;}' file` file文件中包含test的行的下一行用bb替换aa

> p 打印模块的行 `sed -n '/^test/p' file` 仅打印文件中匹配的行

> r file 从file文件中读行 `sed '/test/r file' filename` filename文件中匹配的行读取file文件中的内容添加到改行下边

> w file 写file文件 `sed -n '/test/w file' filename` 将filename中所有满足的行都写到file中

#### 替换标记
> g 标识行内全部替换

> \1 标识匹配的第一个字符串 `sed 's/banana\([0-9]\)/\1' file` 用`banana+数字`的数字替换内容

> & 已匹配字符串标记 `sed 's/^test/&1' file` 用test1替换test
