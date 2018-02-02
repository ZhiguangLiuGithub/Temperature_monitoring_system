# 基于LabVIEW的实时温度监测系统

	【摘 要】提出一种基于LabVIEW软件平台的实时温度监测系统，利用串行通信总线将无线传感器网络中汇聚节点（下位机）的温度数据读取到该系统中。该软件系统具有实时显示温度变化曲线、显示近10次测量序列并提供一定的误差分析与处理、记录温度数值与当前时间到TXT文件、温度超限报警及通知邮件发送等功能。

### 一、总览

软件运行后如图1-1所示，前面板主要分为5个区域。

-  实时温度检测/T-℃——将温度变化的曲线实时显示在波形图标中；

-  串口配置——配置串口使计算机与下位机通信； 

- 测量序列——设置采样频率、显示最近10次的采样值，并计算对应的平均值和不确定度；

- 设置面板——用于配置“文件记录”及“自动报”相关功能；

- 邮件通知——用于设置与邮件通知功能相关的内容。

![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/1.jpg)


### 二、串口配置

- 该区域通过下拉菜单（组合框）的形式，设置端口、波特率、数据长度及是否打开奇偶校验四项基本信息，如图2-1所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/2.jpg)
- 设置完成后，点击“打开串口”按键即可开始读取串口数据，并将其打印到波形图表中，如图2-2所示，点击“关闭串口”按钮，即可关闭串口数据接收。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/3.jpg)
- 若没有检测到串口或通信异常，则关闭串口并弹出对话框提示用户，如图2-3所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/4.jpg)

### 三、测量序列

- 设置采样频率，要与下位机输出数据的频率尽量匹配，串口通信成功后“串口运行状态”灯点亮；

- 通过数值显示控件，用数组的方式将最近10次测量的值显示在前面板上；

- 利用调用子VI计算出其测量对应的平均值及不确定度，如图3-1所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/5.jpg)


四、设置面板

- 打开“是否记录工作日志/ .txt”开关，并设置文件保存路径，则系统会将每一次采集数据得到的温度值和对应的本地时间记录在指定位置的文本文件中，如图4-1、4-2所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/6.jpg)
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/7.jpg)

- 若文件存储路径无效，则关闭文件记录功能，并弹出对话框提示用户，如图4-3所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/8.jpg)

- 点击“开启自动报警”按钮，并设置超限阈值。则当温度超过设定阈值时，系统会点亮“报警状态灯”并同时发出滴滴声，直至温度不超过设定值，如图4-4所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/9.jpg)

- 点击“开启自动报警”按钮，并设置超限阈值。则当温度超过设定阈值时，系统会点亮“报警状态灯”并同时发出滴滴声，直至温度不超过设定值，如上图。

### 五、邮件通知

- 点击“开启邮件通知按钮”打开该功能，并设置收件人邮箱，如图5-1所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/10.jpg)

- 当步骤四中的自动报警功能打开，且实时温度超过设定值时，该系统将通过SMTP将报警信息发送到指定邮箱，以通知操作人员及时处理，如图5-2所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/11.jpg)

- 当邮件发送功能出现错误时，自动关闭该功能并弹出对话框提示用户，如图5-3所示。
![Alt text](https://github.com/CHENG-MING/Temperature_monitoring_system/raw/master/images/12.jpg)


### Requirements：
- LabVIEW 2016












