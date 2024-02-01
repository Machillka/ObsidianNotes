
`Graph Neural Network ( 图神经网络 )`

## 网络结构

利用邻接表存储 Graph 的信息。利用向量存储 U, V, E ( 点，边，全局 ) 信息。

在不考虑信息流动的情况下，每一层使用MLP进行运算映射到下一层。缺点在于边、点和全局的信息没有被很好的利用起来，融合在一起。

最后一层得到的图就是网络对于输入图的理解，然后进行下游任务的处理，比如加上分类层等。

## Message passing

将该节点的信息与自己的邻居的信息进行整合运算（如加法、取mean等操作），传递给下一层。所以如果层数够深，并且输入图为连接图，则最后输出的图可以更好的得到全局的理解

信息汇聚也可以汇聚其他信息（比如节点的边权、点权等）
![[arch_mpnn.a13c2294.png]]![[arch_graphnet.b229be6d.png]]
（图片来源[A Gentle Introduction to Graph Neural Networks (distill.pub)](https://distill.pub/2021/gnn-intro/)）

