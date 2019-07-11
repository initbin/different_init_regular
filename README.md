# different_init_regular
实验不同初始化参数、正则化方式的影响
## Installation
  * python 3.7
  * jupyter notebok
  * matplotlib
  * numpy
  * sklearn
## datasets
[data.mat](https://pan.baidu.com/s/1RpFw2E1HHLOL6WpUZc5QFQ) 提取密码：mp2q

## result
L2正则化的结果  
![result_L2](https://github.com/initbin/different_init_regular/blob/master/result_L2.png)  
dropout的结果  
![result](https://github.com/initbin/different_init_regular/blob/master/result_dropout.png)
## learning
L2正则化是在成本函数中增加一项L2范数，会改变成本的计算，以及后向传播  
Dropout是随机失活，一般是在神经元较密集的层采用，神经元较少的层不采用，通过一个超参数keep_prob进行控制。失活率为1-keep_prob。会改变前向传播和后向传播。  
  1.初始化矩阵D1 = np.random.rand(..., ...)和Al相同维度，其数都是0-1之间的D1 = np.random.rand(A1.shape[0], A1.shape[1])  
  2.将D1的值转换为0或1（使用keep_prob作为阈值 D1 = D1 < keep_prob  
  3.舍弃A1的一些节点（将它的值变为0或False）A1 = A1 * D1  
  4.缩放未舍弃的节点(不为0)的值 A1 = A1 / keep_prob
