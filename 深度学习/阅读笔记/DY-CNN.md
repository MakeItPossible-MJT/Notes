# DY-CNN

<img src="DY-CNN.assets/image-20220406144922453.png" alt="image-20220406144922453" style="zoom:80%;" />

相较于CondConv，改变了计算attention的方法。

##### 1、对注意力值归一化处理

##### 2、将Softmax中的温度参数变大，以尽可能训练号每一个卷积层，然后逐渐降低温度参数。