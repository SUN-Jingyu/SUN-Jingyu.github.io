# 本文记录准备秋招所学习的知识以及反思

## 如何设计硬件电路全流程

> 学习路径 [b站 达尔文-1个好的硬件电路如何设计](https://www.bilibili.com/video/BV1j3411q7KV/?spm_id_from=333.788.top_right_bar_window_custom_collection.content.click&vd_source=ff9a60fb4cd8133ac45d108a89246dc0)

1. **分析项目需求，确定主芯片**  
    确定外围设备的需求以及功能。
2. **搭建硬件框图**
    系统框架的绘制与原理图的选型；需要考虑到价格，生产供货周期，量产截止时间以及潜在性问题。
3. **绘制原理图**
    准备元器件（自画或者拷贝；参考数据手册绘制原理图，我觉得这部分需要软件的电路仿真LTspice，
4. **PCB设计**
    封装添加和网络表同步，规则设置，布局布线。
5. **PCB打样**
    准备Gerber文件；工艺要求文件
6. **焊接调试**
    SMT贴片还是手焊，短路测试，上电测试，再调功能，维修以及模块化检查出问题的电路。
7. **PCBA展示**

## LDO

[TI 官方手册 Understanding Low Drop Out(LDO) Regulators](https://www.ti.com/download/trng/docs/seminar/Topic%209%20-%20Understanding%20LDO%20dropout.pdf)
