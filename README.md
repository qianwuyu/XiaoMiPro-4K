# 小米笔记本Pro-4K 2017/2018 Hacintosh Bootloader

引用说明：本引导是针对Github上 [daliansky](https://github.com/daliansky/) 用户的 [XiaoMi-Pro-Hackintosh](https://github.com/daliansky/XiaoMi-Pro-Hackintosh) 仓库 EFI 进行更改适配，已跟多次更新该 EFI 的 [stevezhengshiqi]() 沟通，同意设立第三方仓库，以方便更改过配置的小米笔记本Pro用户，特此告知！

更新将从 2020.6.25 开始，针对最新 `release`  ，同时改配 `Clover` 与 `OpenCore` 。

### 目录

- [魔改后配置说明]()
- [安装前须做]()
- [蓝牙解决方案]()
- [鸣谢]()

### 魔改后配置说明

|   规格   |             详细信息             |
| :------: | :------------------------------: |
| 电脑型号 |   小米笔记本Pro 15.6‘’(MX150)    |
|  处理器  |      Intel i5-8250u 处理器       |
|   内存   |         8GB 升级为 16GB          |
|   硬盘   |  PM981 256GB更换为HP EX 900 1TB  |
| 集成显卡 |          Intel UHD 620           |
|  显示器  | 更换为 4K 内置显示屏（15.6英寸） |
|   声卡   |     瑞昱 ALC298 (节点:30/99)     |
|   网卡   |        更换为BCM 94360CS2        |
|  读卡器  |      瑞昱 RTS5129/RTS5250S       |

### 安装前需做

- 因笔记本屏幕更换为4K，所以需要先解锁 DVMT 至 64 MB，具体解锁方式请参考 [DVMT_and_0xE2_fix](https://github.com/daliansky/XiaoMi-Pro-Hackintosh/blob/master/BIOS/DVMT_and_0xE2_fix) .

- 为了更好的体验，建议同时解锁 CFG 与 Voltage Shift 

### 蓝牙解决方案

蓝牙常见方案有以下几种，如果需要具体实施方案见[蓝牙解决方案](https://github.com/daliansky/XiaoMi-Pro-Hackintosh/wiki/蓝牙解决方案)：

- 插入USB蓝牙 （SSDT-USB-USBBT.aml）
- 焊接并飞线至WLAN_LTE卡槽 （SSDT-USB-WLAN_LTEBT.aml）
- 焊接并飞线至指纹端口 （SSDT-USB-FingerBT.aml）
- 使用虚拟机上传蓝牙固件（不做讨论）

如果并非如我一般飞线至WLAN_LTE卡槽，请先将相应文件更名为 `SSDT-USB.aml` ，复制到 `EFI\OC\ACPI\SSDT-USB.aml` 或者 `EFI\CLOVER\ACPI\patched\SSDT-USB.aml` 完成替换。

### 鸣谢

感谢 [stevezhengshiqi]() 为小米笔记本Pro黑苹果所做出的贡献；