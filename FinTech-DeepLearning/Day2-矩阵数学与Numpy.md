# **矩阵数学与Numpy**&emsp;[[目录]](../README.md)

## 一、矩阵数学相关知识

1. 矩阵的加减法
2. 矩阵的数乘、点乘（及其规则“形状匹配”）
3. 矩阵的转置

>重要点！  
&emsp;&emsp;维度:数组/矩阵的维度

## 二、Numpy库

1. `array()函数`&emsp;&emsp;将列表、数组变化为ndarray对象
   >ndarray可存储任意维度的张量，支持快速数学运算
2. ndarray对象的`shape属性`
   >m=np.array([[1,2,3],[4,5,6]])&emsp;`//np来源 import numpy as np`  
m.shape&emsp;&emsp;//outputs：(2,3)  
m.shape[1]&emsp;&emsp;//putputs：3
3. ndarray对象的`reshape()函数`
4. ndarray对象`切片语法`
   >m[:,0]&emsp;&emsp;表示取第一维所有元素和第二维第一个元素&emsp;eg：[[1],[4]]  
m[:,1:]&emsp;&emsp;表示取第一维所有和第二维第二个至最后一个元素&emsp;eg：[[2,3],[5,6]]
5. ndarray对象的元素级运算  
利用ndarray对象与+、-、*、/进行运算符运算
   >可直接运算&emsp;&emsp;技巧：若想将列表[1,2,3,4]中每个元素加5，不必使用for循环，可直接`np.array([1,2,3,4])+5`，利用ndarray对象实现元素级快速数学运算
6. ndarray元素级乘法运算  
通过`np.multiply(ndarrayObj,ndarrayObj)`函数实现  
注意！实现的是 ***元素级*** 运算，而非矩阵运算
7. ndarray矩阵乘法  
通过`np.matmul(ndarrayObj,ndarrayObj)`函数实现  
注意！两矩阵应满足形状兼容&emsp;例如3x**2**矩阵与**2**x4矩阵为形状兼容，2x**3**矩阵与**4**x2矩阵则不兼容，会报错
8. ndarray矩阵转置  
方法一：调用对象T属性&emsp;&emsp;eg：m.T  
方法二：调用transpose()函数，但比较少用
9. np.min(ndarrayObj)函数  
作用：找出ndarray中最小值
10. np.max(ndarrayObj)函数  
作用：找出ndarray中最大值
11. np.mean(ndarrayObj)函数  
作用：算出ndarray的平均值