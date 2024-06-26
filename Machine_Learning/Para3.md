# 第三章: 线性模型

## 二分类扩展至多分类:

**一对其余:**

![2024-06-03_18-47.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/Machine_Learning/2024-06-03_18-47.png)

将多分类问题转换为多个二分类问题，每个二分类器负责识别一个类别。对于每个类别，训练一个二分类器，该分类器将该类别视为正类，其他所有类别视为负类。预测时，选择输出概率最高的分类器对应的类别。

**一对一** : 

![2024-06-03_18-50.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/Machine_Learning/2024-06-03_18-50.png)

为每对类别训练一个二分类器。如果有 K 个类别，则需要训练 K(K−1)/2​ 个分类器。预测时，通过投票机制决定最终类别。

**argmax** :

![2024-06-03_18-51.png](/home/sxz/The%20Final%20Battle%20of%20the%20Semester/Machine_Learning/2024-06-03_18-51.png)

是对**一对其余**的拓展.

## 线性分类:(Logistic Regression二分类)

sigmod函数:    $  f(x)=  \frac{1}{1+e^{-x}}​$

### 交叉熵

### 信息量

如果一件事情发生的概率很低，那么它的信息量就很大；反之，如果一件事情的概率很高，它的信息量就很低。举个例子：今年巴西队打进了世界杯，和今年男足打进了世界杯，那个信息量大！简而言之，发生概率小的事件信息量大，发生概率小的，信息量反而小。因此信息量可以定义如下：

$$
I(x_i)=log{1\over p(x_i)}
$$

$p(x_i)$表示随机事件发生的概率.

### 信息熵(information entropy)

信息熵实质是信息量的期望, 描述的整个系统的信息量.公式如下:

$$
H(p)=-\sum^n_{i=1}p(x_i)logp(x_i)
$$

### 相对熵

又称**KL散度**. 若对同一个随机变量X有两个单独的概率分布P(X)和Q(X)，使用KL散度来衡量这两个分布的差异。差异越大这相对熵越大，差异越小相对熵越小。

$$
D_{KL}(p\Vert q)=\sum^n_{i=1}p(x_i)logp(x_i)-\sum^n_{i=1}p(x_i)logq({x_i)}
$$

### 交叉熵

即为KL散度后半部分:

$$
H(p,q)=-\sum^n_{i=1}p(x_i)logq(x_i)
$$

在对分布 𝑞(𝑦) 的符号进行编码时，熵 𝐼(𝑞) 也是理论上最优的平均编码长度，这种编码方式称为熵编码（ Entropy Encoding ） 

## Softmax回归: 多分类问题

使用的"argmax"的方式进行分类,即使用全连接层.

使用的回归函数:

$$
\hat{y}=softmax(o)   其中,\hat{y_j}=\frac{exp(o_j)}{\sum_{k}exp(o_k)}
$$

其中o是特征的权重和.

## 感知器

模拟生物神经元行为的机器,有与生物神经元相对应的部件,如权重(突触), 偏置( 阈值 )及激活函数( 细胞体 ),输出为+1或-1.
