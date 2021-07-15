# SHELL SCRIPT

1、向文件末尾添加一行数据

```bash
echo "text" >> info.txt
```

如果是覆盖之前的数据

```bash
echo "text" > info.txt
```

2、向文件的某行添加数据



3、循环

```bash
#!/bin/bash

count=1

echo "这是一个执行${1}.c的循环"

while [ 1 ]
do
	echo "第${count}次:"
	./$1
	echo ""
	count=$((${count}+1))
done
```

