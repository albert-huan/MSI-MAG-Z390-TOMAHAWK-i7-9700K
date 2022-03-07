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

#### BIOS设置

> 升级最新BIOS
>
> 同时请设置语言为简体中文并进入高级模式（F7）。

必要设置：

- OC(Overclocking) -> CPU 特征 -> Intel 虚拟化技术 **[允许]**
- OC(Overclocking) -> CPU 特征 -> Intel VT-D 技术 **[禁止]**
- OC(Overclocking) -> CPU 特征 -> CFG锁定 **[禁止]**

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