# 第一章

## 1.最优化的一般形式

![一般形式](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-28_19-52.png)

## 2.范数的基本概念

注: 下图为一些常见的范数

![方向导数与梯度](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-28_19-53.png)

由此引出向量范数:

![向量范数](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-28_19-54.png)

## 3.方向导数与梯度

![方向导数与梯度](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-28_19-56.png)

![方向导数与梯度](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-28_19-57.png)

### Hessi矩阵:

![海瑟矩阵](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-28_19-58.png)

## 4.凸集与凸函数

### 凸集的定义

如果连接集合C中的任意两点的线段都在C内,则称C为**凸集**,即

$x_1,x_2\in C \Rightarrow \theta x_1 + ( 1- \theta )x_2 \in C, 0 \leqslant \theta \leqslant 1 $

注: 在$R^n$ 空间中,经过不同的两点$x_1 ,x_2 $ 可以确定一条直线, 其方程为 

$y=\theta x_1 + (1- \theta)x_2, \theta \in \Bbb{R} $

**仿射集定义** : 即为上述凸集定义中的$ \theta \in \Bbb{R} $

### 凸集的性质

**定理** 

* 若$S$是凸集, 则$ kS=\{ks|k \in \Bbb{R}, s \in S \} $ 是凸集.

* 若$S$和$T$均是凸集,则$S+T=\{s+t|s \in S, t\in T \} $ 是凸集.

* 若$S$和$T$均是凸集, 则$S \cap T$ 也是凸集.

* 凸集的内部和闭包都是凸集.

### 凸组合和凸包

**凸组合定义** : 形如

$ x=\theta_1 x_1 +\theta_2 x_2+...+ \theta_k x_k  $

其中, $ \theta_1+\theta_2+...+\theta_k=1,\theta_i \geqslant 0 , i=1,...,k$

的点称为$x_1,...,x_k$的凸组合.

**凸包的定义** : 集合$S$的所有点的凸组合构成的点集为$S$的凸包,记为$convS$

**定理1** : 若$convS \subseteq S $ 则$S$是凸集; 反之亦然.**(凸集与凸包的关系)**

**定理2** : $convS$是包含$S$的最小凸集.

### 仿射包与仿射组合

其定义与凸包与凸组合相同,不同的是$\theta$的取值是任意实数.

在几何意义上,仿射包$S$(affine$S$)是包含集合$S$的全平面.

![](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_08-49.png)

### 锥组合与凸锥

**锥组合的定义** : 形如

$ x=\theta_1 x_1+...+\theta_k x_k,\theta_i>0(i=1,...,k). $

的点称为$ x_1,...,x_k $的锥组合.

**凸锥的定义** : 若集合$S$中任意点的锥组合都在S中,则称$S$为凸锥.

## 重要的凸集举例

### 超平面与半空间

**超平面的定义** : 任取非零向量$ a\in \Bbb{R}^n,$形如$\{x|a^Tx=b\} $的集合称为超平面.

**半空间的定义** :  任取非零向量$a\in \Bbb{R}^n$,形如$\{x|a^Tx\leqslant b\} $的集合称为半空间.

![2024-05-30_09-05.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_09-05.png)

### 多面体

我们把满足线性等式和不等式组的点的集合称为多面体,即$ \{x|Ax\leqslant b,Cx=d\}, $

其中$ A\in \Bbb{R}^{m\times n},C\in \Bbb{R}^{p\times n},x\leqslant y $表示向量$x$的每个分量都小于等于$y$的对应分量.

多面体是有限个半空间和超平面的交, 因此由凸集的性质可知, 其为凸集.

### 范数球与椭球

**球的定义** : 设空间中到某一定点$x_c$(称为中心)的距离小于等于定值$r$(称为半径)的点的集合为(范数)球, 即

$ B(x_c,r)=\{x|\ ||x-x_c||\ \leqslant r\}=\{x_c+ru|\ ||u||\leqslant 1 \}$

一般而言,我们使用$||.||_2$度量距离,即使用2-范数球.

**椭球的定义** : 设形如

$ \{x|(x-x_c)^TP^{-1}(x-x_c) \leqslant1\}=\{x_c+Au|\ ||u||_2\leqslant1\} $

的集合为椭球,其中$x_c$为椭球中心,$P$对称正定,且$A$非奇异( 行列式不等于0 )

### 范数锥

球和椭球的范围取决于x的范围, 而锥的范围则同时取决于x和控制径t的范围.

**范数锥的定义** : 形如

$ \{(x,t)|\ ||x||\leqslant t\} $

的集合为范数锥.

### 特殊矩阵集合和(半)正定锥

**对称矩阵集合** : 记$S^n$为$n\times n$对称矩阵的集合, 即

