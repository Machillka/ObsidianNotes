# Deep Q Network

  

原理与 Q - Learning 类似

$Q_{new}(s, a) = Q$

  

### Network 1 (Evaluate Network)

用与选择动作

Input: State

Output: Action

  

其中的映射关系使用神经网络实现

该选择动作的方法在ChooseAction当中以一定概率使用 (tan)