## 1. Machine Learning 概述

构建一个模型模拟人 / 生物的模型，达到计算机自主学习的效果

### 监督学习
已经标记好的数据
1. 回归分析 （ 比如训练出 加法运算器 ）
	1. 线性回归
	2. 逻辑回归
2. 分类问题 （ 分类好瓜还是坏瓜 ）
	1. 决策树
		1. ID3
		2. C45
	2. 支持向量机（SVM）
	3. 朴素贝叶斯
### 非监督学习
聚类算法
1. k means
2. 最大期望算法
3. 限制玻尔兹曼机
### 强化学习
常见于游戏AI，主要由 Agent， Environment，State，Action，Reward
（举例超级玛丽）

### 实际建模
1. 收集数据
2. 数据处理
3. 构建模型
4. 训练
5. 评估
6. 调参
7. 使用

推荐课程 —— [吴恩达](https://www.bilibili.com/video/BV164411b7dx/?share_source=copy_web&vd_source=fbbfec5474f3893268b3de8cdea613d1)
推荐读物 —— “ 西瓜书 ”

## 数学基础 （可选）
1. 集合
2. 向量
3. 矩阵
4. 概率
	1. 古典概型
	2. 贝叶斯定理
5. 多元微积分

## Python 基础 （可选）
1. 顺序结构
2. 简单变量
3. 分支结构
	1. if , else, elif
4. 循环语句
	1. For
	2. While
6. 数据结构
	1. List
	2. Dictionary
7. 调包


## 2. BP 神经网络
#### 理论部分
1. 神经元模型 / 感知器
2. 网络结构
	1. 输入
	2. 全连接层
	3. 输出
3. 前向传播
	1. 线性运算
	2. 激活函数
	3. 利用线性代数简化运算（ 可选 ）
4. 激活函数以及意义
	1. 非线性的关系（解决线性不可分问题）
	2. 常见激活函数（非线性函数）
		1. $Sigmoid(x) = \frac{1}{1+e^{-x}}$
		2. 阶跃函数
		3. Relu
		4. Tanh
5. 反向传播
	1. 损失函数
	2. 求梯度
		1. 根据链式法则可以得到$\frac{\partial E}{\partial w_{ij}}=\frac{\partial E}{\partial modelOutput}*\frac{\partial output}{\partial netInput} * \frac{\partial netInput}{w_{ij}}$
		2. 输出层 -> 隐含层 为
			1. $\frac{\partial E}{\partial O_i}$ （ 对损失函数进行求导 ）
			2. $\frac{\partial O_i}{\partial I_i}$ （ 对激活函数进行求导 ）
			3. $\frac{\partial I_i}{\partial Net_i}$ ( 对隐含层求和函数求导 )
		3. 隐含层 -> 隐含层 为 同理得
			1. 损失函数
			2. 激活函数
			3. 求和函数
	4. 更新参数 $w_{ij} := w_{ij} -\lambda \nabla w_{ij}$
6. 参数问题
	1. 过拟合 （ 泛化误差大 ）
		1. 减少模型复杂度 / dropout
		2. 提前停止 training
		3. 增强数据集
		4. 正则化
	2. 欠拟合
		1. 增加参数
		2. 增加网络深度
		3. 同上
#### 实战部分
1. 拟合函数 （ 预测价格 ）
2. 分类器 （MNIST 数据集）

#### 涉及代码部分
1. Dense 全连接层
2. Dropout 随机失活神经元层
	1. 在 training 时候自动启用
	2. 在 预测的时候 自动关闭
3. Softmax 激活函数
	1. 用于多分类
	2. $$Softmax(x_i) = \frac{e^{x_i}}{\sum_n^{j=0}e^{x_j}}$$
4. Flatten 展开层
5. Adam 优化器
	1. 动态调整学习率
	2. 不用在意这个细节
6. 'mse' --> mean_squared_error
	1. 均方差损失函数
	2. $\frac{1}{2n}\sum_i^n{(y_i - \hat y_i)^2}$
7. ‘SCC’
	1. 接受 logits 向量和 True 索引，并为每个样本返回一个标量损失。
	2. 用于多分类损失函数
## 3. CNN
#### 理论部分
1. 卷积操作
	1. 理解一下大致流程 （ 滑动窗口 ）
		1. 填充
		2. 步长
	2. 高维卷积
		1. 举例 RGB 编码的三通道图片
	3. 卷积层的叠加
		1. 输出特征维度 = 滤波器个数
2. 池化层操作
	1. 减少特征数 （ 防止过拟合 ）
	2. 类似卷积操作流程
3. 调参技巧

#### 实战部分
实现图像分类器 （MNIST）

## 4. RNN
#### 理论部分
1. 把当前输出作为下一个输入
	1. $f(x_t) = f(input, x_{t - 1}, x_{t - 2}, …, x_1)$
	2. $f(x_t) = f(input, x_{t - 1})$
2. 可以用于处理时间序列

#### 实战部分
1. Encoder -> Decoder

## 5. NLP



