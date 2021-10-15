# gdb

1、下断点

```bash
b main
```

2、运行

```bash
r < input.txt
```

3、单步执行

```bash
n # 不进入函数 nexti
s # 进入函数 stepi
f # 执行完函数 finish
```

4、查询函数地址

```bash
info address func
# 这个info有很多作用
info registers # 查看寄存器的值
```

5、查询地址向上增长的内容

```bash
x/nfu addr #以f格式打印从addr开始的n个长度单元为u的内存值
# f:x:十六进制，o:8进制
# u:b:byte，h:两个byte，w：四个byte，g：八个byte
```

6、列出所有的函数

```bash
gdb functions (regex)
# reges可选，可列出符合正则表达式的函数名
```

