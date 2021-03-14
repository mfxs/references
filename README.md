# References

+ **Refining activation downsampling with SoftPool**
> 提出一种基于softmax的池化方式，利用softmax函数计算感受野中每个元素的权重，再对感受野内元素进行加权求和，梯度反向传播时同样采用相同权重进行运算。

+ **Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning**
> 本文通过理论推导证明了含有dropout的任意神经网络近似等价于深度高斯过程，从而推导得出在含有dropout的神经网络框架下计算输出不确定性只需要随机多次前向传播，样本方差即可描述不确定性。

+ **NLNL: Negative Learning for Noisy Labels**
> 由于标签通常可能存在噪声，因此基于传统标签的方式容易受噪声影响。为此提出采用互补标签，即该样本不属于哪一类，通过修改交叉熵损失函数实现利用互补标签进行负学习。为了消除噪声严重样本的影响，以及利用传统正学习方式，在此基础上增加选择性负学习和选择性正学习，通过设定阈值以筛选标签更可靠的样本。