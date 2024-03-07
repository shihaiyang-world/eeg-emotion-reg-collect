# eeg-emotion-reg-collect


## 1. 介绍
本项目是一个基于脑电信号的情绪识别项目，基于脑电信号的情绪识别，记录参考论文列表

## 2. 数据集
本项目使用的数据集是DEAP数据集，数据集下载地址：[DEAP](http://www.eecs.qmul.ac.uk/mmv/datasets/deap/index.html)

32个用户，每个用户40个视频片段，每个片段63s，3s的基础信号和60秒情绪信号数据
每个片段包含40个脑电信号通道，其中32个是脑电通道，包含8个生理信号通道，每个通道包含128个数据点。
数据原始大小：32文件 *   40 * 40 * 8064（63*128）


## 3. 参考论文

| 论文                                                                                                                                                                                                                                  | 年份   | 主要方法介绍                                                                                    | 代码                                                         | 备注                                                                           |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----|:------------------------------------------------------------------------------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------------|
| [4DCRNN](https://link.springer.com/article/10.1007/s11571-020-09634-1)                                                                                                                                                              | 2020 | 特征：微分熵 电极位2D Map<br/>模型方法：CNN+LSTM<br/>                                                   | 有                                                          | 正确率94.22±2.61   94.58±3.69基线论文                                               |
| [ 4D-aNN：4D attention-based neural network](https://link.springer.com/article/10.1007/s11571-021-09751-5)                                                                                                                           | 2022 | 输入：微分熵<br/>模型方法： Attention Base CNN+ 通道Attention+ Attention-based bidirectional LSTM      | 无                                                          | 正确率96.90±1.65   97.39±1.75 <br/>跟基线论文思路一致<br/>多个位置加了Attention<br/>           |
| [DGCNN](https://ieeexplore.ieee.org/abstract/document/8320798)                                                                                                                                                                      | 2020 | 特征：DE PSD等<br/>模型: DGCNN      Dynamical Graph Convolutional Neural Networks               | [code](https://github.com/xueyunlong12589/DGCNN)           | 正确率：86%   使用图卷积 <br/>参考一下图卷积实现   <br/>可以用多输入的方式CNN+GCN -> LSTM               |
| [based on multi-task learning with capsule network and attention mechanism](https://www.sciencedirect.com/science/article/pii/S0010482522000956?__cf_chl_tk=lP2C6_S_b5LgzNnRPOEx9gCuVXa17yQ3XiZT9z7rjzE-1709543095-0.0.1.1-1386)    | 2022 | 特征：raw 原信号特征<br/>模型: CapsuleNet + CNN+GCN+Channel Attention                               | 无                                                          | 正确率：94.96 ± 3.60	95.54 ± 3.63<br/>胶囊网络的参考                                    |
| [based on the attention mechanism and pre-trained convolution capsule network](https://www.sciencedirect.com/science/article/pii/S0950705123001223?__cf_chl_tk=LTl.7rkCG_cLAKEYO4B8ON54y.5j1YN_e3iH3UYD7ek-1709792474-0.0.1.1-1386) | 2023 | 特征：原脑电信号<br/>模型:  PreTraining Coordinator Attention+MobileNet+CapsuleNet                  | 无                                                          | 	正确率93.89%	95.04%<br/>引入胶囊网络，参考了思路。但是引入胶囊之后正确率不高                             |
| [ICaps-ResLSTM](https://www.sciencedirect.com/science/article/pii/S1746809423008558#b28)| 2024 | 特征：原信号特征<br/>模型: CapsuleNet + ResLSTM     1s的时间窗口 原信号32*128大小的矩阵，先卷积reshape得到胶囊，经过ResLSTM | 无                                                          | 正确率：**98.06 ± 1.24	97.94 ± 1.32**   目前最高 到98了<br/>参考了一下，用胶囊网络加原信号的方式，卷积直接OOM |
| [Deep Learning Architecture for Short-Term Passenger Flow Forecasting in Urban Rail Transit](http://doi.org/10.1109/TITS.2020.3000761)  | 2020 | 特征：轨道客流量预测 <br/>模型:ResNet+LSTM+GCN                                                        | [Code](https://github.com/JinleiZhangBJTU/ResNet-LSTM-GCN) | tensorflow开发，轨道流量预测的<br/>使用了GCN+LSTM    可以参考方式                               |
| [Efficient-CapsNet: capsule network with self-attention routing](https://github.com/EscVM/Efficient-CapsNet/tree/main)  | 2021 | Efficient Capsule                                                                         | [Code](https://github.com/EscVM/Efficient-CapsNet/tree/main)                                                   | 基础的模型  Efficient Capsule， 加入到我的逻辑里，准确率变低。                                    |
| []()  | 2022 | 特征：<br/>模型:                                                                               | 无                                                          |                                                                              |
| []()  | 2022 | 特征：<br/>模型:                                                                               | 无                                                          |  
| []()  | 2022 | 特征：<br/>模型:                                                                               | 无                                                          |                                                                              |


