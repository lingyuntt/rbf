来源：小凌のBlog—Good Times|一个不咋地的博客
https://blog.ling08.cn/
## 正则化RBF ##
用RBF网络解决插值问题时，基于上述正则化理论的 RBF网络称为正则化网络。其特点是隐节点数等于输人样本数，隐节点的激活函数为Green函数，常具有式a（r）=exp（-r的平方/2*σ的平方）的Gauss形式，并将所有输入样本设为径向基函数的中心，各径向基函数取统一的扩展常数。
由于正则化网络的训练样本与“基函数”是一一对应的。当样本数 P 很大时，实现网络的计算量将大得惊人，此外 P 很大则权值矩阵也很大，求解网络的权值时容易产生病态问题。为解决这一问题，可减少隐节点的个数，即 N < M < P，N 为样本维数，P 为样本个数，从而得到广义 RBF 网络。

![image](https://user-images.githubusercontent.com/61224939/167990411-e250c18b-b13a-46fb-beee-7e49451e6f44.png)

广义 RBF 网络的基本思想是：用径向基函数作为隐单元的“基”，构成隐含层空间。隐含层对输入向量进行变换，将低维空间的模式变换到高维空间内，使得在低维空间内的线性不可分问题在高维空间内线性可分。RBF 网络的学习算法（数据中心的监督学习算法）采用梯度下降算法，以忽略阈值的单输出网络为例，单样本训练的参数更新公式如下：

![image](https://user-images.githubusercontent.com/61224939/167990461-45eae00c-2f38-4879-8bb2-72f9c8e9addd.png)
## 简要图 ##

![image](https://user-images.githubusercontent.com/61224939/167990489-0336450f-06db-444f-a067-2414e25c0956.png)

## 运行结果 ##

这里为了运用算法，简要的举了一个例子，仅供参考
输入 ：
X=-1:0.1:1

输出 ：
D=[-0.96 -0.577 -0.0729 0.377 0.641 0.66 0.461 0.1336 -0.201 -0.434 -0.5 -0.393 -0.1647 0.0988 0.3072 0.396 0.3449 0.1816 -0.0312 -0.2183 -0.3201]

![image](https://user-images.githubusercontent.com/61224939/167990515-c043e06b-7d0b-4f4a-a977-c1e3ac21a73b.png)


```python
########################误差 1.97094######################第0次迭代
########################误差 0.87572######################第100次迭代
########################误差 0.58298######################第200次迭代
########################误差 0.29211######################第300次迭代
########################误差 0.08972######################第400次迭代
########################误差 0.04544######################第500次迭代
########################误差 0.02676######################第600次迭代
########################误差 0.01461######################第700次迭代
########################误差 0.00708######################第800次迭代
########################误差 0.00354######################第900次迭代
[-1.] -> [[-0.92630567]]
[-0.9] -> [[-0.5819172]]
[-0.8] -> [[-0.09586922]]
[-0.7] -> [[0.38054865]]
[-0.6] -> [[0.65524628]]
[-0.5] -> [[0.65606183]]
[-0.4] -> [[0.44954136]]
[-0.3] -> [[0.13573688]]
[-0.2] -> [[-0.19378414]]
[-0.1] -> [[-0.4351655]]
[-2.22044605e-16] -> [[-0.50417201]]
[0.1] -> [[-0.39375574]]
[0.2] -> [[-0.16560002]]
[0.3] -> [[0.09903841]]
[0.4] -> [[0.31451208]]
[0.5] -> [[0.40014661]]
[0.6] -> [[0.33274067]]
[0.7] -> [[0.16960969]]
[0.8] -> [[-0.01452695]]
[0.9] -> [[-0.18870826]]
[1.] -> [[-0.35617567]]
>>>S
[[-2.06216068e+01]
 [-6.23379026e-01]
 [-2.75235180e-01]
 [-1.83220403e-01]
 [-3.51571592e-01]
 [-3.74599402e-01]
 [-6.51551503e-01]
 [-3.80983180e-01]
 [ 2.21513900e-01]
 [ 7.83684980e-03]
 [-1.76384505e-01]]
>>>C
[[-2.02833963  0.76382975 -0.3515109  -0.65582968 -0.16646301  0.71497565
   0.16555357  0.66236107 -0.09091257 -0.94265449  0.48418609]]
>>>权值
[[ 1.27165879]
 [ 0.26187551]
 [ 0.85204661]
 [ 0.8898032 ]
 [ 0.69645458]
 [ 0.30058268]
 [ 0.46231703]
 [ 0.34839319]
 [-1.02111873]
 [ 0.1330878 ]
 [ 0.36195479]]
```




----------

[1]   韩力群，人工神经网络理论及应用 [M]. 北京：机械工业出版社，2016.
