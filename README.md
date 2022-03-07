## MSI MAG Z390 TOMAHAWK i7-9700K

### 当前版本信息

| 信息                                                         | 版本                   |
| ------------------------------------------------------------ | ---------------------- |
| 系统                                                         | macOS Big Sur 11.6 20G165 |
| [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) | 0.7.8                  |
| 模拟机型                                                     | iMac19,1               |
| [Lilu.kext](https://github.com/acidanthera/Lilu/releases)    | 1.6                  |
| [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC/releases) | 1.2.8                  |
| [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases) | 1.5.7                  |
| [AppleALC.kext](https://github.com/acidanthera/AppleALC/releases) | 1.6.9                  |
| [IntelMausi.kext](https://github.com/acidanthera/IntelMausi/releases) | 1.0.7                  |
| [CPUFriend.kext](https://github.com/acidanthera/CPUFriend)   | 1.2.4                  |

### 电脑配置信息

| 硬件     | 型号                                  |
| :------- | ------------------------------------- |
| 处理器   | Intel i7-9700K                        |
| 主板     | MSI MAG Z390 TOMAHAWK                 |
| 内存     | 威刚 8GB DDR4 3000MHz * 2             |
| 硬盘     | 阿斯加特 1T                           |
| 显卡     | 核显                                  |
| 无线蓝牙 | NA 								   |
| 有线网卡 | 双网卡 							   |
| 无线网卡 | NA 								   |

### 安装教程

#### BIOS设置

> 升级最新BIOS
> 同时请设置语言为简体中文并进入高级模式（F7）。

必要设置：

- OC(Overclocking) -> CPU 特征 -> Intel 虚拟化技术 **[允许]**
- OC(Overclocking) -> CPU 特征 -> Intel VT-D 技术 **[禁止]**
- OC(Overclocking) -> CPU 特征 -> CFG锁定 **[禁止]**

按需设置：

- STTINGS -> 高级 -> 内建显示配置 -> 设置第一显卡 **[PEG]**  *(仅同时拥有核显及独显需要手动设置)*
- STTINGS -> 高级 -> 内建显示配置 -> 集显共享内存 **[64M]** *(如果使用拥有核显的处理器)*
- STTINGS -> 高级 -> 内建显示配置 -> 集成显卡多显示器 **[允许]** *(如果使用拥有核显的处理器)*
- STTINGS -> 高级 -> PCI子系统设置 -> Above 4G memory/Crypto Currency mining **[允许]**
- STTINGS -> 高级 -> USB设置 -> XHCI Hand-off **[允许]**
- STTINGS -> 高级 -> USB设置 -> 传统USB支持 **[允许]**
- STTINGS -> 高级 -> 电源管理设置 -> ErP Ready **[允许]**
- STTINGS -> 高级 -> Windows操作系统的配置 -> Windows 10 WHQL支持 **[允许]**
- STTINGS -> 高级 -> 唤醒事件设置 -> 唤醒事件管理 **[BIOS]**
- STTINGS -> 高级 -> 唤醒事件设置 -> USB设备从S3/S4/S5唤醒 **[允许]** *(设置后我这边出现关机下键盘灯仍亮着情况。如出现一样情况，建议关闭，可按电源键唤醒)*

#### 修改config.plist文件

> 修改plist文件建议用[ProperTree](https://github.com/corpnewt/ProperTree)工具。
>
> 修改参考这两位大神的文章：[xjn博客](https://blog.xjn819.com/?p=543) [黑果小兵博客](https://blog.daliansky.net/OpenCore-BootLoader.html)

- 修改三码
  1. 使用[GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)脚本生成三码+ROM（机型填`iMac19,1`）
  2. 用[ProperTree](https://github.com/corpnewt/ProperTree)工具打开`config.plist`文件，进入`PlatformInfo` -> `Generic ` 填入三码。

### 更新记录

- 2022年03年06日
  - 更新OpenCore 0.7.8