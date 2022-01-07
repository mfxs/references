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

+ **A Clockwork RNN**
> 为了克服RNN在长期记忆时存在的梯度消失或爆炸问题，将RNN中隐层状态分为不同的更新速率组，更新速率快的神经元依赖于更新速率慢的神经元，因此长期依赖关系可以由更新速率慢的神经元保留，可以考虑和软测量中的多速率问题相结合。

+ **Variational Progressive-Transfer Network for Soft Sensing of Multirate Industrial Processes**
> 提出一种处理多速率软测量的迁移模型，首先根据过程变量的采样速率划分为不同的数据块，采用VAE的框架逐步从高速率数据块迁移至低速率数据块，最终得到完整的软测量模型。

+ **P-DIFF+: Improving learning classifier with noisy labels by Noisy Negative Learning loss**
> 提出采用概率差异分布作为反映标签是否纯净的指标，即标签类概率减去其余类别中的最大概率，该指标越大越可能是纯净标签，据此将标签划分为纯净标签和噪声标签，结合NL思想将纯净标签和噪声标签同时用于对分类网络进行训练。

+ **Joint Negative and Positive Learning for Noisy Labels**
> NLNL的改进版本，通过损失函数的修改实现单阶段的快速收敛，并解决NL的欠拟合问题。NL+在NL的基础上引入固定系数项，从而调整了梯度图分布情况（这部分比较难懂），使得有噪声的样本不会由于处在高梯度区域而被挤到和干净样本重叠的区域，更好地实现了两类样本的分离，PL+在PL的基础上首先对干净样本的选取做了更严格的限制，同时也引入固定系数项，使得模型能够更专注于对干净样本的学习，提升收敛速度。

+ **Masked Autoencoders Are Scalable Vision Learners**
> 基于MAE的图像表征学习方法，针对图像数据对patch进行mask，采用不对称的encoder和decoder结构恢复出原图，整体思路很简单，很多trick也是借鉴NLP的方法，不知道牛在哪里。

+ **Time Series Shapelets: A New Primitive for Data Mining**
> 提出一种用于时序数据局部特征提取的方法，首先将所有时序样本中满足长度要求的所有子序列作为Shapelet的候选集，分别计算每个候选子序列和时序样本之间的距离，基于此距离寻找能够将不同类样本划分的最佳分割阈值，类似决策树方法寻找分割后信息增益最大的候选子序列作为Shapelet，为了提高计算效率，提出两种优化技巧：1、采用滑窗方式计算候选子序列和时序样本之间距离时，若此时距离值已超过记录中的最小值时可以提前停止当前计算，将窗口向前滑动；2、计算出候选子序列和部分时序样本之间距离后，若此时所能达到的信息增益上限无法超过已有候选子序列的信息增益则可以提前排除当前候选子序列的计算。在用于时序数据分类任务时，类似于决策树的思想方法，每个结点含有对应Shapelet和距离阈值，根据时序样本和Shapelet之间距离与阈值的关系进入左右子树。

+ **Data-Driven Soft Sensor Design with Multiple-Rate Sampled Data: A Comparative Study**
> 一篇较早的多速率软测量综述文章，将多速率软测量的方法归纳为4类：Numerical Interpolation，Polynomial Transformation，Data Lifting，Weighted PLS。Numerical Interpolation相当于采用上采样将由于多速率采样问题造成的缺失数据进行填补；Polynomial Transformation采用同乘多项式的方法使得参数估计时只使用快速率的过程变量和低速率的质量变量；Data Lifting相当于采用下采样将快速率的过程变量堆叠起来；Weighted PLS感觉像是没有堆叠过程变量直接下采样。

+ **USAD: UnSupervised Anomaly Detection on Multivariate Time**
> 提出一种结合AE和GAN的多变量时间序列异常检测方法。首先构造两个共用编码器的AE，再进行两阶段的训练，第一阶段采用常规重构损失对两个AE训练，第二阶段采用对抗学习的想法，将AE1的重构结果输入至AE2进行重构，AE1尽可能迷惑AE2无法判断输入的是原始数据还是重构数据，而AE2尽可能辨别是原始输入还是重构输入，最终根据两个AE得出的异常分数加权求和判断是否异常。通过两个AE对抗学习的方式能够放大异常和正常数据之间的差异。

+ **Deep Forest: Towards an Alternative to Deep Neural Networks**
> 提出一种利用随机森林实现深度模型的方法，本质上使用随机森林替代传统神经网络中的神经元，同时结合了许多深度学习的技巧，如Resnet、ELM、多尺度等，并且能够通过交叉验证方式自适应选择层数，控制模型复杂度。

+ **Feature-aligned Stacked Autoencoder: A Novel Semi-supervised Deep Learning Model for Pattern Classification of Industrial Faults**
> 基于“预训练+微调”的半监督故障诊断问题，提出结合无标签样本伪标签信息，利用Sinkhorn距离将同类别有标签样本和无标签样本分布对齐。

+ **Reconstruction-based Anomaly Detection with Completely Random Forest**
> 提出一种基于完全随机森林的重构异常检测方法，根据每棵决策树所给出bounding box的交集，计算得到重构样本，根据重构误差大小判断样本是否发生异常。相较于基于自编码器的异常检测方法，训练效率更高，超参数更少。