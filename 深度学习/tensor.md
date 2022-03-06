# tensor基本操作

## 创建张量

```python
torch.arange(n) # 产生0~n的序列张量
x.shape # 输出张量的形状
x.numel() # 元素总数
X=x.reshape(a, b) # 改变张量形状为a,b，如果a是-1，会根据b自动计算a
troch.zeros((a, b, c)) # 全0张量
torch.ones((a, b, c)) # 全1张量
torch.randn(a, b, c) # 正态分布张量
torch.tensor([[1,2,3],[4,5,6]]) # 一个确定数值的张量
```

## 运算符

```python
+ - * / ** # 加减乘除，求幂 按元素
exp(x) # 以e为底求幂
torch.cat((X,Y),dim=0) # 按行连接
torch.cat((X,y),dim=1) # 按列连接
X.sum() # 对张量求和
> == < # 按元素比较，生成张量
```

