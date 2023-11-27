# Deep Q Network  

原理与 Q - Learning 类似
Q 迭代式

$$Q_{new}(s, a) = Q(s, a) + \alpha(reward + \gamma \ max Q(s_{next}) - Q(s, a)$$
其中 $Q(s, a)$ 利用 以 $\theta$ 为参数的神经网络来近似得到，即
$$Q(s, a) \approx Q(s, a, \theta)$$
作为监督学习的神经网络，需要提供真实标签，定义真实标签为 $$TargetQ = reward + \gamma *max Q(s_{next})$$
则 损失函数可以定义为
$$
Loss(\theta) = E[(\ TargetQ - Q(s, a, \theta)\ )^2]
$$

为了提高算法稳定性，利用一个神经网络 $F(\theta_1)$ 来生成 TargetQ，其中 $\theta_1$ 在一段时间之后再与$Q(\theta)$ 的 $\theta$ 同步，即
$$
	\theta_1:= \theta \ \ \ \ \ \ \ \ \ \ after\ \  a \ \ while
$$
### Network 1 (FindAction Network)

用与选择动作

Input: State

Output: Action

  

其中的映射关系使用神经网络实现

该选择动作的方法在ChooseAction当中以一定概率使用 (tan)