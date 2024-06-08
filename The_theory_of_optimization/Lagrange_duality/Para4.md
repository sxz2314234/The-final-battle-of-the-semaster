# 第四章: 拉格朗日对偶

## 拉格朗日函数

对于任意的优化问题( 不要求凸 ):

$$
min\ f_0(x)\\
s.t.\ f_i(x)\leq 0,\ i=1,2,...,m\\
h_i(x)=0,j=1,2,...,p
$$

其拉格朗日函数$L : R^n\times R^m\times R^p\rightarrow R$, 定义为

$$
L(x,\lambda,v)=f_0(x)+\sum^m_{i=1}\lambda_if_i(x)+\sum^p_{j=1}v_ih_j(x)
$$

可以看作是目标函数和约束函数的加权和

## 对偶函数

对偶函数是对拉格朗日函数在$x\in X$中对$x$取下确界

因此对偶函数一定是凹函数

大概的思路就是对偶函数中最小化之后x已经是个定值，此时对偶函数g(λ,ν)是相对于变量λ,ν的一簇仿射函数，仿射函数是既凹又凸的，那么就利用其凹性，一簇仿射函数的下界就是一个凹函数。  
也可以从下图直观的看出：

![2024-06-06_10-53.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Lagrange_duality/2024-06-06_10-53.png)

**证明 : 不论目标函数与优化条件是否为凸, 其对偶函数一定是凹函数.**

![2024-06-07_11-04.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Lagrange_duality/2024-06-07_11-04.png)

公式(5)到公式(6),由于线性函数既凸又凹,这里就利用其凹性.

**定理 :**

对偶函数的最优解$\le$原函数最优解

$$
\forall \lambda_i\ge 0,\forall v,\ g(\lambda,v)\le P^*
$$

## 对偶问题

$$
max\ g(\lambda,v)=max\ min_{(x)}L(x,\lambda,v)
$$

**对偶函数**是从拉格朗日函数转换过来的，只跟λ,ν相关的函数，不是一个问题（不需要得到最值什么的）

**对偶问题**利用对偶函数一定≤原问题最优解的性质,进而去求解对偶函数的最大值$D^*$,将原问题通过对偶函数（凹函数）转化为求解对偶问题（凸优化问题）

## 为什么费劲周折的去转化成对偶问题呢?

因为无论原问题是否为凸优化问题，转化成的对偶问题**一定是凸优化问题**

并且由凸优化问题的特性: 局部最优解为全局最优解.

**举个例子** :

例子: 带等式约束的最小二乘问题, 形式如下:

$$
min\ x^Tx\\
s.t.\ Ax=b
$$

* 其拉格朗日函数为: $L(x,v)=x^Tx+v^T(Ax-b) $

* 最小化: $\nabla_xL(x,v)=2x+A^Tv=0, \implies x=-(1/2)A^Tv$

* 对偶函数为:$g(v)=L((-1/2)A^Tv,v)=-\frac{1}{4}v^TAA^Tv-b^Tv $

## 强对偶与弱对偶

**弱对偶** : 对偶函数的最优解$\le$原问题的最优解

* 始终成立: 无论原问题是否为凸

* 可以用来求解复杂问题原问题的下界

**强对偶** :对偶函数的最优解=原问题的最优解

* 通常不成立

* 若原问题为凸,通常是成立的,需要满足" 约束规范性条件 "

## 约束规范性条件

![2024-06-06_11-23.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Lagrange_duality/2024-06-06_11-23.png)

例子:

![](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/Lagrange_duality/2024-06-06_11-24.png)

## KKT条件

1. 解$x^*$必须满足所有约束条件

2. 构造拉格朗日函数, 并且在$x^*$处关于$x$的偏导为0

3. 对于每个不等式约束$g_i(x),$对应的拉格朗日乘子$\lambda_i$和约束函数值$g_i(x^*)$之间满足互补条件: $\lambda_ig_i(x^*)=0 $

4. 拉格朗日乘子非负$\lambda_i\ge0$
