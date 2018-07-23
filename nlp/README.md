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
