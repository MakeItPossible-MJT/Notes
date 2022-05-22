# CoConv: Cooperative Dynamic Convolution

n个conv experts，由n维路由向量缩放（这n维路由向量依赖于input）。

每个expert卷积的权重由对应的注意力值缩放，然后聚合为最终的统一权重。

<img src="CoConv%E9%98%85%E8%AF%BB%E7%AC%94%E8%AE%B0.assets/image-20220403155457375.png" alt="image-20220403155457375" style="zoom:80%;" />

卷积可以表示为
$$
Y = W ⊛ X
$$
![](CoConv%E9%98%85%E8%AF%BB%E7%AC%94%E8%AE%B0.assets/image-20220403160707707.png)

所以，传统卷积可以通过这种方式分解为多个并行的卷积运算。

这可以并行训练多个卷积层，并在推理过程中融合它们以提高效率。

<img src="CoConv%E9%98%85%E8%AF%BB%E7%AC%94%E8%AE%B0.assets/image-20220406162803300.png" alt="image-20220406162803300" style="zoom:80%;" />





## potential improvement

但是注意力值的计算依然依赖于已经存在的参数，这也许是ok的。

