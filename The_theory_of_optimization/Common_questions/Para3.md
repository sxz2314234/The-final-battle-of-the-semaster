# 常见的优化问题

***注意 : 此章节重点在于介绍各类常见的凸优化问题,并未介绍相应的解法,因此不需要过分纠结. 只需要了解各种描述凸优化问题的形式即可***



![2024-06-03_07-35.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_07-35.png)

## 1.凸优化

### 定理: 凸优化问题的任意局部极小点都是全局最优.

![2024-06-03_08-16.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_08-16.png)

### 可微凸优化问题的最优性条件

![2024-06-03_08-22.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_08-22.png)

![2024-06-03_08-22_1.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_08-22_1.png)

## 线性规划

![2024-06-03_09-57.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_09-57.png)

## 二次规划

![2024-06-03_09-58.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_09-58.png)

## 带有二次约束的二次规划问题(QCQP)

![2024-06-03_09-59.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Common_questions/2024-06-03_09-59.png)

## 几何规划

### 基本形式:

$$
minimize f_0(x)\\
subject\ to\ f_i(x)\le1,\ i=1,2,3...,m\\
x>0
$$

其中,目标函数$f_0(x)$和约束函数$f_i(x)$都是posynomial函数.

### Posynomial函数

Posynomial函数是几何规划中的核心概念，它是由多个单项式（monomial）之和构成的函数。一个单项式的形式为：

$$
cx_1^{a_1}x_2^{a_2}...x_m^{a_m}
$$

其中:

* c>0是一个正系数

* $x_i$是决策变量

* $a_i$是实数指数

一个posynomial函数是多个单项式的和：

$$
f(x)=\sum^K_{k=1}c_kx_1^{a_1k}x_2^{a_2k}...x_n^{a_nk}
$$

## 半定规划

当$K$为$S^k_+$时,即$k\times k$半正定锥时,如下形式的优化问题称为半定规划(SDP):

$$
min\ c^Tx\\
s.t.\ x_1F1+x_2F2+...+x_nFn+G\le0\\
Ax=b
$$

其中,$G, F1, F2..., Fn\in S^k_+,A\in R^{p\times n}$

**二阶锥规划(SOCP)**

$$
min\ f^Tx\\
s.t.\ \Vert A_ix+b_i\Vert_2\le c_i^Tx+d_i,i=1,2,..,n
$$

## 多目标优化( 也称: 向量优化 )

同时优化多个目标函数,寻求最优解.

但是各目标函数之间往往存在矛盾, 因此几乎不存在全局最优的最优解.

我们一般根据具体需求,寻找满足某些目标函数的Pareto解

一般的解法是**权重法**:

将所有目标函数线性组合成一个单一的目标函数，使用不同的权重组合来生成不同的Pareto解。

$$
f(x)=\sum_{i=1}^kw_if_i(x)
$$

其中,$w_i$是第i个目标的权重,且$\sum^k_{i=1}w_i=1.$
