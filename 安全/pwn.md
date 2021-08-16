# pwn库

1、打印调试信息

```python
context(os='linux',log_level='debug') #打印调试信息
```

2、连接程序

```python
conn = process('./program') #运行
conn = gdb.debug('./demo', 'break main') #调试连接
# 调试连接程序能开一个终端，运行gdb到断点处，与pwn配合使用，非常强大。
# 如输入可以从pwn中输入，接收字符串也可以从pwn中接收。gdb负责程序的运行和地址有关信息等。
```

3、接收信息

```python
conn.recv()
```

4、发送信息

```python
conn.sendline(payload)
```

5、与程序互动

```python
conn.interactive()
```

6、将地址转为64位小端序

```python
p64(position)
```
