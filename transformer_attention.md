# Transformer 

## 1. 为什么要引入自注意力机制？

  在seq2seq架构中我们使用encoder、decoder，一般在encoder、decoder中使用RNN（lstm,gru,simpleRNN）用于特征提取器，虽然lstm、gru相比simple RNN解决了梯度爆炸、记忆力短的问题，但是当输入序列较长的时候，seq2seq架构仍然会导致对较早时刻的输入信息记忆不全的问题，也叫“information bottle neck”。 
  导致了两个问题： 
  - 信息消失: 较早时刻的信息被忘记
  - 梯度消失: 在反向传播中，梯度越来越小，导致模型最终没有学习。
 
  <img width="500" alt="截屏2023-02-02 上午12 29 04" src="https://user-images.githubusercontent.com/30898964/216271443-de0266a8-8610-49b3-ba6d-7f08e1d6cf77.png">


<img width="500" alt="截屏2023-02-02 上午12 41 59" src="https://user-images.githubusercontent.com/30898964/216274113-1b29f08b-ad1b-475a-9449-21b727ce8b24.png">
   
  ### Transformer 与 seq2seq的区别

  在seq2seq中引入attention可以在一定程度消失问题，请注意seq2seq的encoder、decoder必须依赖RNN。
  然而，Transformer就厉害了，去掉了encoder、decoder中RNN，只需要attention，原seq2seq架构中我们需要顺着时间时间片计算，如需处理的序列越长，时间片越长，越容易导致梯度消失。 tansformer就不会收到因处理的序列较长导致的的梯度消失问题，
  
  tansfomrer 是大型语言模型bert，gpt的基础
  
 
<img width="500" alt="截屏2023-02-02 上午12 54 22" src="https://user-images.githubusercontent.com/30898964/216276999-3609c84f-b225-4456-83f7-e26c4996f527.png">

论文出处：

<img width="500" alt="截屏2023-02-02 上午12 55 17" src="https://user-images.githubusercontent.com/30898964/216277208-9d97327b-abfa-4822-a026-f8e723c00f41.png">


一般注意力打分函数有如下几种。 
<img width="500" alt="s(x oaxuVgs(UxVg)  印分制对g透行线性变楼居透行点机， 相龙有积機型，双线性機型在特雞相制度" src="https://user-images.githubusercontent.com/30898964/216278348-f29ffb9d-f8f1-43e7-abff-6e42e6131781.png">

transformer 模型用的是缩放点积注意力（Scaled Dot-Product attention)
缩放点积使用矩阵乘法，计算速度效率高，占用内存低。因很多数连成会导致值越来越大，或越来越小（方差大），所以除以了一个d，d是向量维度。

<img width="500" alt="截屏2023-02-02 上午12 58 46" src="https://user-images.githubusercontent.com/30898964/216277963-988f14a8-4e73-40ea-91f0-144170c688dc.png">


### 多头注意力机制(Multi-Head Attention)

Transformer模型使用的是多头注意力机制，多个注意力机制是并行工作的。

<img width="500" alt="截屏2023-02-02 上午1 07 14" src="https://user-images.githubusercontent.com/30898964/216279941-94414d63-8318-494e-83e6-f15f214938cf.png">


线性变换过程

<img width="1192" alt="截屏2023-02-02 上午10 15 41" src="https://user-images.githubusercontent.com/30898964/216410965-28faf764-e513-4720-9f60-28f9ab4f1905.png">




















