# References

+ **Refining activation downsampling with SoftPool**
> 提出一种基于softmax的池化方式，利用softmax函数计算感受野中每个元素的权重，再对感受野内元素进行加权求和，梯度反向传播时同样采用相同权重进行运算。

+ **Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning**
> 本文通过理论推导证明了含有dropout的任意神经网络近似等价于深度高斯过程，从而推导得出在含有dropout的神经网络框架下计算输出不确定性只需要随机多次前向传播，样本方差即可描述不确定性。

+ **NLNL: Negative Learning for Noisy Labels**
> 由于标签通常可能存在噪声，因此基于传统标签的方式容易受噪声影响。为此提出采用互补标签，即该样本不属于哪一类，通过修改交叉熵损失函数实现利用互补标签进行负学习。为了消除噪声严重样本的影响，以及利用传统正学习方式，在此基础上增加选择性负学习和选择性正学习，通过设定阈值以筛选标签更可靠的样本。

+ **在线鲁棒最小二乘支持向量机回归建模**
> 为克服离群点对LSSVR建模的影响，首先建立常规的LSSVR模型，根据误差分布情况自适应设定鲁棒代价函数中的参数，再通过梯度下降对LSSVR模型中的权值$\alpha$进行更新，从而能够限制离群点对模型的影响，提升模型鲁棒性。同时实现模型的增量学习使其能够在线更新。

+ **Weighted least squares support vector machines: robustness and sparse approximation**
> 提出一种加权版本的LSSVR，首先建立常规的LSSVR模型，根据误差对损失函数中每个样本的误差项赋予权重，误差越大权重越小，进而求解加权版本的LSSVR，能够使得模型不再关注离群点的信息。同时为了保留SVR中模型权值$\alpha$的稀疏性特点，提出一种剪枝策略，在训练得到加权版本的LSSVR后去除一些较小权值对应的样本，从而实现稀疏化的目的。