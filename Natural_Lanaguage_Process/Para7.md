# 第七章: 词法分析与词性标注

词是自然语言中能够独立于用的最小单位, 是自然语言处理的基本单位.



词法分析包括: 分词, 命名实体识别, 词性标注



**自动词法分析** 就是利用计算机对自然语言的形态( morphology )进行分析, 判断词的结构和类别等.



**词性** 是词汇最重要的特性, 是连接词汇到句法的桥梁



英语形态分析基本任务: 单词识别, 形态还原



**交集型歧义 (Intersectional Ambiguity)**

交集型歧义是指某个词或短语在不同的语义类别中有重叠的含义。在这种情况下，词语的不同解释之间有某种共同点或交集。即使在不同的上下文中，这些解释也可能会有部分重合。

例如：

- “银行”可以指金融机构，也可以指河岸。对于句子“他在银行旁边钓鱼”，两个解释的交集是“河岸”，因为河岸也是一个可能的钓鱼地点。

**组合型歧义 (Compositional Ambiguity)**

组合型歧义是指由多个成分组成的表达式，其不同成分的组合方式导致不同的整体意义。即使每个单独成分的意义是明确的，但它们的组合方式却可以产生不同的解释。

例如：

- “老教授的学生”可以有两种解释：
  - 老的教授的学生（教授是老的）
  - 教授的老学生（学生是老的）在这种情况下，歧义来源于“老”这个词到底修饰“教授”还是“学生”。



评价指标:

* 精确率 
  
  * P=正确的个数/系统输出的个数

* 召回率( 查全率 )
  
  * R=正确的个数/正确的总个数

* F1值, 正确率与召回率的综合值
  
  * $$
    F1=\frac{2\times P\times R}{P+R} \times 100\%
    $$



分词算法

* 有词典切分/无词典切分

* 基于规则的方法/基于统计的方法



具体分词算法:

1. 最大匹配法: 有词典切分

2. 最少分词法:( 最短路径法 )

3. 基于HMM的分词方法

4. 由字构词( 基于字标注 )的分词方法: 将分词过程看作是字的分类问题,BMES

5. 生成式方法与区分式方法结合
   
   * 大部分基于词的分词方法采用的是生成式模型, 而基于字的分词方式采用区分(判别)式模型



未登录词识别:

命名实体(Named Entity), 人名(中国人名和外国译名), 地名, 组织机构名, 数字, 日期, 货币数量



词性(partofspeech)标注(tagging)的主要任务是消除词性兼类歧义



词性标注的方法

* 基于规则的词性标注方法: Tagging词性标注系统

* 基于统计模型的词性标注方法: HMM

* 规则和统计方法相结合的词性标注方法
  
  * 规则消歧, 统计概率引导
  
  * 或者统计方法赋初值, 规则消歧
