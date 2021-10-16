# Vim

1、编辑多文件

```bash
:n #编辑下一个
:N #编辑上一个
```

2、多窗口编辑文件

```bash
:sp file #打开file，上下显示
vim -ON file1, file2 #左右显示
vim -oN file1, file2 #左右显示
```

3、在vim中执行shell命令

```bash
:!command
```

4、滚动屏幕

```bash
ctrl + e #向下滚动一行
ctrl + y #向上滚动一行
ctrl + d #向下滚动半页
ctrl + u #向上滚动半页
ctrl + f #向上滚动一页
ctrl + b #向上滚动一页
```

5、替换字符串

```bash
:%s/word1/word2/gc
# %是从第1行到最后一行，也可以用1,$代替
# g是替换每一行的所有匹配的单词，比如第1行有word1word1,加了g选项，两个word1都会被替换，不加word1只会替换第1个。
# c是用来确认的，对于每一个匹配到的word1,会让你确认需不需要替换。
# 如果word中带有/符号，那么可以把分隔符改为#，
#比如把hello/替换为world/，:%s#hello/#world/#g 
```

```bash
# linux和windows换行的符号区别
# linux是回车(0x0A)，windows是回车换行(0x0A0D)
# 0x0D表现为^M，有时需要去掉它，可以用如下命令：
:%s/^M$//g
```

