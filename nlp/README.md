### 关于自然语言处理方面的笔记

#### 计算相似度的方法
度量文本相似度包括如下三种方法：

一是基于关键词匹配的传统方法，如N-gram相似度；

二是将文本映射到向量空间，再利用余弦相似度等方法；

三是深度学习的方法，如基于用户点击数据的深度学习语义匹配模型DSSM，基于卷积神经网络的ConvNet，以及目前state-of-art的Siamese LSTM等方法。 

1) 字面距离

> 莱文斯坦距离(编辑距离)、Jaro距离、SimHash

2) 语义相似性

①基于关键词匹配
> N-gram 相似度\
> Jaccard 相似度

② 基于向量空间
> Word2vec\
> TF-IDF\
> LSA\
> 相似度计算：欧式距离、曼哈顿距离、余弦相似度、其他

③基于深度学习
> 深度学习\
> DSSM\
> ConvNet\
> Skip-thoughts Vectors\
> Tree-LSTM\
> Siamese LSTM/Manhattan LSTM/MaLSTM\
> Others


### 算法的提出

一个算法的提出，一定是先有场景和需求，或者是前面的算法有改进的空间。场景高于算法这点是毋庸置疑的。

这几个博客[佟学强](http://www.cnblogs.com/txq157)、[红色石头](https://blog.csdn.net/red_stone1/)、[科学空间](https://spaces.ac.cn/)、[liuchongee](https://blog.csdn.net/liuchonge)、[Jey Zhang](http://www.jeyzhang.com/)、[西士城](https://zhuanlan.zhihu.com/xitucheng10)、[机器学习算法与自然语言处理](https://zhuanlan.zhihu.com/qinlibo-ml)、[悟乙己](https://blog.csdn.net/sinat_26917383/article/details/54882554)很不错
