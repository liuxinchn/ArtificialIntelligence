# ML



Machine Learning ≈ Looking for Function

深度学习，就是这个function是类神经网络的形式。

![输入与输出](./figure/iooffunction.png)



## Introduction

机器学习根据输出，其任务分为：

- Regression
- Classification
- Structured Learning



做机器学习的步骤：

1. Function with Unknown Parameters. 

   y = b + wx

2. Define Loss from Training Data

   将w和b作为损失函数的输入，e为损失e = | y - y<sup>^</sup> |, L(w,b)=1/N*Σe，可以用MAE、MSE或其他作为损失函数

3. Optimization

   找到最佳的w<sup>\*</sup> 和 b<sup>\*</sup>，其过程是随机找一个点，计算微分，然后根据微分的值，逐步向minima值靠近，其中可以设置学习率，表示向minima点靠近的速度。以只有一个w为例，w1 = w0 - η* L'/w'，η是学习率，为超参数。

   