# 对抗地址空间随机化(ALSR)

1、通过jmp esp，将shellcode写到返回地址上边，返回地址写有jmp esp(0xffe4)的地址上。

2、把shellcode注入到全局变量上，把返回值改为全局变量的地址。
