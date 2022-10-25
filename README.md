#  **Edge Computing Gateway** 
**Editor**: Bohao, **Email**: bohao.chu@qq.com


## 1. **简介**

边缘计算网关（ **E**dge **C**omputing **G**ateway，**ECG**），以下简称 **ECG**。

本项目结构分为硬件部分和软件部分，基于 **Altium Designer 22** 设计的最新电路板位于 [hardware](./hardware/) 目录下，可以将其PCB文件打包，交给厂家进行打印。在硬件部分中，不再对PCB的设计进行描述，只对硬件结构，以及如何驱动各个硬件模块进行描述。在位于 [software](./software/) 的软件部分中，，将描述如何启动和使用各个模块，同时将重点介绍如何将机器学习算法应用在 **ECG** 上。

## 2. **硬件**

|4G|LoRa|TPU|ZigBee|433M|GPS|Camera|USB3|UART|ETH|WiFi|BLE|
|---|---|---|---|---|---|---|---|---|---|---|---|
|USB2.0|SPI|USB3.0|SPI|UART|UART|CSI|USB3.0|UART|-|-|-|


### 2.1 **物理层**

**ECG** 留出了12个的接口（存在复用）分给不同的硬件收发器和TPU，这些硬件收发器分为两大类，一类是传感器类（比如，通过 **LoRa** 收发器接受从 **LoRa** 节点发过来的信息，用通过 **GPS** 模块获取当前的地理坐标），一类是调试用（比如，通过 **UART** 打印输出信息，通过 **WiFi/ETH** 连接互联网，通过 **USB3.0** 连接鼠标/键盘）。

![](./assets/img/HD.png)


### 2.2 **驱动层**

在物理层中，各个模块通过不同的结构（存在复用）连接到 **Compute Module 4 (Linux)** 上。我们首先需要为各个模块设置[驱动](./software/lora/)，即达到可以工作的基本要求。在各个驱动之上，我们希望可以通过一个程序来统筹管理这些模块，其结构如下图。

在硬件部分中，将描述如何会为各个**硬件模块**（绿色）加载对应的**驱动和程序**（蓝色模块）。

![](./assets/img/dr2.png)


## 3. **软件**

在软件部分中，将描述如何实现统一驱动程序，以及APP和平台如何通过它使用各个模块。



## 4. **案例**

在案例部分中，我们将通过几个APP的案例使用ECG.


## 引用

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)


# ZZU EDGE COMPUTING GATEWAY
**Author**: 郑州大学物联网实验室， **E-mail**: bohao.chu@qq.com

<a href="https://www.youtube.com/watch?v=U0yiJcg7bTg"><img src="./assets/img/youtube.png"></a>
## **INTRODUCTION**



我们基于CM4设计了一个物联网网关，携带了一个基于4TOPS算力的Google Coral TPU机器学习加速器, 可以实现边缘计算。
![functions](/assets/img/functions.png "Magic Gardens")



## **HARDWARE**

![gateway](/assets/img/gateway.jpg "Magic Gardens")

### **BOOM**

### **Power Management System**
![gateway](/assets/img/pms.png "Magic Gardens")

### **Differential Pairs**
![gateway](/assets/img/differential_pairs.png "Magic Gardens")


## 软件

