# 机器人参数说明

> 第一章中，我们探讨了产品的卖点及其设计理念，为您提供了对产品高层次理解的全景视角。现在，让我们进入第二章——机器人参数说明。这一章节将是您理解产品技术细节的关键。详细了解这些技术参数，不仅可以帮助您充分认识到我们产品的先进性和实用性，而且还能够确保您能够更有效地利用这些技术来满足您的具体需求。

## 1 机器规格参数

|产品型号 |Mercury X1 |
|:------------: |:---------------------------: |
|整机高度 |1.18m |
|工作电压 |24V |
|自由度 |19自由度 |
|续航时间 |8小时 |
|机械臂最大负载 |1KG |
|机械臂重复定位精度 |± 0.05mm |
|整机净重 |55KG |
|底盘驱动电机 |高性能直驱电机 |
|最大运行速度 |1.2m/s |
|最大爬坡角度 |15° |
|主控 |Nvidia Jetson Orin Nano 8GB |
|主控算力 |67 TOPS |
|屏幕 |9英寸触摸屏 |
|移动地盘传感器 |激光雷达，超声波雷达，2D视觉 |
|3D 相机 |dabai DC1 |
|麦克风 |线性4麦，5米180°拾音 |
|IO |	24V 6 Input, 6 Output |
|通信方式 |CAN 总线/WIFI/网口/蓝牙/USB/串口 |



## 2 软件基本功能支持

| 功能/开发环境 | 使用情况 |
| :------------: | :--------: |
| 自由移动 | 支持 |
| 关节运动 | 支持 |
| 笛卡尔运动 | 支持 |
| 轨迹录制 | 支持 |
| 无线控制 | 支持 |
| 紧急停止 | 支持 |
| Windows      | 支持 |
| Linux        | 支持 |
| MAC          | 支持 |
| ROS 1        | 支持 |
| Python       | 支持 |
| C++          | 支持 |
| C#           | 支持 |
| JavaScript   | 支持 |
| myblockly    | 支持 |
| Arduino      | 支持 |
| mystudio     | 支持 |
| 串口控制协议 | 支持 |
| TCP/IP       | 支持 |
| MODBUS       | 支持 |


# 3 控制核心参数

<!-- <img src="../../resources/8-FilesDownload/2-serialproduct/image.png " width="800" height="auto" /> -->

### 主控制器规格表

| 指标            | 参数         |
| :---------------: | :----------------: |
| 主控     | Jetson Orin Nano SUPER 8GB       |
| 主控型号 | Jetson Orin Nano SUPER 8GB           |
| CPU             | 6 核 NVIDIA Carmel ARM®v8.2 64 位 CPU <br> 6MB L2 + 4MB L3 |
| GPU           | 搭载48个Tensor核心的384核NVIDIA Volta™ GPU |
| AI 性能       | 67 TOPS        |
| 存储        | 16 GB eMMC 5.1         |
| CSI 摄像头      | 2个CSI摄像头 |
| 网络     | 10/100/1000 BASE-T以太网|
| USB 接口    | 1 个 USB 3.2 2.0 (10 Gbps) <br> 2 个 USB 2.0 接口|
| 其他 I/O  | 2个UART串口|


### 左右臂副控制器规格表

| 指标            | 参数         |
| :---------------: | :----------------: |
| 副控     | 左右臂副控      | 
| 副控型号 | ESP32           |
| 核心参数 | 240MHz dual core. <br> 600 DMIPS, 520KB SRAM. <br> Wi-Fi, dual mode Bluetooth |
| 辅控Flash | 4MB                |
| LED显示 | 5X5 RGB |


# 4 结构尺寸参数


> 本章以毫米为距离单位，以度为角度单位。

## 产品尺寸及工作空间
  选择机器人安装位置时，必须考虑机器人正上方和正下方的圆柱体空间，尽可能避免将工具移向圆柱体空间。因为这样会造成工具运动较慢时，关节却转动过快，从而导致机器人工作效率低下，风险评估难以进行。

<!-- <img src="../resources/2-ProductFeature/产品尺寸.png " width="400" height="auto" /> -->
<!-- 图2.3.1 产品尺寸 -->

<!-- <img src="../resources/2-ProductFeature/工作空间.png " width="800" height="auto" />   -->
<!-- 图2.3.2 产品工作空间 -->
            

<!-- ## 2 底座安装尺寸 -->

<!-- <img src="../resources/2-ProductFeature/底座尺寸.png " width="400" height="auto" /> -->
<!-- 图2.3.3 底座安装尺寸 -->