$ S^n=\{X\in \Bbb{R}^{n\times n}|X^T=X\}. $

**半正定矩阵集合** : 记$S^n_+$为$n\times n$半正定矩阵的集合,即

$S^n_+=\{X\in S^n|X\geqslant 0 \}.$

**正定矩阵集合** : 记为$S^n_{++}$

![2024-05-30_09-55.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_09-55.png)

## 保凸运算

### 仿射变换

仿射变换( 缩放, 平移,投影等 )也是保凸的.

设$f: \Bbb{R}^n\rightarrow \Bbb{R}^m$是仿射变换,即$f(x)=Ax+b,A\in\Bbb{R}^{m\times n},b\in \Bbb{R}^m,$则

凸集在$f$下的像是凸集

凸集在$f$下的原像是凸集

![2024-05-30_10-11.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_10-11.png)

### 透视变换和分式线性变换的保凸性

**透视变换**:$P: \Bbb{R}^{n+1}\rightarrow \Bbb{R}:P(x,t)=x/t,domP=\{(x,t)|t>0\}$

透视变换下凸集的像和原像是凸集.

**分式线性变换**:$ f: \Bbb{R}^n\rightarrow \Bbb{R}^m:f(x)= \frac{Ax+b}{c^Tx+d},domf=\{x|c^T+d>0\}  $

分式线性变换的像与原像是凸集

## 广义不等式与对偶锥

### 适当锥

我们知道锥是凸集.一个凸锥$K\subseteq \Bbb{R}^n$是适当锥,当其还满足

* $K$是闭集;

* $K$是实心的,即$intK\neq \varnothing ;$

* $K$是尖的,即内部不含有直线;若$ x\in K,-x\in K, $则一定有$x=0.$

![2024-05-30_10-35.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_10-35.png)

### 广义不等式

广义不等式是一种偏序(不必要保证所有对象都具有可比较性)关系，
可以使用适当锥诱导.

**广义不等式** : 对于适当锥$K$,定义偏序广义不等式为

$ x\le _Ky \leftrightarrow y-x\in K, $

**严格偏序广义不等式** 

$ x\le _Ky \leftrightarrow y-x\in intK, $

![2024-05-30_10-46.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_10-46.png)

**广义不等式的性质**:

![2024-05-30_10-47.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_10-47.png)

### 对偶锥

设$K$是一个锥

**定义** : 令锥$K$为全空间$\Omega$的子集,则$K$的对偶锥为

$ K^*=\{y\in \Omega|<x,y>\geqslant0,\forall x\in K .$<x,y>表示x与y的内积

![2024-05-30_10-57.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_10-57.png)

## 分离超平面

超平面是空间中一类特殊的凸集(仿射集), 可以证明Rn空间中的超平面恰好是n − 1维的. 我们可以用超平面分离不相交的凸集.

**分离超平面定理** : 如果$C$和$D$是不相交的凸集, 则存在非零向量$a$和常
数$b$, 使得

$ a^T \leqslant b,\forall x\in C, $且

$ a^Tx\geqslant b,\forall x\in D, $ 

即超平面$ \{x|a^Tx=b\} $分离了$C$和$D$.

![2024-05-30_11-07.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_11-07.png)

![2024-05-30_11-08.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_11-08.png)

**严格分离超平面定理**要求小于或大于不包含等于的情况.

### 支撑超平面

上述严格分离定理的退化形式要求$x_0\notin C$ . 当点$x_0$恰好落在C的边界上
时(此时不满足"不相交"的条件), 我们可以构造超平面.

**定义** : 给定集合$C$以及边界上的点$x_0$, 如果$a\neq0$满
足$ a^T \leqslant a^Tx_0,\forall x\in C, $ 那么称集合
$ \{x|a^Tx=a^Tx_0\} $

为C在边界点$x_0$处的支撑超平面.

根据定义, 点$x_0$和集合$C$也被该超平面分开.
从集合上而言, 超平面$\{x|a^Tx=a^Tx_0\} $与集合C在点x0处相切, 并且半空
间$\{x|a^T\leqslant a^Tx_0 \}$包含C.

注意根据凸集成立的分离超平面定理, 凸集上任何的边界点都满足支撑
超平面存在的条件, 则对于凸集成立如下的定理.

**支撑超平面定理** : 若$C$是凸集, 则$C$的任意边界点处都存在支撑超平面.

支撑超平面定理有非常强的几何直观: 给定一个平面后,可把凸集边界上的任意一点
当成支撑点, 将凸集放在该平面上.
这也是凸集的特殊性质, 一般的集合甚至无法保证存在平面上的支撑点.

![2024-05-30_11-30.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/The_theory_of_optimization/1.Convex/2024-05-30_11-30.png)
