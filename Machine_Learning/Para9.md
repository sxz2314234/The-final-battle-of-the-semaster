# 第九章: 无监督学习

## 典型的无监督学习问题:

* 聚类

* 特征学习

* 密度估计

## 主成分分析

一种最常用的数据降维方法，使得在转换后的空间中数据的方差最大。

推导目标函数:

1. 样本点$x^{(n)}$投影之后的表示为:
   
   * $z^{(n)}=w^Tx^{(n)} $

2. 所有样本投影后的方差为
   
   * $$
     \sigma(X;w)=\frac{1}{N}\sum^N_{n=1}(w^Tx^{(n)}-w^T\hat{x})\\
=\frac{1}{N}(w^TX-w^T\hat{X}){(w^TX-w^T\hat{X})}^T
=w^TSw
     $$
   
   * 其中$S$是关于数据样本$X$的协方差矩阵

3. 目标函数
   
   * $$
     max\  w^TSw\\
s.t.\ w^Tw=1   
     $$
   
   * 保持$w$为单位向量

4. 引入拉格朗日函数, 使之转变为无约束优化问题( 变量为: $w$ )
   
   * $$
     max\  w^TSw+\lambda (w^Tw-1)
     $$

5. 求解该问题, 只需令该目标函数的梯度为0

## 稀疏编码

**(线性)编码 :** 给定一组基向量A = [a_1 ,··· ,a_M]，将输入样本x 表示为这些基向量的线性组合

<img src="file:///home/sxz/The%20Final%20Battle%20of%20the%20Semester/Machine_Learning/图片1.png" title="" alt="" width="470">

其中$A$称为**字典**, $z$称为**编码**

**稀疏编码 :** 找到一组“过完备”的基向量（即M>D）来进行编码。

稀疏编码特别强调在表示数据时所需的非零系数尽量少，因此得名“稀疏”编码。

<img src="file:///home/sxz/The%20Final%20Battle%20of%20the%20Semester/Machine_Learning/图片2.png" title="" alt="" width="452">

**核心思想 :** 稀疏编码的核心思想是：对于给定的数据$x$，找到一组基向量（称为字典） $D$ 和对应的稀疏系数向量 $a$，使得数据可以用这些基向量的线性组合来近似表示，并且稀疏系数向量 $a$ 尽可能稀疏。

在数学上可以描绘成如下问题:

$$
min_{D,a}\ \Vert x-Da\Vert^2_2+\lambda \Vert a\Vert_1
$$

其中:

- $x$ 是输入数据。
- $D$ 是字典矩阵，每列为一个基向量。
- $a$ 是稀疏系数向量。
- $\Vert x-Da\Vert_2^2$​ 是重建误差项，表示数据 $x$ 和其近似表示 $Da$ 之间的差异。
- $\Vert a\Vert_1$​ 是稀疏正则项，表示稀疏系数向量 $a$ 的$L1$范数，确保稀疏性。
- $\lambda$ 是正则化参数，控制重建误差和稀疏性的权衡。

## 自编码器

主要包含有

* 编码器( Encoder ) : $f:\Bbb{R}^D\rightarrow\Bbb{R}^M$

* 解码器( decoder ) : $g:\Bbb{R}^M\rightarrow\Bbb{R}^D$

目标函数: 最小化重构错误

$$
L=\sum^N_{n=1}\Vert x^{(n)}-g(f(x^{(n)}))\Vert^2
$$

## 稀疏自编码器

通过给自编码器中隐藏层单元z加上稀疏性限制，自编码器可以学习到数据中一些有用的结构。

目标函数 :

![](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/Machine_Learning/图片3.png)

其中 :

* $\Vert*\Vert $是指重构错误

* $\eta$是稀疏超参,$\rho(Z)$是稀疏性衡量函数

* $\Vert W\Vert^2$是权重矩阵的正则化项 

## 聚类
