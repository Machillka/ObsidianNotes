# Deep Q Network  

原理与 Q - Learning 类似
Q 迭代式

$$Q_{new}(s, a) = Q(s, a) + \alpha(reward + \gamma \ max Q(s_{next}, a_{next}) - Q(s, a)$$
其中 $Q(s, a)$ 利用 以 $\theta$ 为参数的神经网络来近似得到，即
$$Q(s, a) \approx Q(s, a, \theta)$$
作为监督学习的
### Network 1 (Evaluate Network)

用与选择动作

Input: State

Output: Action

  

其中的映射关系使用神经网络实现

该选择动作的方法在ChooseAction当中以一定概率使用 (tan)