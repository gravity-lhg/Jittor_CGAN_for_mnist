# Jittor_CGAN_for_MNIST

#### **项目背景**

本项目为计图 Jittor 第二届人工智能挑战赛热身赛。

采用 Jittor 神经网络框架，基于 MNIST 数据集，使用 CGAN 条件生成对抗网络进行手写数字生成任务。

#### 实现效果

![模拟手机号码](result.png)

#### 所需环境

Window, Linux，Mac 均可，主要依赖于 Jittor 神经网络框架的安装环境。

Jittor 神经网络框架安装详见 [Jittor 官网安装教程](https://cg.cs.tsinghua.edu.cn/jittor/download/)

#### 文件说明

- checkpoints 文件夹
  - discriminator_last.pkl  判别网络的权重文件（100 epochs）
  - generator_last.pkl  生成网络的权重文件（100 epochs）
- CGAN.py 模型、网络训练已经测试代码

#### 网络训练

在当前目录下执行命令：

```python
# 执行命令前请修改 CGAN.py 中的 number 变量，换为想要生成的手机号码
python CGAN.py
```

#### 网络推理

在推理前请注释掉 **模型训练** 部分的代码，并修改权重文件加载路径：

```python
# 修改权重文佳加载路径为 checkpoints/xxxxxxxx_last.pkl
# 如果需要，可以在 CGAN.py 文件最后一行 save() 中修改结果保存路径及名称

# 完成以上操作后，执行下述命令进行推理
python CGAN.py
```

***注：*** 如果设备支持 cuda 加速并安装了 Jittor GPU 版本，训练和推理过程会自动进行 GPU 加速；如果没有，则会使用 CPU 进行训练和推理。

#### 致谢

本项目基于 *Conditional Generative Adversarial Nets* 论文实现，模版代码有清华 计图Jittor 团队提供。
