# OMEN by HP Laptop 15-ce007tx

> 本人机型：OMEN by HP Laptop 15-ce007tx

## [英文版](README-ENG.md)

### 配置

| 产品名称 | OMEN by HP Laptop 15-ce007tx                |
| ----------------- | ----------------------------------------- |
| BIOS              | F.20               |
| 处理器            | Intel(R) Core(TM) i7-7300HQ CPU  |
| 独立显卡           | NVIDIA GeForce GTX 1050ti                 |
| 显卡              | Intel(R) HD Graphics 630                  |
| 声卡              | ALC295                    |
| 硬盘              | C2000Pro 1TB、HGST 1T      |

## Progress 进展
- 引导方式
  - `CLOVER` 已支持，具体版本号见 `Release`
  - `OpenCore` 已支持，运行版本 0.5.7
- 系统支持
  - 理论支持 macOS High Sierra 10.13.6（17G65）- Catalina 10.15.4（19E266）之间的全部版本
  - 建议安装 macOS Mojave 10.14.6 或更高版本
- 电源管理
  - CPU变频：已启用 X86 原生电源管理，将闲时频率从 1.2GHz 降低到 0.8GHz，并更改 `EPP` 为节能模式（0x80）
  - 睡眠和唤醒：支持合盖睡眠和唤醒，支持 USB 设备唤醒（当使用电池进行睡眠时，所有外置设备将自动断电无法进行唤醒），`CLOVER` 下可能出现 `RTC` 唤醒（如果开启电能小憩）
  - 电池显示：电量百分比可显示，充放电正常，开启 X86 原生电源管理后状态栏百分比多于实际值，目前尚不明确具体原因，因此从100%满电开始放电时电量变化将会比较缓慢（即便实际值已经是95%状态栏仍然显示为100%）
- 核显 HD630
  - 使用HD615（591C0005）驱动Type-C输出DP显示
  - 显示正常，支持完整的 `H.264` 和 `HEVC` 解码
  - 支持亮度调节和保存
  - 支持 `FN` 快捷键调节亮度
  - 如需使用 `HiDPI` 请参考网上的教程，使用脚本开启容易出现花屏问题
- USB
  - 已经正确定制所有端口，USB3.0正常，端口显示最大速率 5 Gbps
- 网卡
  - 有线网卡：Realtek RTL8111 千兆网卡，正常工作
  - 无线网卡为螃蟹网卡无解 （蓝牙以及无线更换了BCM94360CS2）
    注：转接卡之后要断掉一截pcb并且网卡无法使用螺丝固定
- 声卡
  - 使用AppleALC其layout-id为 14 (0.5.8的OC已修复唤醒无外放问题）
- 触摸板
  - 使用VoodooPS2以及VoodooInput时我的不可用如果有相同情况请自行更换为applePS2
- 读卡器
  - 不带驱动，需要使用请自行寻找驱动（Sinetek-rtsx.kext）
## Instruction 使用说明
  - 注：如果使用之后电池不变 请关机长按电源键出了一个滴声音，重置电池即可
  - 如果需要双系统无缝切换，建议将 `OpenCore` 设置为第一引导
  - 建议所有机友更新 `BIOS` 和 `ME` 固件
### 无效功能
- 独显是没法驱动的，这个大家都知道！
- 由于独显没法驱动，所以HDMI、miniDP 无法使用！
- 其它问题暂时没发现，或者没注意到，毕竟每个人的使用程度不一样，我的要求就是能简单的娱乐办公就行了！

### 一些参考教程
黑果小兵[小兵博客系统下载](https://blog.daliansky.net/)

宪武[OC部件](https://github.com/daliansky/OC-little)

xjn博客[使用OpenCore引导黑苹果](https://blog.xjn819.com/?p=543)


### 安装完之后可以干些什么？

我也不知道我只是日常使用

### 致谢
- 感谢[miit0o](https://github.com/miit0o)将本指南翻译成英文
- 感谢 [xjn](https://blog.xjn819.com/?p=543)提供OC配置文件教程
- 感谢 [黑果小兵](https://blog.daliansky.net/OpenCore-BootLoader.html)提供的OC精解
- 感谢 [iStarForever](https://github.com/XStar-Dev)帮助完善热补丁以及OpenCore
- 感谢各位群友帮助解决各种问题

### 常见问题

**Q:如何进入BIOS或者设置启动项？**

A:开机后按下ESC键，然后根据指引选择

**Q:为什么在你的电脑上可以，而我的电脑上不行呢？**

A:我也不知道，您可以尝试问一下你的电脑:为什么你不行？

**Q:为什么没有HiDPI？**

A:我并不能解决所有的问题，如果您能向我提供帮助，那么太感激您了！

联系方式：Hatsune._Miku@outlook.com
  QQ群号：1062513799
