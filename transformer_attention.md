# Transformer 

## 1. 为什么要引入自注意力机制？

  在seq2seq任务重我们使用encoder、decoder架构，我们使用lstm/gru 作为encoder、decoder的特征提取器，虽然lstm、gru相比simple RNN解决了梯度爆炸、记忆力短的问题，但是当出序列
  较长的时候，encoder、decoder架构仍然会导致对较早时刻的输入信息记忆不全的问题，也叫“information bottle neck”。 
  因此导致了两个问题： 信息消失和梯度消失
  
  
  
  


  seq2seq任务中，
  
