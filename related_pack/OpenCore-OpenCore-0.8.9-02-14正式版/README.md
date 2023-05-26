黑苹果OpenCore开放群，群号:9422866，注明“独行秀才Blog引入”

具体使用请参阅[OpenCore配置文字说明第十五版](https://shuiyunxc.gitee.io/2020/03/10/instru/index/)

同步OpenCore官方源码，自编译。

更新日志。

2023-02-14编译OpenCore-0.8.9-02-14正式版

- 改进了应用ACPI补丁时的调试日志记录
- 修正了在没有苹果安全引导的情况下，使用传统引导加载macOS的问题
- 添加Linux支持的传统引导BootInstall脚本
- 更新了SMBIOS和其他内置固件版本
- 修正了在图形模式启动时控制台模式初始化不完整的问题
- 提供额外的UEFI锻造模式，用于固件驱动程序
- 实现了固件驱动程序，在efi时代mac上非本地支持的gpu上启用pre-OpenCore图形
- 在图形模式下防止不必要的清晰屏幕到控制台背景颜色
- 增加了ResizeUsePciRbIo项，以解决一些UEFI固件上损坏的PciIo，谢谢@xCuri0
- 修复了在旧的Atom系统上使用SysReport时崩溃的问题
- 修复了在无缓存引导期间没有内容文件夹的kexts不被修补的问题
- 在支持的情况下，为所有驱动程序增加(.rdata)，以更好地保护内存
- 修复了在非音频HDA编解码器的系统上使用SysReport时崩溃的问题
- 修正了对GDB和LLDB的调试脚本支持
- 修正了在macOS加载时遗留的引导调试构建中断

2023-01-02编译OpenCore-0.8.8-01-02正式版

- 更新底层EDK II包到edk2-stable202211
- 更新macOS 13.1中的AppleKeyboardLayouts.txt
- 更新了SMBIOS和其他内置固件版本
- 更新ocvalidate，允许重复工具，如果FullNvramAccess是不同的
- 修复Kernel` -> `Block由于Arch而跳过了一个条目，则不会处理块条目
- 修正了启用kext阻塞时由于XML损坏而导致的间歇性预链接失败
- 从OpenCore文件中删除了用于拾取器隐藏的magic Acidanthera 序列号
- 增加了.contentVisibility来隐藏和禁用引导项
- 增加Linux支持QemuBuild.command用于Duet调试
- 内置新的安全PE/COFF装载机
- 添加预构建的mtoc通用二进制与苹果硅支持
- 修正了OpenDuet在Apple Silicon上的构建
- 添加SD卡设备路径支持启动设备选择

2022-12-07编译OpenCore-0.8.7-12-07正式版

- 启动非文本启动项时删除了不需要的透明屏幕
- 固定了ProvideCurrentCpuInfo中AMD CPU的TSC/FSB，
- 添加了Misc - Boot -Hibernate SkipsPicker，以在从macOS休眠中醒来时不显示选择器
- 将macrecover更改为将文件下载到com.apple.recovery。默认情况下启动，
- 在MacPro5,1等设备上运行不支持Mac efi的GPU时，支持Apple内置选择器（使用BootKicker.efi或PickerMode Apple）
- 已启用PickerMode Apple以成功启动所选条目
- 已启用BootKicker。efi成功启动选定的条目（通过重新启动）
- 将防欺骗UEFI 2.x检查添加到OpenVariableRuntimeDxe，

2022-11-07编译OpenCore-0.8.6-11-07正式版

- 更新的NVRAM保存脚本与早期macOS兼容（雪豹+测试）
- 更新了NVRAM保存脚本，可自动安装为启动守护程序（Yosemite+）或注销挂钩（旧版macOS）
- 固定非标准轮询频率的最大点击持续时间和双击速度
- 添加了对指针停留单击的支持
- 修复了某些系统上第一个非早期日志行的递归循环崩溃
- 修复了使用不安全的快速文件记录时的早期日志保存
- 更新了SMBIOS和其他系统的内置固件版本
- 使用独立模拟NVRAM驱动程序解决EFI 1.1系统（包括早期Mac）上的睡眠唤醒故障
- 更新了macOS 12和13的macrecovery命令，thx@Core-i99
- 用macOS特定的STA更新SSDT-BRG0，以避免Windows上的兼容性问题，thx@Lorys89
- 修复了OpenLinuxBoot中导致32位UEFI固件崩溃的内存问题

2022-10-06编译OpenCore-0.8.5-10-05正式版

- 更新了SMBIOS和其他版本的内置固件
- 已将仅存在于Windows Server 2022中的CPU对象移动到SSDT-HV-DEV-WS2022.dsl中
- 更新了Hyper-V设备路径扩展，以支持热添加/删除磁盘
- 改进了内核修补期间的详细日志记录

2022-09-06编译OpenCore-0.8.4-09-06正式版

- 在ocvalidate中增加了对Driver -> LoadEarly的检查
- 为需要直接访问NVRAM的工具增加了FullNvramAccess选项
- SSDT-HV-CPU所取代。与SSDT-HV-DEV dsl。dsl，以兼容Windows 10上的macOS旧版本和新版本
- 将内置zlib库更新为1.2.12
- 更改ocpasswordgen在密码输入时不打印字符
- 增加了基于配置测试kext注入的ProcessKernel实用程序
- 修复了在奔腾4系统上使用SysReport时崩溃的问题
- 修复了在使用DEBUG构建和文件日志记录时调用ExitBootServices()后的崩溃
- 修复了macOS上的32位用户空间构建支持(使用High Sierra 10.13及以下版本)
- 增加了基本的NetworkPkg驱动程序与HTTP引导支持

2022-08-13编译OpenCore-0.8.4-08-13编译版

- 在oc validate中增加了对Driver -> LoadEarly的检查
- 为需要直接访问NVRAM的工具增加了FullNvramAccess选项
- 以SSDT-HV-CPU.dsl所取代SSDT-HV-DEV.dsl，以兼容Windows 10上的macOS旧版本和新版本

2022-08-01编译OpenCore-0.8.3-08-01正式版

- 增加了——show-csr选项切换SIP启动菜单项
- 添加了macOS 10.4和10.5支持AllowRelocationBlock Booter quirk
- 在ProvideCurrentCpuInfo quirk中增加了macOS 10.4的CPU缓存信息注入
- 增加了独立于OpenDuet使用的仿真NVRAM驱动程序
- 增加了对NVRAM重置的支持，并在使用仿真NVRAM时设置默认启动项
- 升级模拟NVRAM注销脚本，以允许无监督安装最近的macOS OTA更新
- 增加了Driver -> LoadEarly用于NVRAM初始化前需要加载的驱动

202207-28编译OpenCore-0.8.3-07-28编译版

- 修正了在macOS 10.4.11下执行无缓存引导时选择FAT二进制片的错误
- 修复了在OpenCanopy中标签动画初始化导致的罕见中断
- 增加了——show-csr选项切换SIP启动菜单项
- 添加了macOS 10.4和10.5支持AllowRelocationBlock Booter项
- 在ProvideCurrentCpuInfo 项中增加了macOS 10.4的CPU缓存信息注入

202207-23编译OpenCore-0.8.3-07-23编译版

- 更新版本号为0.8.3
- 增加ext4文件系统驱动
- 增加了对macOS 13 DP3内核集合的支持
- AudioDxe增加了-force-device选项，允许在HDA控制器上出现UEFI音频，误报为非HDA音频设备
- 提供可选的不安全的快速文件日志记录(仅适用于具有完全兼容的FAT32驱动程序的固件)
- 修复了在无缓存注入时错误的OSBundleLibraries_x86_64处理
- 更改RsaTool不链接macOS上的系统ssl
- 修正了启用kext阻塞时无缓存注入时的崩溃
- 从AudioDxe删除默认编解码器连接延迟
- 添加了可选的——codec-setup-delay参数到AudioDxe
- 将Audio -> SetupDelay的单位从微秒改为毫秒(如果使用此设置，则将之前的值除以1000)

2022-07-05编译OpenCore-0.8.2-07-05正式版

- 在调试版本中添加了注入的kext捆绑包版本打印
- 为CreateVault脚本添加了Linux兼容性

2022-06-12编译OpenCore-0.8.2-06-12编译版

- 修复在macOS 13上的“AppleCpuPmCfgLock”错误
- 修复在macOS 13上的“DummyPowerManagement”错误
- 更新了SMBIOS和其他系统的内置固件版本
- 添加macOS 13对“AvoidRuntimeDefrag”项的支持，也就是可以勾选此项

2022-06-06编译OpenCore-0.8.1-06-06正式版

- 在更新的macOS版本上改进了ExtendBTFeatureFlags项
- 增加了关于DMAR表和ForceAquantiaEthernet
- 在LauncherOption属性中添加了系统选项
- 关于CustomPciSerialDevice的更新说明
- 为NTFS添加了只读驱动程序
- 切换重置NVRAM并将SIP切换到可配置的引导入口协议驱动程序
- 支持可选Apple固件本机NVRAM重置
- 支持的NVRAM重置（可选地保留BIOS引导条目）
- 切换SIP支持的用户指定的csr活动配置值
- 为切换SIP添加了可选的启用和禁用样式（允许主题设计器提供不同的图标）
- 为Hyper-V Gen1 VM上的TSC计算添加了PIIX4 ACPI PM计时器检测

2022-04-27编译OpenCore-0.8.1-04-27编译版

- 更新版本号为0.8.1
- 在较新的macOS版本上改进了ExtendBTFeatureFlags的quirk项

2022-04-19编译OpenCore-0.8.0-04-19正式版

- 增加了Misc ->Serial 自定义串口属性
- 增加了CustomPciSerialDevice项，使XNU能够正确识别定制的外部串行设备

2022-03-13编译OpenCore-0.8.0-03-23编译版

- 在脚本中切换到Python 3(使用Python /path/to/script强制Python 2)
- 增加ForceAquantiaEthernet项，支持aququantia AQtion基于AQC-107s的10GbE网卡，感谢@Mieze和@Shikumo
- 更新SMBIOS和其他内置固件版本

2022-03-13编译OpenCore-0.8.0-03-13编译版

- 更新版本号为0.8.0
- 支持早期日志的保存





特别是不能在远景论坛转载！可能被远景因此封号，谢谢合作
