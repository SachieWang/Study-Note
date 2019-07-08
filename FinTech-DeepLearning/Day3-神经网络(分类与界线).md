# **神经网络（分类与界线）**&emsp;[[目录]](../README.md)

```txt

神经网络是ML中的一个模型用于分类与回归两类问题的解答
·分类   把数据划归为不同的类别
·回归   建立数据间的连续关系
·为啥叫神经网络？由若干感知器连接（上一个输出==>>下一个输入）（组成逻辑网状结构？？？）
```

## 一、分类

1. **概念：** 通过样本输入数据进行运算，依据结果将样本划归进不同类

## 二、界线

1. **概念：** 进行样本分类的标准（分类函数）

## 三、感知器--神经网络的基础构成组件

1. **概念：** 一个感知器对应一个分类标准（分类函数）
2. **寻找最优感知器原理：** 数据集中每一个点都会把分类结果提供给感知器，并调整感知器。
3. **调整感知器基本方式：** 利用数据集中分类错误的点的值配以偏置单元,  
通过$+-$运算改变weight与bias，调整界线位置
   >通常这种方式会使界线剧烈调整，影响其他点的分类，故引入学习速率$\alpha$，控制调整的“步长”，使界线慢慢向最佳位置靠近
4. **感知器算法**
   ```python
   import numpy as np
   # Setting the random seed, feel free to change it and see different solutions.
   np.random.seed(42)

   def stepFunction(t):
      if t >= 0:
         return 1
      return 0

   def prediction(X, W, b):
      return stepFunction((np.matmul(X,W)+b)[0])

   # TODO: Fill in the code below to implement the perceptron trick.
   # The function should receive as inputs the data X, the labels y,
   # the weights W (as an array), and the bias b,
   # update the weights and bias W, b, according to the perceptron algorithm,
   # and return W and b.
   def perceptronStep(X, y, W, b, learn_rate = 0.01):
       # Fill in code
      for i in range(len(X)):
         y_hat = prediction(X[i],W,b)
         if y[i]-y_hat == 1:
            W[0] += X[i][0]*learn_rate
            W[1] += X[i][1]*learn_rate
            b += learn_rate
         elif y[i]-y_hat == -1:
            W[0] -= X[i][0]*learn_rate
            W[1] -= X[i][1]*learn_rate
            b -= learn_rate
      return W, b
    
   # This function runs the perceptron algorithm repeatedly on the dataset,
   # and returns a few of the boundary lines obtained in the iterations,
   # for plotting purposes.
   # Feel free to play with the learning rate and the num_epochs,
   # and see your results plotted below.
   def trainPerceptronAlgorithm(X, y, learn_rate = 0.01, num_epochs = 25):
      x_min, x_max = min(X.T[0]), max(X.T[0])
      y_min, y_max = min(X.T[1]), max(X.T[1])
      W = np.array(np.random.rand(2,1))
      b = np.random.rand(1)[0] + x_max
      # These are the solution lines that get plotted below.
      boundary_lines = []
      for i in range(num_epochs):
         # In each epoch, we apply the perceptron step.
         W, b = perceptronStep(X, y, W, b, learn_rate)
         boundary_lines.append((-W[0]/W[1], -b/W[1]))
      return boundary_lines
   ```

## 四、误差函数

1. **概念：** 通过每一个错误分类的点，评估错误点位置与我们期望位置之间的差异，来慢慢的修正我们分类函数。因为误差暗示了如何进行正确的分类，因此误差的定义就变得尤为重要，这也被称为误差函数。
2. **作用：** 提供预测值与期望值之间的差异，以指导权重的更新

## 五、梯度下降
1. **概念：** 通过局部最小值调整，进行步进修改，以找到最优值的方式叫梯度下降（步长由导数计算得来）
2. **前提：** 误差函数必须是连续函数而非阶跃函数（误差函数可微分）

>如何将阶跃函数转变为连续函数？  
