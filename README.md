# References

+ **Refining activation downsampling with SoftPool**
> 提出一种基于softmax的池化方式，利用softmax函数计算感受野中每个元素的权重，再对感受野内元素进行加权求和，梯度反向传播时同样采用相同权重进行运算。