## 双臂末端法兰尺寸
<center>
<img src="../resources/2-ProductFeature/末端法兰.png" width="600" height="auto" />
<br>
图2.4.1 末端尺寸</center>

## DH值
<center>
<img src="../resources/2-ProductFeature/DH值.jpg" width="600" height="auto" />
<br>
图2.4.2 DH值</center>

## 手臂部分
<center>
<img src="../resources/2-ProductFeature/X450手臂部分.jpg" width="600" height="auto" />
<br>
图2.4.3 手臂部分</center>


# 5 电气特性参数

## 底座接口总览
<center>
<img src="./../resources/2-ProductFeature/底座正视图.jpg "
width="400" height="auto" />
<br>
Figure 1 底座正视图
<br>
<img src="./../resources/2-ProductFeature/底座左视图.jpg" width="400" height="auto" />
<br>
Figure 2 底座左视图
<br>
<img src="./../resources/2-ProductFeature/底座右视图.jpg " width="400" height="auto" />
<br>
Figure 3 底座右视图
<br>
<img src="./../resources/2-ProductFeature/05519a0595f3536c0b6d72ddc8b17e7.jpg " width="400" height="auto" />
<br>
Figure 4 底座内部图
<br>
</center>


## 底座接口说明

| 编号 | 接口    | 定义 | 功能         | 备注         |
|:----:|:--------------:|:---------:|:-----------------:|:----------------:|
| 1   |电源输入接口 | DC24V输入 | DC24V 输入 |                  |
| 2   | 开关         | 电源开关  | 控制输入电源通断  | 带灯（通电灯亮） | 
| 3   | 急停接口 | STOP      | 急停回路接口 |             | 
| 4  | 网口     |    |    |   |
| 5   | USB3.0       | USB3.0*2   | 可外接设备或U盘   |                  |    
<br>

#### 1 电源输入接口：本接口与DC24V电源适配器接口连接

#### 2 电源开关：控制总电源输入的通断，关闭时，控制器也断电

#### 3 急停回路端子：与急停按钮盒连接，可用于控制机器人紧急停止
>  **注**: 机器人使用中必须接上急停开关，并确保急停开关回路处于连通状态。
 
#### 4 以太网

#### 5 USB3.0接口：以串口总线标准3.0进行数据连接的接口；用户可以使用USB接口拷贝程序文件，也可以使用USB接口连接鼠标、键盘等外设
             


## 末端接口总览
<center>
<img src="./../resources/2-ProductFeature/左臂末端图.jpg" width="400" height="auto" />
<br>
Figure 5 左臂末端图
<br>
<img src="./../resources/2-ProductFeature/右臂末端图.jpg" width="400" height="auto" />
<br>
Figure 6 右臂末端图
<br>
</center>

## 末端接口说明
| 编号 | 接口    | 定义 | 功能         | 备注         |
|:------:|:----------------:|:-----------:|:-------------------:|:------------------:|
| 6  |   4pinUSB端子   | 对外接口 | 连接摄像头 |  |
| 7   | M8航空插座 | 末端工具IO接口 |  与外部设备交互 |                  |



#### 如图所示是M8航空插座I/O图，Mercury X1机器人提供了一路输入和两路输出。
<center>
<img src="../resources/2-ProductFeature/机械臂末端工具说明.png " width="" height="auto" />
<br>
各个工具I/O端口的定义如下表所示，注意的是，工具I/O无论是输入还是输出都是PNP类型，接线方式同底部输出接口一致。
</center>

| 编号 | 信号 | 解释             | 配套M8线颜色 |
| :------: | :------: | :-----------------------: | :--------------------------: |
| 1      | GND    | DC24V 负极      | 白                      |
| 2      | OUT1   | 工具输出接口1 | 褐                      |
| 3      | OUT2   | 工具输出接口2 | 绿                      |
| 4      | 485A   | 预留, 未开发   | 黄                     |
| 5      | 24V    | DC24V 正极         | 灰                        |
| 6      | IN1    | 工具输入接口1  | 粉                       |
| 7      | IN2    | 具输入接口2             | 蓝                      |
| 8      | 485B   | 预留, 未开发   | 紫                    |

> **注意:** 此接口目前不支持热插拔, 可能会导致机器器件损坏。在插拔前，需要先关机。

#### USB端子：用于连接摄像头



如果您已经阅读了本章的所有内容，可以继续阅读下一章。

[← 上一章](../1-ProductIntroduction/README.md) | [下一章 →](../3-UserNotes/README.md)
