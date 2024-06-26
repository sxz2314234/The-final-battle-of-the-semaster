# 第五章: 迭代算法框架(一)

## 无约束优化算法的基本框架

寻找一个极小化序列$x^{(k)}\in domf ,k=0,1,..., $使得$f(x^{(k)})\rightarrow p^*=f(x^{(*)})=inff(x) $

可以看作是迭代求解: $\nabla f(x^*)=0 $

**三要素**:

* 初始解 : 恰当的$x^{(0)}$
  
  * 初始解属于目标函数的定义域
  
  * 下水平集是闭集,即
    
    * $S\in \{x\in domf|f(x)\le f(x^{(0)})\} $

* 更新机制
  
  * 常见的更新方法是: $x^{(k+1)}=x^{(k)}+t^{(k)}\Delta x^{(k)} $
  
  * 搜索方向是: $\Delta x^{(k)}\in R^{(n)} $
  
  * 步长: $t^{(k)}\in R$

* 收敛条件( 若函数是强凸的 )
  
  * $f(x)-p^*\le \frac{1}{2m}\Vert\nabla f(x)\Vert^2_2 $

### 强凸函数的定义

若一个凸函数满足$f(y)\ge f(x)+\nabla f(x)^T(y-x)+\frac{1}{2}\Vert y-x\Vert^2 $

则这个函数是强凸的.

**强凸函数的性质 :**

1. **唯一最小值**：强凸函数在其定义域内具有唯一的最小值点。

2. **更快的收敛速度**：在优化问题中，许多迭代算法对强凸函数的收敛速度更快，通常可以达到线性收敛或更快。

3. **二阶导数**：如果 f 是二次可微的，那么强凸性等价于其 Hessian 矩阵 ∇2f(x) 满足：
   
   $∇^2f(x)⪰mI$
   
   这里 I 是单位矩阵，⪰ 表示大于等于在半正定矩阵的意义上。

## 下降的方法

**基本框架的伪代码**

给定 : 初始解$x^{(0)}\in domf $

重复:

1. 确定下降方向$\Delta x $

2. 直线搜索: 确定步长$t>0$

3. 更新: $x:=x+t\Delta x $

直至: 满足终止条件

**基本的下降算法**

* 梯度下降法
  
  * 其方向是: 函数的负梯度方向

* 最速下降法
  
  * 其方式是在某个单位范数球中找到最小的$\nabla f(x)^T v $其中$\Vert v\Vert=1 $

* 牛顿法
  
  * 其方向是$\nabla x_{nt}=-\nabla^2f(x)^{-1}\nabla f(x) $

### 牛顿法

[[最优化方法笔记] 牛顿法与修正牛顿法 - MarisaMagic - 博客园](https://www.cnblogs.com/MarisaMagic/p/17904136.html)
