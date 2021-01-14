### 华为MateBook D2018款黑苹果EFI

#### 支持big sur 11.0.1(20B29) OTA升级及全新安装

#### OpenCore Version: 0.6.4

#### 问题

最新EFI存在白苹果及登录界面闪屏1-2次的问题，应该是显卡缓冲帧的问题，请谨慎使用，

其他驱动可能存在些小问题，应该不太影响日常使用，不过因人而异，详见issues

#### 配置(全部原装，无需更换配件)

| 描述     | 详情                           |
| -------- | ------------------------------ |
| 电脑型号 | 华为MateBook D2018             |
| 处理器   | 英特尔酷睿i7-8550U处理器       |
| 内存     | 16 GB 2400 MHz DDR4            |
| 硬盘     | LITEON CV8-8E256 SATA          |
| 显卡     | Intel UHD Graphics 620 2048 MB |
| 声卡     | Realtek ALC256                 |
| 无线网卡 | Intel Wireless 8265 / 8275     |



#### BIOS修改

机器采用系微(insyde)bios，使用常规的setup_var修改失败。H2O VUE系列工具(H2OUVE-W-GUIx64.exe,   解压InsydeH2OUVE.zip)可成功修改，全程可在PE下进行。工具使用教程请自行搜索

|          | 偏移量 | 修改值                  | BIOS修改节点 |
| :------- | :----- | :---------------------- | ------------ |
| CFG Lock | 0x3C   | 0X0: 关闭     0x1: 打开 | cpusetup     |
| DVMT     | 0XDF   | 0x2: 64M                | sasetup      |



*cfg lock关闭后可启用原生电源管理。ps: 目前没感觉出来差别*

*dvmt调整至64M及以上，以支持外接4K及以上显示器。不过因为设备只有HDMI 1.4的接口，最高只支持到4K@30hz,而且DVMT最大只能修改到64M*

