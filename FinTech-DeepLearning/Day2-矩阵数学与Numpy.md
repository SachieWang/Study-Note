# **矩阵数学与Numpy**&emsp;[[目录]](../README.md)

## 一、矩阵数学相关知识

1. 矩阵的加减法
2. 矩阵的数乘、点乘（及其规则“形状匹配”）
3. 矩阵的转置

>重要点！  
&emsp;&emsp;维度:数组/矩阵的维度

## 二、Numpy

1. `array()函数`&emsp;&emsp;将列表、数组变化为ndarray对象
   >ndarray可存储任意维度的张量，支持快速数学运算
2. ndarray对象的`shape属性`
   >m=np.array([[1,2,3],[4,5,6]])  
m.shape&emsp;&emsp;//outputs:(2,3)
3. ndarray对象的`reshape()函数`
4. ndarray对象`切片语法`
   >m[:,0]&emsp;&emsp;表示取第一维所有元素和第二维第一个元素&emsp;eg：[[1],[4]]  
m[:,1:]&emsp;&emsp;表示取第一维所有和第二维第二个至最后一个元素&emsp;eg：[[2,3],[5,6]]
5. ndarray对象的元素级运算