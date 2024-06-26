# 第一章:绪论

## 常用的深度学习框架

* pytorch
  
  * 使用动态计算图, 这意味者图结构是运行时产生的.
  
  * 提供了强大的自动微分的功能
  
  * 多平台支持, 包括CPU和GPU( 通过CUDA )
  
  * 易于使用简单明了

* tensorflow
  
  * 使用静态计算图, 图结构在运行之前已经定义好了.
  
  * 提供了丰富的模块和组件库
  
  * 分布式计算

* paddlepaddle
  
  * 灵活的架构设计,可以支持不同深度学习模型的构建和训练。
  
  * 高性能分布式训练,能够在多机多卡环境下进行高效的模型训练。
  
  * 易于使用的API

## 人工智能的三大常见流派

* 连接主义( 仿生学 )

* 符号主义( 逻辑推理 )

* 行为主义( 感知+行动 )

## 机器学习流程

1. 准备数据及预处理

2. 特征提取

3. 特征转换

4. 预测

5. 结果

## 表示学习vs浅层学习vs深度学习

### 表示学习

为了提高机器学习系统的准确率，我们就需要将输入信息转换为有效的特征，或者更一般性称为表示（Representation）。如果有一种算法可以自动地学习出有效的特征，并提高最终机器学习模型的性能，那么这种学习就是可以叫做表示学习（Representation Learning）。

### 表示的形式:

* 局部表示

* 分布式表示

### 浅层学习

浅层学习（Shallow Learning）是指那些相对于深度学习（Deep Learning）而言结构较为简单的机器学习算法和方法。浅层学习模型通常具有较少的层数和较少的参数，因此它们在计算复杂度和所需数据量上相对较低。以下是一些常见的浅层学习算法：

* **线性回归（Linear Regression）**：用于回归任务，建立输入特征与输出之间的线性关系。

* **逻辑回归（Logistic Regression）**：用于二分类任务，通过逻辑函数建立输入特征与二分类结果之间的关系。

* **支持向量机（Support Vector Machine, SVM）**：用于分类和回归任务，寻找最优超平面来分隔数据点。

* **决策树（Decision Tree）**：通过构建树形结构进行分类或回归。

* **朴素贝叶斯（Naive Bayes）**：基于贝叶斯定理进行分类，假设特征之间相互独立。

* **K-近邻算法（K-Nearest Neighbors, KNN）**：通过计算新数据点与训练数据集中点的距离进行分类或回归。

* **主成分分析（Principal Component Analysis, PCA）**：一种降维技术，通过线性变换将数据投影到低维空间。

### 深度学习

所谓“深度”是指原始数据进行非线性特征转换的次数。

深度学习（Deep Learning）是一种机器学习的子领域，致力于通过多层神经网络从数据中学习复杂的特征表示和模式。与浅层学习相比，深度学习的主要特点是其网络结构通常包含多个隐藏层，能够自动地从数据中提取和学习高层次的抽象特征。

以下是深度学习的几个关键概念和技术:

1. **神经网络（Neural Networks）**：
   
   * **人工神经网络（Artificial Neural Networks, ANN）**：由多个神经元（类似于大脑中的神经细胞）连接组成的网络。每个神经元接收输入信号，经过加权和激活函数处理后输出结果。
   
   * **多层感知器（Multilayer Perceptron, MLP）**：一种典型的前馈神经网络，包含输入层、多个隐藏层和输出层。

2. **卷积神经网络（Convolutional Neural Networks, CNNs）**：
   
   * 主要用于处理图像数据。通过卷积层、池化层和全连接层，CNN能够自动提取图像的空间层次特征。

3. **循环神经网络（Recurrent Neural Networks, RNNs）**：
   
   * 主要用于处理序列数据，如时间序列、文本等。RNN通过其内部的循环结构，能够捕捉序列中的时间依赖性。

4. **长短期记忆网络（Long Short-Term Memory, LSTM）**：
   
   * RNN的一种变体，能够更好地捕捉长时间依赖性，适用于长序列数据的处理。

5. **自编码器（Autoencoders）**：
   
   * 一种无监督学习模型，通过将输入数据编码为低维表示，再从低维表示重建数据，用于特征提取和降维。

6. **生成对抗网络（Generative Adversarial Networks, GANs）**：
   
   * 包含一个生成器和一个判别器，通过相互竞争的方式进行训练，能够生成逼真的数据样本。

7. **Transformer模型**：
   
   * 以注意力机制为核心的模型，广泛应用于自然语言处理任务，如BERT和GPT。

## 赫布法则:

当一个神经元的活动导致另一个神经元的活动，并且这种关联反复出现，那么前一个神经元的突触效能会增强。这种增强的突触效能被认为是学习和记忆的基础。

## 神经网络发展历史的五个阶段:

1. 第一阶段: 模型提出
   
   * 提出MP模型,感知机器(考)

2. 第二阶段: 冰河时期( 发现了神经网络的两个关键问题 )
   
   * 基本感知机无法处理异或问题
   
   * 电脑没有足够的能力来处理大型神经网络, 其需要很长的计算时间.

3. 第三阶段: 反向传播算法引起的复兴(考)

4. 第四阶段: 流行度降低
   
   * 统计学习理论和以支持向量机为代表的机器学习模型开始兴起
   
   * 相比之下,神经网络理论基础不清晰,优化困难,可解释性差等缺点更加凸显.

5. 第五阶段: 深度学习的崛起
   
   * 卷积神经网络(Alexnet是第一个现代深度卷积网络模型)
