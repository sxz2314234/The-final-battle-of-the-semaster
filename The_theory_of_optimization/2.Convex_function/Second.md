# 二. 凸函数

## 基础知识

### 矩阵变量函数的导数

多元函数梯度的定义可以推广到变量是矩阵的情形. 对于以$ m\times n $矩阵$X$为自变量的函数$f(x)$,若存在矩阵$G \in \Bbb{R}^{m\times n} $满足

$\lim_{V\to 0}\frac{f(X+V)-f(X)-<G,V>}{\Vert V\Vert} =0$

其中$\Vert .\Vert$是任意矩阵范数,就称矩阵变量函数$f$在$X$处$Frechet$可微,$G$为$f$在$Frechet$可微意义下的梯度. 令$\frac {\partial f}{\partial x} $表示$f$关于$x_{ij}$的偏导数.则矩阵变量的函数$f(X)$的梯度为海瑟矩阵.

**等价定义: $Gateaux$可微**

设$ f(X) $为矩阵变量函数,如果对任意方向$ V\in \Bbb{m\times n} $,存在矩阵$ G\in\Bbb{R}^{m\times n} $满足

$ \lim_{t\to 0}\frac{f(X+tV)-f(X)-t<G,V>}{t} =0 $

则称$f $关于$X$是$Gateaux$可微的.

### 广义实值函数与适当函数

![2024-05-31_10-09.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-05-31_10-09.png)

### 下水平集与上方图

![2024-05-31_10-10.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-05-31_10-10.png)

### 下半连续函数

等价定义: 对于$\forall \xi>0$都存在$x_0$的开邻域$U(x_0)$使得

$ \forall x\in U(x_0),f(x)>f(x_0)-\xi $

**这保证了下半连续函数不会突然减小到某一值.**

![2024-05-31_10-53.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-05-31_10-53.png)

### 闭函数与下半连续函数

![2024-05-31_10-54.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-05-31_10-54.png)

## 凸函数的定义与性质

![2024-05-31_11-05.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-05-31_11-05.png)

### 一元凸函数的例子:

![2024-05-31_13-05.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-05-31_13-05.png)

### 多元凸函数的例子

![2024-06-01_06-58.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_06-58.png)

### 凸函数判定定理( 判定凸函数的方法 )

**方法一:** 由凸函数的定义导出

**方法二**: 一阶条件( 凸函数的某一点切线的取值总小于该凸函数上的取值 )

![2024-06-01_07-09.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-09.png)**方法三**: 梯度单调性

![2024-06-01_07-12.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-12.png)**方法四**: 上方图

![2024-06-01_07-20.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-20.png)

**方法五**: 二阶条件

![2024-06-01_07-21.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-21.png)

## 保凸运算

验证一个函数是否为凸函数,除了上述通过定理证明之外,还可通过一些简单的凸函数进行保凸运算得到:

* 非负加权和

* 与仿射函数的复合

* 逐点取最大值

* 与标量, 向量函数复合

* 取下确界

* 透视函数

### 非负加权和与仿射函数的复合

![2024-06-01_07-29.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-29.png)

### 逐点取最大值

![2024-06-01_07-38.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-38.png)

### 与标量函数的复合

![2024-06-01_07-58.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_07-58.png)

注: 函数$h$上带一个 ~ 应该是函数$h$的对偶函数  

### 与向量函数的复合

![2024-06-01_08-00.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_08-00.png)

### 透视函数

![2024-06-01_08-03.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/2.Convex_function/2024-06-01_08-03.png)
