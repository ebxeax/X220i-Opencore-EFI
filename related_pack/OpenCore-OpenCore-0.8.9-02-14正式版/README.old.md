2022-03-08编译OpenCore-0.7.9-03-08正式版

- 更新基础包 EDK II package 到 edk2-stable202202

2022-02-13编译OpenCore-0.7.9-03-03编译版

- 修复了启用AVX加速时可能出现的内存报错
- 添加了日志模块，用于按模块进行正向和反向日志过滤
- 将OpenLinuxBoot驱动程序参数从partuuidpts:{PARTUUID}重命名为autoopts:{PARTUUID}
- 支持从独立/boot分区启动Linux，而不使用/loader/entries文件（用户必须指定完整的内核启动选项）
- 在驱动程序参数中处理XML实体

2022-02-13编译OpenCore-0.7.9-02-13编译版

- 更新版本号为0.7.9
- 添加自动检测macOS安装程序卷名，以便在安装时使用 .disk_label文件无法正常显示。
- 添加--restore-nosnoop 标志恢复到AudioDxe，修复v0。7.7 Windows声音选择
- 增加一个新方法，当SetApfsTrimTimeout设置为0时禁用修剪
  修正了macOS 12上的SetApfsTrimTimeout（仅在设置为零时有效）
- 为macrecovery添加了构建qemu恢复映像的脚本
- 修复了在虚拟机监控程序上选择SecureBootModel的问题（应该是x86legacy）
- 为预链接和更新版本添加了kext阻止策略
  添加了全局MSR 35h修复程序以提供当前CPUINFO，允许KVM中的-cpu主机

2022-02-08编译OpenCore-0.7.8-02-08正式版

- 更新了ocvalidate，以警告使用secure SecureBootModel加载不安全的DmgLoading（在运行时已被禁止）
- 修复了AudioDxe最近更新后未禁用未使用频道的问题
- 允许gain在没有SystemAudioVolumeDB的情况下跟踪旧macOS上的操作系统音量
- 修复了验证密码时没有鼠标支持的崩溃问题
- 修复了启用ProvideCustomSlide时设置的AppleInternal CSR位
- 增加了对的支持。满足口味和口味。启动条目协议条目的contentDetails文件，包括OpenLinuxBoot
- 在OpenLinuxBoot中添加了LINUX_BOOT_ADD_RW标志，以支持例如奋进
- 在OpenLinuxBoot中添加了flags+=和flags-=参数，以在需要时简化驱动程序标志的设置
- 修复了当LINUX_BOOT_USE_LATEST标志清除时OpenLinuxBoot条目名称的歧义
- 更新了SMBIOS和其他系统的内置固件版本
- 修复了部分（重新）安装Linux发行版的OpenLinuxBoot中的崩溃
- 改进了错误PE图像文件解析的正确性

2022-01-13编译OpenCore-0.7.8-01-13编译版

- 更新版本号为0.7.8
- 更新ocvalidate，对不安全的' DmgLoading '与安全的' SecureBootModel '(在运行时已经不允许)发出警告
- 修正了AudioDxe在0.7.7更新后不会禁用未使用的通道

2022-01-11编译OpenCore-0.7.7-01-11正式版

- 添加了VREF处理，以在更多苹果硬件上支持UEFI声音
- 更新音频输出通道检测，在更多苹果硬件上支持UEFI声音
- 添加了手动GPIO配置（在Apple硬件上为UEFI声音使用--GPIO设置AudioDxe驱动程序参数）
- 将UEFI音频电平切换为分贝增益，以便准确匹配已保存的macOS音量
- 最小音频辅助音量和最小音频音量的单独设置

2022-01-04编译OpenCore-0.7.7-01-04编译版

- 修复了Nvidia HDA音频出现时AudioDxe启动暂停的问题
- 解决了AudioDxe在某些固件上禁用Windows中的声音的问题
- 在内置AppleEvent实现中添加了指针轮询周期的调整
- 在内置AppleeEvent实现中添加了设备指针列表的调整

2021-12-22编译OpenCore-0.7.7-12-22编译版

- 修正了 Intel Rocket Lake或更新的Cpuid1Data建议中的拼写错误。
- 更新SMBIOS和其他内置固件版本。
- 更新基础EDK II包到edk2-stable202111
- 解决AudioDxe中两个可能的QEMU崩溃
- 增加AudioDxe设置缓存(避免不必要的设置延迟)
- 添加DisconnectHda quirk，允许在苹果硬件(和其他)上UEFI声音
- 添加自动检测的Cirrus Logic GPIO使能UEFI声音在苹果硬件
- 在QEMU intelhda驱动程序中增加了bug的解决方案，允许在QEMU中UEFI sound
  实现多通道(如低音+主扬声器;扬声器+耳机)UEFI声音配置AudioOutMask

2021-12-14编译OpenCore-0.7.7-12-14编译版

- 例行更新。

2021-12-12编译OpenCore-0.7.7-12-12编译版

- 增加ProvideCurrentCpuInfo对Intel Alder Lake的支持
- 修正Cpuid1Data，应对Intel Rocket Lake和后续更新的CPU。

2021-12-10编译OpenCore-0.7.7-12-10编译版

- 例行更新。

2021-12-08编译OpenCore-0.7.7-12-08编译版

- 更新版本号为0.7.7
- 修复由入口点中的寄存器损坏导致的罕见崩溃。

2021-12-06编译OpenCore-0.7.6-12-06编译版

- 修复处理zero-sized内存属性表

2021-12-04编译OpenCore-0.7.6-12-04编译版

- 已删除不推荐的SSDT-PNLFCFL

2021-12-02编译OpenCore-0.7.6-12-02编译版

- 例行更新

2021-11-30编译OpenCore-0.7.6-11-30编译版

- 添加BiosVideo.efi驱动程序，用于重新连接图形连接
- 更改FadtEnableReset，以避免不可靠的键盘控制器重置
- 添加EnableVmx项，允许在Mac上的其他操作系统中进行虚拟化
- 升级ProtectUefiServices，以防止在启用安全引导的情况下进行链加载GRUB shim时覆盖服务指针

2021-11-28编译OpenCore-0.7.6-11-28编译版

- 增加了ReconnectGraphicsOnConnect选项，启用替代UEFI图形驱动程序

2021-11-26编译OpenCore-0.7.6-11-26编译版

- 修复ScanPolicy中带有逻辑单元的处理设备路径

2021-11-24编译OpenCore-0.7.6-11-24编译版

- 例行更新

2021-11-22编译OpenCore-0.7.6-11-22编译版

- 例行更新

2021-11-20编译OpenCore-0.7.6-11-20编译版

- 例行更新

2021-11-18编译OpenCore-0.7.6-11-18编译版

- 更新了绘图顺序，以避OpenCorporation中的图像变形

2021-11-16编译OpenCore-0.7.6-11-16编译版

- 修复PROVIDECOLEGOP未禁用仅限blit模式的问题（例如，在Z690上）
- 修复Alder Lake SMBIOS CPU型号信息
- 给Intel Alder Lake添加了XCPM CPU电源管理ACPI表

2021-11-14编译OpenCore-0.7.6-11-14编译版

- 例行更新

2021-11-12编译OpenCore-0.7.6-11-12编译版

- 更新了恢复下载命令，包括macOS 11和12

2021-11-10编译OpenCore-0.7.6-11-10编译版

- 修复了OpenCanopy长标签在图形背景上淡出的问题

2021-11-08编译OpenCore-0.7.6-11-08编译版

- 例行更新

2021-11-06编译OpenCore-0.7.6-11-06编译版

- 修正了使用GCC编译时对stack canary的支持
- 增加了自动缩放因子检测
- 显式限制ResizeAppleGpuBars为0和-1

2021-11-04编译OpenCore-0.7.6-11-04编译版

- 更新版本号为0.7.6

2021-11-02编译OpenCore-0.7.5-11-02正式版

- 0.7.5正式版

2021-10-31编译OpenCore-0.7.5-10-31编译版

- 更新了恢复下载命令，包括macOS 11和12

2021-10-29编译OpenCore-0.7.5-10-29编译版

- 例行更新

2021-10-27编译OpenCore-0.7.5-10-27编译版

- 更新内置固件版本的SMBIOS和其他相关内容

2021-10-25编译OpenCore-0.7.5-10-25编译版

- 例行更新

2021-10-23编译OpenCore-0.7.5-10-23编译版

- 在下载DMG过程中增加了签名检查

2021-10-21编译OpenCore-0.7.5-10-21编译版

- 例行更新

2021-10-19编译OpenCore-0.7.5-10-19编译版

- 例行更新

2021-10-17编译OpenCore-0.7.5-10-17编译版

- 例行更新

2021-10-15编译OpenCore-0.7.5-10-15编译版

- 例行更新

2021-10-13编译OpenCore-0.7.5-10-13编译版

- 增加了GPU调整BAR项，以减少每个操作系统的BAR

2021-10-11编译OpenCore-0.7.5-10-11编译版

- 例行更新

2021-10-09编译OpenCore-0.7.5-10-09编译版

- 修订OpenLinuxBoot文档
- 支持Linux osree引导布局
- 修复了启动入口协议的外部驱动器图标

2021-10-07编译OpenCore-0.7.5-10-07编译版

- 更新版本号为0.7.5

2021-10-05编译OpenCore-0.7.4-10-05正式版

- 增加了从GRUB shim文件中提取供应商安全启动证书的工具
- 增加了bridgesharwaremodel NVRAM变量来修复macOS 12上的T2 SB AP模型
- 更改默认苹果安全启动模式，以匹配macOS 12的SMBIOS
- 修正了未添加到NVRAM变量的opencore版本

2021-10-03编译OpenCore-0.7.4-10-03编译版

- 例行更新

2021-10-01编译OpenCore-0.7.4-10-01编译版

- 例行更新

2021-09-29编译OpenCore-0.7.4-09-29编译版

- 更新了SMBIOS和其他系统的内置固件版本

2021-09-27编译OpenCore-0.7.4-09-27编译版

- 例行更新

2021-09-25编译OpenCore-0.7.4-09-25编译版

- 更新了SMBIOS和其他系统的内置固件版本

2021-09-23编译OpenCore-0.7.4-09-23编译版

- 在AdviseFeatures中增加了对 large BaseSystem的支持

2021-09-21编译OpenCore-0.7.4-09-21编译版

- 例行更新

2021-09-19编译OpenCore-0.7.4-09-19编译版

- 例行更新

2021-09-17编译OpenCore-0.7.4-09-17编译版

- 例行更新

2021-09-15编译OpenCore-0.7.4-09-15编译版

- 增加完全覆盖自动检测Linux启动选项的能力

2021-09-13编译OpenCore-0.7.4-09-13编译版

- 修复针对更多传统CPU的CPU核心计数检测

2021-09-11编译OpenCore-0.7.4-09-11编译版

- 修复Linux内核排序顺序
- 添加Linux引导可选日志详细信息

2021-09-09编译OpenCore-0.7.4-09-09编译版

- 更新版本后至0.7.4

2021-09-07编译OpenCore-0.7.3-09-07正式版

- 添加ForceOcWriteFlash UEFI quirk项以启用写入OC系统变量

2021-09-06编译OpenCore-0.7.3-09-06编译版

- 更新了Flavours.md中的Linux变体
- 实现了引导入口协议，允许插件引导入口驱动程序
- 添加了StringBuffer和FlexArray库
- 更新驱动程序以支持参数（需要config.plist更新，请参见示例）
- 添加了OpenLinuxBoot驱动程序：OC本机Linux自动检测和引导，无需通过GRUB链接
- 修复了过长的启动条目名称破坏内置菜单中的文本流的问题

2021-09-04编译OpenCore-0.7.3-09-04编译版

- 将基础EDK II包更新为edk2-stable202108
- 更新x86legacy的Apple安全引导变量

2021-09-02编译OpenCore-0.7.3-09-02编译版

- 例行更新

2021-08-31编译OpenCore-0.7.3-08-31编译版

- 例行更新

2021-08-29编译OpenCore-0.7.3-08-29编译版

- 例行更新

2021-08-27编译OpenCore-0.7.3-08-27编译版

- 例行更新

2021-08-25编译OpenCore-0.7.3-08-25编译版

- 例行更新

2021-08-23编译OpenCore-0.7.3-08-23编译版

- 例行更新

2021-08-21编译OpenCore-0.7.3-08-21编译版

- 修复了0.6.9中引入的重绘导致的OpenCanopy性能损失
- 增加了基于模式的自动变量初始化，以提高安全性

2021-08-19编译OpenCore-0.7.3-08-19编译版

- 例行更新

2021-08-17编译OpenCore-0.7.3-08-17编译版

- 更新Docs/Kexts.md

2021-08-15编译OpenCore-0.7.3-08-15编译版

- 例行更新

2021-08-13编译OpenCore-0.7.3-08-13编译版

- 更新Docs/Kexts.md

2021-08-11编译OpenCore-0.7.3-08-11编译版

- 例行更新

2021-08-09编译OpenCore-0.7.3-08-09编译版

- 改进了SSDT-PNLF与CFL+图形的兼容性

2021-08-07编译OpenCore-0.7.3-08-07编译版

- 例行更新

2021-08-05编译OpenCore-0.7.3-08-05编译版

- 更新版本号至0.7.3

2021-08-03编译OpenCore-0.7.2-08-03正式版

- OpenCore-0.7.2-08-03正式版

2021-08-01编译OpenCore-0.7.2-08-01编译版

- 更新Docs/Kexts.md

2021-07-30编译OpenCore-0.7.2-07-30编译版

- 例行更新

2021-07-28编译OpenCore-0.7.2-07-28编译版

- 例行更新

2021-07-26编译OpenCore-0.7.2-07-26编译版

- 改进了SSDT-PNLF与Windows和更新图形的兼容性
- 通过缩短OC magic改善CLANGPDB OpenCore的构建

2021-07-24编译OpenCore-0.7.2-07-24编译版

- 更新SMBIOS和其他系统的内置固件版本

2021-07-22编译OpenCore-0.7.2-07-22编译版

- 例行更新

2021-07-20编译OpenCore-0.7.2-07-20编译版

- 例行更新

2021-07-18编译OpenCore-0.7.2-07-18编译版

- 修复AudioDxe中未初始化的内存访问导致音频播放失败的问题
- 为更好的安全性和兼容性，将默认苹果安全启动模式改为x86legacy
- macOS Big Sur 增加默认APFS MinDate和MinVersion，以获得更好的安全性

2021-07-16编译OpenCore-0.7.2-07-16编译版

- 增加了对stack canaries的支持（安全cookies/堆栈保护）

2021-07-14编译OpenCore-0.7.2-07-14编译版

- 添加GraphicsInputMirroring以修复一些非Apple图形UEFI应用程序中键盘失效问题

2021-07-12编译OpenCore-0.7.2-07-12编译版

- 例行更新

2021-07-10编译OpenCore-0.7.2-07-10编译版

- 对OSBundleLibraries/osbundlelibraries64进行了修复

2021-07-08编译OpenCore-0.7.2-07-08编译版

- 更新版本号至0.7.2
- 修正macOS 12上的AppleXcpmForceBoost补丁

2021-07-06编译OpenCore-0.7.1-07-06正式版

- 更新0.7.1正式版

2021-07-04编译OpenCore-0.7.1-07-04编译版

- 修复macOS 12上的ProvideCurrentCpuInfo MSR修补程序

2021-07-02编译OpenCore-0.7.1-07-02编译版

- 例行更新

2021-06-30编译OpenCore-0.7.1-06-30编译版

- 修正OpenCanopy当默认输入超出屏幕右侧时不能正确显示的问题

2021-06-28编译OpenCore-0.7.1-06-28编译版

- 添加 DEBUG TPM状态的TpmInfo工具

2021-06-26编译OpenCore-0.7.1-06-26编译版

- 添加Apple12和Windows11相关特性

2021-06-24编译OpenCore-0.7.1-06-24编译版

- 修复在OpenCanopy中按change entry键和单个启动项时的DEBUG ASSERT

2021-06-22编译OpenCore-0.7.1-06-22编译版

- 修正了IA32上内置picker的错误超时
- 增加了对ESP分区上自定义内核的支持

2021-06-20编译OpenCore-0.7.1-06-20编译版

- 例行更新

2021-06-18编译OpenCore-0.7.1-06-18编译版

- 例行更新

2021-06-16编译OpenCore-0.7.1-06-16编译版

- 记录SetDefault.icns宽度与Selector.icns宽度的匹配
- 增加VSCode源代码级别的IDE调试配置示例来调试文档
- 增加其他次要的调试文档更新

2021-06-14编译OpenCore-0.7.1-06-14编译版

- 更新SMBIOS和其他系统的内置固件版本
- 修正macOS 12上的PowerTimeoutKernelPanic
- 修复OpenCanopy引导条目上的透明点击检测
- 已将PCI设备信息转储添加到SysReport
- 修正macOS 12上的SetApfsTrimTimeout
- 记录并添加现有要求的安全回退，设置默认宽度以匹配选择器宽度

2021-06-12编译OpenCore-0.7.1-06-12编译版

- 将CPU信息（MSRs）转储添加到SysReport

2021-06-10编译OpenCore-0.7.1-06-10编译版

- 更新版本号至0.7.1
- 添加SyncTableIds quirk以同步修改的OEM表单标识符

2021-06-08编译OpenCore-0.7.0-06-08正式版

- 正式版

2021-06-05编译OpenCore-0.7.0-06-05编译版

- 例行更新

2021-06-03编译OpenCore-0.7.0-06-03编译版

- 添加csr-data Apple NVRAM var到文档
- 修正文件对齐导致CLANGPDB图像协同设计问题
- 用AdviseFeatures替换AdviseWindows以支持APFS

2021-06-01编译OpenCore-0.7.0-06-01编译版

- 更新OC默认SIP关闭值
- 记录影响macOS更新的SIP值
- 添加csr-data Apple NVRAM var到文档

2021-05-30编译OpenCore-0.7.0-05-30编译版

- 增加可选的切换SIP系统启动菜单选项
- 添加了CsrUtil.efi工具，类似于Apple CsrUtil
- 删除了对<TOOLPATH>.lbl/.l2x预绘制条目标签的支持
- 修复了OpenCanopy中控制台模式工具和条目之前未清除的先前文本
- 修复了GopPassThrough和UgaPassThrough的调试生成崩溃
- 为内存测试实用程序添加了自定义
- 在sample.plist文件中更新了推荐的memtest86配置
- 增加自定义的引导程序风格
- 在OC构建中应用自定义
- 添加了CPU拓扑修复，以提供 ProvideCurrentCpuInfo quirk

2021-05-28编译OpenCore-0.7.0-05-28编译版

- 例行更新

2021-05-26编译OpenCore-0.7.0-05-26编译版

- 修复由于架构不匹配而跳过修补程序时未处理的其他内核修补程序

2021-05-24编译OpenCore-0.7.0-05-24编译版

- 添加了Hyper-V设备路径扩展以允许设置默认启动卷
- 添加了GopPassThrough的Apple变体，以仅处理AppleFramebufferInfo句柄

2021-05-22编译OpenCore-0.7.0-05-22编译版

- 例行更新

2021-05-20编译OpenCore-0.7.0-05-20编译版

- 已删除对<BOOTPATH>.icns和<TOOLPATH>.icns支持
- 添加个性化内容，允许自定义启动图标兼容的图标包
- 增加了macOS引导条目的自动个性化检测
- 添加了ProvideCurrentCpuInfo quirk，为Hyper-V虚拟机提供正确的TSC/FSB

2021-05-18编译OpenCore-0.7.0-05-18编译版

- 例行更新

2021-05-16编译OpenCore-0.7.0-05-16编译版

- 修复在LoadeImage和其他地方处理多节点设备路径的问题
- 已更改OpenCanopy映像目录以支持目录前缀
- 已将OpenCanopy首选图像集更改为acidathera\GoldenGate

2021-05-14编译OpenCore-0.7.0-05-14编译版

- 例行更新

2021-05-12编译OpenCore-0.7.0-05-12编译版

- 例行更新

2021-05-10编译OpenCore-0.7.0-05-10编译版

- 改进了某些情况下的direct GOP渲染器性能
- 增加了对direct GOP渲染器中显示旋转的支持

2021-05-08编译OpenCore-0.7.0-05-08编译版

- 例行更新
- 修复固件写保护BootOptionSupport时NVRAM复位

2021-05-06编译OpenCore-0.7.0-05-06编译版

- 更新版本号至0.7.0

2021-05-04编译OpenCore-0.6.9-05-04正式版

- 更新正式版

2021-05-02编译OpenCore-0.6.9-05-02编译版

- 修正在低分辨率运行OpenCanopy时的错误，现在会回退到内置

2021-04-30编译OpenCore-0.6.9-04-30编译版

- 用户空间实用程序添加bundled Linux
- 修复空插槽时返回SMBIOS制造商值无DIMM的问题

2021-04-28编译OpenCore-0.6.9-04-28编译版

- 更新SMBIOS及其他的内置固件版本

2021-04-26编译OpenCore-0.6.9-04-26编译版

- 例行更新

2021-04-24编译OpenCore-0.6.9-04-24编译版

- 修正在OpenCanopy中使用箭头键时循环的问题

2021-04-22编译OpenCore-0.6.9-04-22编译版

- 优化部分代码
- 例行更新

2021-04-20编译OpenCore-0.6.9-04-20编译版

- 根据现有的ExposeSensitiveData，添加了OpenCore版本号的显示到OpenCanopy以及内置界面
- 增加了对UEFI工具中不区分大小写的参数处理的支持
- 增加SHA-512和SHA-384哈希算法的矢量加速度

2021-04-18编译OpenCore-0.6.9-04-18编译版

- 优化部分代码
- 例行更新

2021-04-16编译OpenCore-0.6.9-04-16编译版

- 增加了OC_ATTR_USE_MINIMAL_UI，允许运行没有关机和重启按钮的图形界面

2021-04-14编译OpenCore-0.6.9-04-14编译版

- 添加ForgeUefiSupport quirk来解决遗留的efi1.x固件兼容性问题
- 添加ReloadOptionRoms quirk，以强制PCI设备上的加载选项ROM

2021-04-12编译OpenCore-0.6.9-04-12编译版

- 更新基础EDK II包为edk2-stable202102
- 应用所需最低Apple OEM以适应Apple Event协议版本
- 将CustomDelays更改为正常的布尔设置，默认设置为false
- 更改键盘重复故障保护和样本值的苹果OEM值
- 更改PointerSpeedMul故障安全到苹果OEM值
- 更新了文档，包括AMI KeySupport与V1或V2 KeySupport与不使用KeySupport的系统上的密钥重复设置配置
- 禁止不正确的安全配置时，防止“set default”UI

2021-04-10编译OpenCore-0.6.9-04-10编译版

- 优化部分代码
- 例行更新

2021-04-08编译OpenCore-0.6.9-04-08编译版

- 更新版本号为0.6.9
- 修正加载时光标矩形移动不同步的问题，例如CrScreenshotDxe

2021-04-06编译OpenCore-0.6.8-04-06正式版

- 修复了OpenCanopy字体高度计算，可能会拒绝以前使用的字体并减轻内存损坏
- 修复了Xeon E5XXX/E5-XXXX和Xeon WXXXX/W-XXXX CPU的错误标识
- 添加了RSDP、RSDT和XSDT处理NormalizeHeaders ACPI quirk

2021-04-04编译OpenCore-0.6.8-04-04编译版

- 添加PickerAudioAssist“磁盘映像”显示
- 修复罕见情况下两次播放PickerAudioAsist指示的问题
- 改进OpenCanopy指针加速
- 添加对AppleEvent协议属性和特性的更精确的控制
- 在CrScreenshotDxe上添加了动态键盘协议安装
- 支持启动带有参数支持的UEFI工具（例如ControlMsrE2），而不需要来自picker的参数

2021-04-02编译OpenCore-0.6.8-04-02编译版

- 匹配的默认Apple引导选择器光标的起始位置
- 更新了OpenShell devices命令，以支持某些苹果固件返回的不对齐的设备名称
- 在OpenCanopy中为dmg引导选项添加了（dmg）后缀
- 添加了Rocket Lake和Tiger Lake CPU的标识符

2021-03-31编译OpenCore-0.6.8-03-31编译版

- 优化部分代码

2021-03-29编译OpenCore-0.6.8-03-29编译版

- 将Escape映射到0键作为快捷键使用，以便在选盘界面隐藏时强制显示
  将CTRL映射到=/+键作为设置默认操作系统的快捷键使用
- 增加在KeySupport模式下，额外支持配置正确的密钥重复行为
- 修复在4核 Intel CPU上的CPU倍频检测
- 修复SMBIOS中多处理器和处理器缓存的错误

2021-03-27编译OpenCore-0.6.8-03-27编译版

- 修正刷新选票界面视图时OpenCanopy闪烁的问题
- 增加OpenCanopy标签导航支持
- 增加OpenCanopy图形密码界面
- 增加OpenCanopy的脉冲动画信号超时
- 增加OpenCanopy的“设置默认”指示器
- 修复OpenCanopy不会中止超时指针点击
- 修复OpenCanopy简介动画不能用UIScale缩放的问题
- 增加openencanopy启动项标签滚动(修复丢失的长标签)
- 增加选项卡关闭和重新启动按钮内建选择器
- 修复一些运行OpenDuet的系统固件关闭的问题

2021-03-25编译OpenCore-0.6.8-03-25编译版

- 增加苹果事件键盘处理，以改进OpenCanopy和内置选择器的按键响应
- 增加苹果键映射的边缘检测，以改进拾取器中的非重复键响应
- 修正一些PS/2系统上键盘处理的快速重复然后失速问题
- 使用PollAppleHotKeys改进Shift+Enter和Shift+Index行为
- 添加了CTRL-hold指示器到内置选择器
- 用ControlMsrE2替换VerifyMsrE2，也允许在某些固件上解锁

2021-03-23编译OpenCore-0.6.8-03-23编译版

- 优化部分代码

2021-03-21编译OpenCore-0.6.8-03-21编译版

- 改进OpenCanopy双击实用性
- 减少OpenCanopy触摸输入滞后，提高可用性

2021-03-19编译OpenCore-0.6.8-03-19编译版

- 修复OpenCanopy和FileVault 2光标的不正常移动
- 修复OpenCanopy中断处理导致的延宕事件和延迟

2021-03-17编译OpenCore-0.6.8-03-17编译版

- 添加ACPI补丁的Base和BaseSkip查询
- 修正在修补过程中ACPI表的损坏

2021-03-15编译OpenCore-0.6.8-03-15编译版

- 优化部分代码

2021-03-13编译OpenCore-0.6.8-03-13编译版

- 修正了SMBIOS SMC版本编码顺序
- 从苹果平台信息增加了TSC频率读取
- 为使用nForce芯片组的苹果设备增加了TSC频率读取

2021-03-11编译OpenCore-0.6.8-03-11编译版

- 进一步改进了传统CPU的CPU频率计算

2021-03-09编译OpenCore-0.6.8-03-09编译版

- 修复OpenCanopy有时会是开机显示菜单错误

2021-03-07编译OpenCore-0.6.8-03-07编译版

- 修复在根文件系统无法创建日志文件的问题
- 修复DisableSingleUser在某些情况下不被启用
- Mac EFI固件增加了ForceBooterSignature quirk

2021-03-05编译OpenCore-0.6.8-03-05编译版

- Windows版本切换为VS2019 toolchain
- 减少了旧式引导安装交互工作
- 提高了OpenCanopy渲染性能
- 减少OpenCanopy鼠标指针输入延迟
- 修正了光标边界可能与OpenCanopy的不同
- 改进的内置选取器渲染性能
- 在“自动”模式下为SMBIOS添加了内存类型解码
- 支持将自定义项设置为默认引导选项

2021-03-03编译OpenCore-0.6.8-03-03编译版

- 更新版本号为0.6.8

2021-03-02编译OpenCore-0.6.7-03-02正式版

2021-03-01编译OpenCore-0.6.7-03-01编译版

- 添加ResetTrafficClass以在legacy HDA上将TCSEL重置为T0
- 修复启动选票超时时，选择默认启动项
- 添加ocpasswordgen实用程序来生成OpenCore密码数据
- 添加ActivateHpetSupport quirk项来激活对HPET的支持
- 修复opencore版本在极少数情况下报告错误版本的问题

2021-02-27编译OpenCore-0.6.7-02-27编译版

- 修复FSB 频率计算以分数表示
- 修正一些AMD cpu显示核心数的问题

2021-02-25编译OpenCore-0.6.7-02-25编译版

- 移除KeyMergeThreshold
- 添加了acdtinfo实用程序来查找某些产品

2021-02-23编译OpenCore-0.6.7-02-23编译版

- 增加了GopPassThrough选项，以支持UGA上的GOP协议。
- 修复部分Xeon和Core 2 CPU频率

2021-02-21编译OpenCore-0.6.7-02-21编译版

- 为某些Apple SMBIOS表添加了OEM保护
- 修复切换到图形模式时使用OpenCanopy，
- 修正在没有GOP的情况下安装Apple-FB协议的问题

2021-02-19编译OpenCore-0.6.7-02-19编译版

- 在旧固件的调试版本中增加了早期版本的屏幕登录功能
- 新增引导时未指定DeviceHandle固件的解决方法
- 在SetupVirtualMap中增加了对R/O页表的支持

2021-02-17编译OpenCore-0.6.7-02-17编译版

- 增加了SSN(和HW_SSN)变量支持

2021-02-15编译OpenCore-0.6.7-02-15编译版

- 在自动模式下增加了OEM值到PlatformInfo
- 改进了Haswell和更早版本的CPU频率计算
- 修复了当应用某些补丁时的问题

2021-02-13编译OpenCore-0.6.7-02-13编译版

- 优化部分代码

2021-02-11编译OpenCore-0.6.7-02-11编译版

- 优化部分代码

2021-02-09编译OpenCore-0.6.7-02-09编译版

- 优化部分代码

2021-02-07编译OpenCore-0.6.7-02-07编译版

- 修复当发现问题时ocvalidate返回代码不为零的问题

2021-02-05编译OpenCore-0.6.7-02-05编译版

- 更新版本号至0.6.7

2021-02-03编译OpenCore-0.6.6-02-03正式版

- 修正EFI图像加载的多个缺陷，特别是APFS驱动程序
- 修正NVRAM系统id被意外地以Little-Endian格式存储的问题
- 添加UseRawUuidEncoding以选择SMBIOS UUID编码样式
- 更新SMBIOS等的内置固件版本

2021-02-01编译OpenCore-0.6.6-02-01编译版

- 修复了在SMBIOS的non-Automatic模式下从DataHub使用SystemUuid的问题
- 从通用模式删除故障保护默认值以匹配non-Automatic模式
- 用LauncherOption和LauncherPath替换了BootProtect
- 新增OpenPartitionDxe用于Apple分区管理方案
- 改进了Misc、NVRAM和UEFI部分中的ocvalidate检查

2021-01-30编译OpenCore-0.6.6-01-30编译版

- 优化部分代码

2021-01-28编译OpenCore-0.6.6-01-28编译版

- 在UEFI-Quirks项中添加DisableSecurityPolicy以解决驱动程序加载的问题
- 增加对AudioDxe中远程小部件连接的支持
- 修复为非macOS系统提供non-RT SetVirtualAddressMap的问题

2021-01-26编译OpenCore-0.6.6-01-26编译版

- 添加SetApfsTrimTimeout来优化APFS trim命令

2021-01-24编译OpenCore-0.6.6-01-24编译版

- 修复OpenUsbKbDxe在处理不支持的设备时崩溃的问题
- 移除HdaCodecDump 以支持SysReport

2021-01-22编译OpenCore-0.6.6-01-22编译版

- 修复了所有二进制文件与页面保护的兼容性

2021-01-20编译OpenCore-0.6.6-01-20编译版

- 将音频编解码器转储添加到SysReport中。

2021-01-18编译OpenCore-0.6.6-01-18编译版

- 优化部分代码

2021-01-16编译OpenCore-0.6.6-01-16编译版

- 优化部分代码

2021-01-14编译OpenCore-0.6.6-01-14编译版

- 用OpenHfsPlus替换VBoxHfs驱动程序

2021-01-12编译OpenCore-0.6.6-01-12编译版

- 将MaxBIOSVersion选项添加到Generic
- 修复macrecovery中的MLB验证功能

2021-01-10编译OpenCore-0.6.6-01-10编译版

- 图标文件添加了对应OpenCanopy的图标

2021-01-08编译OpenCore-0.6.6-01-08编译版

- 在OpenCanopy中添加了键盘和指针输入滚动支持
- 在OpenCanopy中添加了背景图像支持
- 放宽了OpenCanopy中的选择器引导选项的尺寸

2021-01-06编译OpenCore-0.6.6-01-06编译版

- 更新版本号至0.6.6

2021-01-05编译OpenCore-0.6.5-01-05-2021正式版

- 修复了OpenUsbKb与某些键盘的兼容性

2021-01-04编译OpenCore-0.6.5-01-04-2021编译版

- 重新修改了LogoutHook.command以支持老旧的macOS系统
- 音频助理实现对MP3音频解码的支持
- 增加了对PickerVariant的支持，以获得对更多变体主题的支持
- 增加了时间机器对的OC_ATTR_HIDE_THEMED_ICONS 选取器属性的支持

2021-01-02编译OpenCore-0.6.5-01-02-2021编译版

- 改进了对老旧Duet USB控制器的支持

2020-12-31编译OpenCore-0.6.5-12-31编译版

- 优化部分代码
- 例行更新

2020-12-29编译OpenCore-0.6.5-12-29编译版

- 优化部分代码
- 例行更新

2020-12-27编译OpenCore-0.6.5-12-27编译版

- 新增SetupDelay来配置音频设置延迟

2020-12-25编译OpenCore-0.6.5-12-25编译版

- 修复了处理无效序列时macserial崩溃的问题
- 修正了处理2021年系列时的macserial问题
- 在ocvalidate实用程序中增加了高级错误检查

2020-12-23编译OpenCore-0.6.5-12-23编译版

- 修正了使用自定义SMBIOS内存配置时的内存容量
- 删除不再需要UEFI-Quirks-DeduplicateBootOrder项

2020-12-21编译OpenCore-0.6.5-12-21编译版

- 修复启动时计时器分辨率的问题

2020-12-19编译OpenCore-0.6.5-12-19编译版

- 向编译ACPI包中添加了已编译的SSDT范例

2020-12-17编译OpenCore-0.6.5-12-17编译版

- 更新了SMBIOS内置固件版本
- 修复了macrecovery服务器协议兼容性
- 在OpenCanopy中添加了基本的音频助手支持

2020-12-15编译OpenCore-0.6.5-12-15编译版

- 例行更新

2020-12-13编译OpenCore-0.6.5-12-13编译版

- 修复在受保护卷上安装OpenDuet的问题
- 将EDK II基础包更新为edk2-stable20201

2020-12-11编译OpenCore-0.6.5-12-11编译版

- 例行更新

2020-12-09编译OpenCore-0.6.5-12-09编译版

- 更新版本号至0.6.5

2020-12-08编译OpenCore-0.6.4-12-08正式版

- 修正了OpenDuet中导致随机崩溃和挂起等未定义行为
- 编译OpenCore-0.6.4-12-08正式版

2020-12-07编译OpenCore-0.6.4-12-07编译版

- 在Booter patch部分添加了bootloader补丁支持
- 修复了firmware上的启动挂起问题，允许计时器函数重新进入
- 通过PickerAttributes使OpenCanopy的指针控制可选
- 在PlayChime中增加对StartupMute变量的支持
- 增加了对APFS预引导时的每卷图标的支持
- 已从OpenUsbKbDxe驱动程序中删除对HII的依赖项

2020-12-05编译OpenCore-0.6.4-12-05编译版

- 避免在RequestBootVarRouting中使用引导前缀来解决AMI问题

2020-12-03编译OpenCore-0.6.4-12-03编译版

- 例行更新

2020-12-01编译OpenCore-0.6.4-12-01编译版

- 增加了BootstrapShort，以解决Insyde固件de 错误
- 改变Bootstrap(Short) 选择动态入口(需要NVRAM重置)

2020-11-29编译OpenCore-0.6.4-11-29编译版

- 修复了启用Apple安全引导时"DisableSingleUser"的问题

2020-11-27编译OpenCore-0.6.4-11-27编译版

- 例行更新

2020-11-25编译OpenCore-0.6.4-11-25编译版

- 例行更新

2020-11-23编译OpenCore-0.6.4-11-23编译版

- 例行更新

2020-11-21编译OpenCore-0.6.4-11-21编译版

- 例行更新

2020-11-19编译OpenCore-0.6.4-11-19编译版

- 修复了更新链接

2020-11-17编译OpenCore-0.6.4-11-17编译版

- 修复了AMD 19h系列CPU频率计算问题

2020-11-15编译OpenCore-0.6.4-11-15编译版

- 修复了MacOS11.0上启用安全模式的问题
- 为老旧macOS和安全模式添加了AllowRelocationBlock选项

2020-11-13编译OpenCore-0.6.4-11-13编译版

- 例行更新

2020-11-11编译OpenCore-0.6.4-11-11编译版

- 例行更新

2020-11-09编译OpenCore-0.6.4-11-09编译版

- 通过RealPath为工具添加了直接路径
- 允许通过TextMode以文本模式启动选项和目录
- 更新了SMBIOS和其他系统的内置固件版本
- 修复了ACPI修补程序在锁定内存中时无法使用的问题

2020-11-07编译OpenCore-0.6.4-11-07编译版

- 修正了mkext中注入kexts的补丁
- 增加了对从相对路径启动的支持

2020-11-05编译OpenCore-0.6.4-11-05编译版

- 添加了BlacklistAppleUpdate来修复11.0更新的故障
- 从OpenDuet删除HII服务，提高了OpenDuet大小和性能

2020-11-03编译OpenCore-0.6.4-11-03编译版

更新版本号为0.6.4

 2020-11-03编译OpenCore-0.6.3-11-03正式版

- 增加了11.0所需的安全引导NVRAM变量
- 增加了system-id NVRAM变量的设置
- 为虚拟机添加了ForceSecureBootScheme项
- 修正了内核和ACPI补丁不能替换内存的最后字节

2020-11-01编译OpenCore-0.6.3-11-01编译版

- 给一些X299主板上的只读错误增加了解决方案
- 增加了对x86legacy安全引导模型的支持

2020-10-30编译OpenCore-0.6.3-10-30编译版

- 修正了Ps2MouseDxe在OpenDuetPkg下未正确加载

2020-10-28编译OpenCore-0.6.3-10-28编译版

- 添加ForceResolution选项以启用非默认分辨率

2020-10-26编译OpenCore-0.6.3-10-26编译版

- 修正了在选择MacPro5,1时的扫描策略 NVMe的问题
- 修复了平台上的I/O无法读取超过1MB的问题
- 修复了在Big Sur上plist-only kext注入的问题

2020-10-24编译OpenCore-0.6.3-10-24编译版

- 例行更新

2020-10-22编译OpenCore-0.6.3-10-22编译版

- 修正了老旧Atom cpu检测的问题

2020-10-20编译OpenCore-0.6.3-10-20编译版

- Fixed intermittent 32-bit prelinking failures caused by improper Mach-O expansion（无聊的更新）
- 修正了高速缓存注入时解析的错误

2020-10-18编译OpenCore-0.6.3-10-18编译版

- 修正了在blit-only GOP上可以直接启用渲染器
- 增加了对自定义内存属性的支持

2020-10-16编译OpenCore-0.6.3-10-16编译版

- 修正了奔腾M处理器上核心/线程计数的错误
- 补充SDT-UNC中部分内容。解决X99卡ACPI问题
- 更新了SMBIOS和其他设备的内置固件版本
- 将Big Sur beta 10的slide分配保留空间增加到200 MB

2020-10-14编译OpenCore-0.6.3-10-14编译版

- 修复了空插槽上内存数组配置的分配
- 修复了某些版本的macos10.4.10和10.4.11上的CPUID修补。（实在无聊）

2020-10-12编译OpenCore-0.6.3-10-12编译版

- 将EDK II基础包更新为edk2-stable202008
- 为空内存SMBIOS字符串提供帮助
- 修复了BOOTx64.efi和BOOTIA32.efi协议

2020-10-10编译OpenCore-0.6.3-10-10编译版

- 增加了对plist文件中xml注释的支持

2020-10-08编译OpenCore-0.6.3-10-08编译版

- 更新版本号为0.6.3

2020-10-06编译OpenCore-0.6.2-10-06正式版

- 官方编译正式版

2020-10-04编译OpenCore-0.6.2-10-04编译版

- Added prelinkedkernel 32-bit kext injection (10.6-10.7)（我懒得翻译毫无意义的更新）
- 添加了SystemMemoryStatus以支持某些型号的内存更换
- Added older Pentium CPU recognition in SMBIOS（我懒得翻译毫无意义的更新）
- 添加ExtendBTFeatureFlags来正确设置蓝牙的FeatureFlags(替代BT4LEContinuityFixup)
- 添加MinKernel/MaxKernel到CPUID仿冒和DummyPowerManagement
- Fixed -legacy not being added in KernelArch Auto mode（我懒得翻译毫无意义的更新）
- Fixed i386-user32 not forcing i386 on macOS 10.7 on X64 firmwares（我懒得翻译毫无意义的更新）
- Fixed i386-user32 being incorrectly enabled in macOS 10.4, 10.5, and 10.7（我懒得翻译毫无意义的更新）
- Disabled prelinked boot for macOS 10.4 and 10.5 in KernelCache Auto mode我懒得翻译毫无意义的更新）
- 修复了从2020年开始的macserial与iMac20、x系列和其他机型的兼容性，
- 添加LegacyCommpage quirk 来改进ssse3之前的用户空间兼容性
- 修复在选盘阶段 legacy SATA HDDs 显示为外部驱动器

2020-10-02编译OpenCore-0.6.2-10-02编译版

- 例行更新

2020-09-29编译OpenCore-0.6.2-09-29编译版

- 例行更新

2020-09-27编译OpenCore-0.6.2-09-27编译版

- 例行更新

2020-09-25编译OpenCore-0.6.2-09-25编译版

- 增加类型保留内存，以满足休眠hack的需要
- 增加了解决方案,以显示Macintosh HD 而不是Preboot

2020-09-23编译OpenCore-0.6.2-09-23编译版

- 例行更新

2020-09-21编译OpenCore-0.6.2-09-21编译版

- 例行更新

2020-09-19编译OpenCore-0.6.2-09-19编译版

- 修正了加载10.7 EfiBoot的问题（无聊之举）

2020-09-17编译OpenCore-0.6.2-09-17编译版

- 例行更新

2020-09-15编译OpenCore-0.6.2-09-15编译版

- 在发布包中添加了IA32二进制 release bundles包
- 修正了在没有Info.plist的情况下处理cacheless kexts的错误
- 修正了错误kext启动地址导致的卡死
- 添加了mkext 32位kext注入(10.4-10.6)（无聊）
- 增加了cacheless 32位kext注入(10.4-10.7)（无聊）
- 增加了32位内核/kext补丁/卡死支持（无聊）

2020-09-13编译OpenCore-0.6.2-09-13编译版

- 在Generic中添加了ProcessorType选项，允许自定义CPU名称
- 修正了UnblockFs Connect选项不适用于APFS JumpStart

2020-09-11编译OpenCore-0.6.2-09-11编译版

- 例行更新

2020-09-09编译OpenCore-0.6.2-09-09编译版

- 更新了SMBIOS和其他设备的内置固件版本
- 更新版本号为0.6.2

2020-09-08编译OpenCore-0.6.1-09-08正式版

- 0.6.1正式版

2020-09-07编译OpenCore-0.6.1-09-07编译版

- 添加了DisableLinkeditJetIson quirk，以解决11.0b5内核崩溃的问题
- 添加了对配置中缺少字段的调试

2020-09-05编译OpenCore-0.6.1-09-05编译版

- 例行更新
- 优化部分代码

2020-09-03编译OpenCore-0.6.1-09-03编译版

- 例行更新
- 优化部分代码

2020-09-01编译OpenCore-0.6.1-09-01编译版

- 增加了预览UEFI安全引导兼容性
- 添加了FuzzyMatch选项来支持10.6和更早版本的FuzzyMatch匹配
- 增加了KernelArch选项来指定旧内核上的架构设置
- 增加了KernelCache选项来指定较老的内核的内核缓存设置
- 添加了Force部分，以支持在旧版macOS中注入驱动程序
- 将内核驱动程序注入更改为在内核驱动程序补丁之前加载
- 为Add, Block, Force, and Patch sections添加Arch筛选选项

2020-08-30编译OpenCore-0.6.1-08-30编译版

- 修复了OpenDuetPkg中由EHCI SMI引起的硬锁

2020-08-28编译OpenCore-0.6.1-08-28编译版

- 例行更新
- 优化部分代码

2020-08-26编译OpenCore-0.6.1-08-26编译版

- 例行更新
- 优化部分代码

2020-08-24编译OpenCore-0.6.1-08-24编译版

- 修正了macOS 11.0 DMG recovery加载时不支持热插拔
- 修复了10.12.6和其他版本的`XhciPortLimit`问题
- 修复了10.11.5和可能的其他版本上的`increasepcibarasize`问题
- 修复了10.8.5和其他版本上的`LapicKernelPanic`问题

2020-08-22编译OpenCore-0.6.1-08-22编译版

- 更新了SMBIOS和其他设备的内置固件版本
- 修复了在内存不足时修补ACPI表的问题

2020-08-20编译OpenCore-0.6.1-08-20编译版

- 修复了与非内核文件匹配的XNU关联

2020-08-18编译OpenCore-0.6.1-08-18编译版

- 修复了SyncRuntimePermissions创建无效MAT表的问题
- 添加EFI FAT图像加载支持（macOS 10.8及更早版本）
- 添加了 64-bit 无缓存kext注入支持（macos10.9及更早版本）
- 添加了 64-bit mkext kext注入支持（macos10.6及更早版本）

2020-08-16编译OpenCore-0.6.1-08-16编译版

- 例行更新
- 优化部分代码

2020-08-14编译OpenCore-0.6.1-08-14编译版

- 为老式笔记本电脑增加了文本渲染器的builtinext变量（搞不懂为什么还对老式机器还提供支持？？）

2020-08-12编译OpenCore-0.6.1-08-12编译版

- 修正RSDP ACPI表校验和重新计算
- 增加了对10.13+immutablekernel加载的支持
- 修正了在11.0 kext注入中解决一些符号为零的问题
- 通过限制引导管理访问以减少OpenCanopy的大小

2020-08-10编译OpenCore-0.6.1-08-10编译版

- 增加了iMac20,1机型
- 修复了老旧Xeon cpu显示名称，如Xeon E5450
- 添加了kext注入支持，无需内核缓存
- 添加Comet Lake-LP HDA设备代码
- 修正了SATA控制器上的操作系统引导选择问题

2020-08-08编译OpenCore-0.6.1-08-08编译版

- 例行更新
- 优化部分代码

2020-08-06编译OpenCore-0.6.1-08-06编译版

- 提高启动初期对热键的识别灵敏性。
- 通过`DmgLoading`的设置，支持DMG的直接加载。

2020-08-04编译OpenCore-0.6.1-08-04编译版

更新版本号为0.6.1

2020-08-04编译OpenCore-0.6.0-08-04编译版

- 修复了一些多核心i9CPU显示名称的问题，如7920X
- 修复了SSDT-EC-USBX

2020-08-02编译OpenCore-0.6.0-08-02编译版

- 修复了某些SATA控制器在IDE模式下导致OpenDuetPkg启动延迟的问题

2020-07-31编译OpenCore-0.6.0-07-31编译版

- 修正了内存超过4G机器32位OpenDuetPkg启动问题

2020-07-29编译OpenCore-0.6.0-07-29编译版

- `PlatformInfo` `Automatic`的勾选适用于所有机型

2020-07-27编译OpenCore-0.6.0-07-27编译版

- 修正了在10代cpu仿冒CPUID时的OSXSAVE报告
- 新增`SerialInit`选项以单独执行串行初始化
- 修复了在RAID模式下使用SATA控制器在Intel G33上启动OpenDuetPkg的问题

2020-07-25编译OpenCore-0.6.0-07-25编译版

- 例行更新
- 优化部分代码

2020-07-23编译OpenCore-0.6.0-07-23编译版

- 例行更新
- 优化部分代码

2020-07-21编译OpenCore-0.6.0-07-21编译版

- 例行更新
- 优化部分代码

2020-07-19编译OpenCore-0.6.0-07-19编译版

- 例行更新
- 优化部分代码

2020-07-17编译OpenCore-0.6.0-07-17编译版

- 更新了SMBIOS和其他设备的内置固件

2020-07-15编译OpenCore-0.6.0-07-15编译版

- 增加了MacBookPro16,4模版

2020-07-13编译OpenCore-0.6.0-07-13编译版

- 例行更新
- 优化部分代码

2020-07-11编译OpenCore-0.6.0-07-11编译版

- 修正了DxeIpl中ACPI复位寄存器检测的问题

2020-07-09编译OpenCore-0.6.0-07-09编译版

- 例行更新
- 优化部分代码

2020-07-07编译OpenCore-0.6.0-07-07编译版

- 在KernelCollection中注入了最新预览版本（macOS Big Sur ）代码，进测试非10代的机器，大多数可以正常升级安装并顺利的进入到macOS Big Sur ，全新安装在测试中。

2020-07-05编译OpenCore-0.6.0-07-05编译版

- 例行更新
- 优化部分代码

2020-07-03编译OpenCore-0.6.0-07-03编译版

- 例行更新

2020-07-01编译OpenCore-0.6.0-07-01编译版

- 修正了OpenCanopy中调节音量图标延迟的问题

2020-06-29编译OpenCore-0.6.0-06-29编译版

- 在ProvideConsoleGop选项中增加了UGA协议的兼容性
- 新增UgaPassThrough选项以支持GOP上的UGA协议
- 新增AppleFramebufferInfo协议以实现和覆盖
- 修复了串行初始化时文件日志被禁用的问题
- 修复了Meron and similar CPUs上的FSB频率报告的问题

2020-06-27编译OpenCore-0.6.0-06-27编译版

- 修正DP1版本在11.0 lapic内核的缺陷
- 改进的启动macOS选择没有NVRAM的问题

2020-06-25编译OpenCore-0.6.0-06-25编译版

- 增加了勾选`AvoidRuntimeDefrag`对11的支持

2020-06-23编译OpenCore-0.6.0-06-23编译版

- 修正了在调试版本中由未对齐的文件路径访问引起的断言
- 为保持一致性，将`ConfigValidity`实用程序改名为`ocvalidate`
- 新增APFS加载`UEFI-Apfs-GlobalConnect`，以解决旧固件问题

2020-06-21编译OpenCore-0.6.0-06-21编译版

- 新增`Booter-Quirks-ProvideMaxSlide`项，提高笔记本电脑的稳定性
- 修复部分预览不可用的问题。

2020-06-19编译OpenCore-0.6.0-06-19编译版

- 在重启选项中的 `ResetSystem`添加固件模式
- 用run-efi-updater NVRAM参数替换`BlacklistAppleUpdate`项
- 修复FadtEnableReset复位时导致的ACPI 崩溃
- 修复在启动选项扩展期间固定PXE启动项
- 更新基础EDK II包至edk2-stable202005

2020-06-17编译OpenCore-0.6.0-06-17编译版

- 例行更新

2020-06-15编译OpenCore-0.6.0-06-15编译版

- 例行更新
- 优化部分代码

2020-06-13编译OpenCore-0.6.0-06-13编译版

- 例行更新
- 优化部分代码

2020-06-11编译OpenCore-0.6.0-06-11编译版

- 例行更新
- 优化部分代码

2020-06-09编译OpenCore-0.6.0-06-09编译版

- 增加Comet Lake HDA 驱动代码
- 修复非英特尔平台音频路径

2020-06-07编译OpenCore-0.6.0-06-07编译版

- 修复APFS在加载融合驱动器（Fusion Drive）的错误

2020-06-05编译OpenCore-0.6.0-06-05编译版

- 例行更新
- 优化部分代码

2020-06-03编译OpenCore-0.6.0-06-03编译版

- 更新版本号至0.6.0
- 修复AudioDxe的声音问题
- 修复OpenCanopy中苹果FW更新的图标选择问题

2020-06-02编译OpenCore-0.5.9-06-02官方编译正式版

- 新增用于预构建版本的`CrScreenshotDxe`驱动程序
- 修复了Hyper-V频率检测兼容性
- 新增增加了用于调试版本转储系统信息的选项`SysReport`
- 修复一些AMD固件在执行键盘输入时崩溃的问题

2020-05-31编译OpenCore-0.5.9-05-31

- 增加了新型CPU的检测与识别
- 新增ConfigValidity实用程序用于改进了Config验证
- 新增登录时串行端口的初始化与调试
- 禁用无意义的调试日志文件创建，以避免ESP混乱
- 新增`TscSyncTimeout`来解决调试内核导致的崩溃
- 新增 first-class Windows 用于支持 bless model（上帝模式？？）
- 修正 `LapicKernelPanic` 在10.9下内核崩溃问题

2020-05-29编译OpenCore-0.5.9-05-29

- AudioDxe:完善开机声音
- 更新了部分固件（机型）版本

2020-05-27编译OpenCore-0.5.9-05-27

- 例行更新
- 优化部分代码

2020-05-25编译OpenCore-0.5.9-05-25

- 例行更新
- 优化部分代码

2020-05-23编译OpenCore-0.5.9-05-23

- 优化部分代码

2020-05-21编译OpenCore-0.5.9-05-21

- 新增扫描策略对PCI设备的支持(如VIRTIO)

2020-05-19编译OpenCore-0.5.9-05-19

- 新增MacBookPro16,2和MacBookPro16,3模版

2020-05-17编译OpenCore-0.5.9-05-17

- 将`ACPI`,`DeviceProperties`, 和 `NVRAM`模块中的 `（阻止）Block` 改名为 `（删除）Delete` 

2020-05-15编译OpenCore-0.5.9-05-15

- 修复 `FadtEnableReset` FACP表单过小
- 修复QEMU 5.0 和 KVM accelerator导致CPU崩溃
- 移除 `Config-UEFI-Quirks-RequestBootVarFallback`
- 新增 `Config-UEFI-Quirks-DeduplicateBootOrder` 
- 移除`Config-UEFI-Output-DirectGopCacheMode`
- 修复日志耗尽导致引导失败
- 修复文本模式时控制台失效
- 修复blit-only GOP的兼容性
- 修复 在DeviceProperty 和 NVRAM `Block`中“#”失效

2020-05-11编译OpenCore-0.5.9-05-11

- 当图形界面external故障或错误时，强制使用文字builtin界面
- 修复NVRAM变量为空时的警告(如rtc-blacklist)
- 新增 `ApplePanic` 在ESP根目录下储存崩溃日志
- 修复`ReconnectOnResChange` 发生资源变化时，重新连接
- 修复OpenCanopy使用图形界面时的错误
- 修复OpenCanopy文字显示错误
- 添加OpenCanopy部分快捷键的支持(例如Ctrl+Enter)
- 增加builtin文本模式的兼容性

2020-05-07编译OpenCore-0.5.9-05-07

- 在`OpenCanopy`中添加了对HiDPI的完整支持
- 通过使用`CoreText`改进字体渲染
- 修复灯光与自定义背景时字体的渲染
- 在启动菜单列表中添加了`Boot####`选项
- 移除 `HideSelf` 对 `BOOTx64.efi`的识别
- 新增 `BlacklistAppleUpdate` 限制 Apple FW 更新
- 修复accidental工具和NVRAM的默认重启设置
- 修复无法识别`com.apple.recovery.boot` 引导菜单
- 改善了 NVRAM 重置后无法删除 `BootProtect`启动项的问题
- 禁用picker UI时提高引导性能

2020-05-05编译OpenCore-0.5.9-05-05

- 更新版本号

2020-05-04编译OpenCore-0.5.8-05-04

- 修正了创建vault时校验和检查无效的问题。

2020-05-03编译OpenCore-0.5.8-05-03

- 优化了部分代码
- 更新部分固件

2020-05-01编译OpenCore-0.5.8-05-01

- 优化了部分代码

2020-04-29编译OpenCore-0.5.8-04-29

- 在OpenCanopy中增加了部分HiDPI的支持
- 优化了部分代码

2020-04-27编译OpenCore-0.5.8-04-27

- 修复处理24-bit分辨率的问题
- 新增用于DuetPkg的`Ps2KeyboardDxe`驱动
- 更新了`BootInstall` 的DuetPkg版本(开源)

2020-04-25编译OpenCore-0.5.8-04-25

- 新增Misc- Security-BootProtect项
- 安装10.8时，注入固有的kext
- 新增使用图形界面时，对OpenCanopy超时的支持

2020-04-23编译OpenCore-0.5.8-04-23

- 固件版本更新
- 优化部分代码

2020-04-21编译OpenCore-0.5.8-04-21

- 将`Config-UEFI-协议（Protocols）`重命名为`Config-UEFI-ProtocolOverrides(协议覆盖)`，以便于识别
- 新增`Config-Misc-Tools-ResetSystem`工具，可以在菜单中显示关机/重启

2020-04-19编译OpenCore-0.5.8-04-19

- 增加了支持保留内存区域
- 增加RtcRw工具来调整RTC内存
- 添加热补丁applertcchecksum防止内核崩溃
- 添加AppleRtcRam协议

2020-04-17编译OpenCore-0.5.8-04-17

- 修复了AppleEvent和OpenCanopy对OVMF TPL的兼容性限制
- 添加了支持OVMF的鼠标驱动到驱动包。

2020-04-15编译OpenCore-0.5.8-04-15

- 在OpenCanopy中添加了AppleEvent鼠标支持
- 优化部分代码

2020-04-13编译OpenCore-0.5.8-04-13

- 固件版本更新，新增MBA91
- 优化部分代码
- 新增`Config-UEFI-APFS`项，用于APFS驱动和增强安全性（即不用Config-UEFI-Drivers里面的ApfsDriverLoader）

2020-04-10编译OpenCore-0.5.8-04-10

- 修复不正确的实用程序和资源安装包
- 修正`Custom` `UpdateSMBIOSMode` 修改SMBIOSv3列表的问题
- 通过`UpdateSMBIOSMode`使用更新的文档来覆盖分离SMBIOS
- 修复`OpenCanopy`中macOS 10.15.4 安装图标的问题

2020-04-06编译OpenCore-0.5.7官方正式版

- 将`Config-Misc-Boot-PickerAttributes`改名为`Config-Misc-Boot-ConsoleAttributes`
- 为UI配置添加`Config-Misc-Boot-PickerAttributes`

2020-04-05编译OpenCore-0.5.7-04-05

- 添加 `config-Booter-Quirks-ProtectMemoryRegions`以修复内存加载时的一些问题。
- 移除`config-Booter-Quirks-ProtectCsmRegion`用`config-Booter-Quirks-ProtectMemoryRegions`代替

2020-04-03编译OpenCore-0.5.7-04-03

- 修复了`OpenRuntime`中4K对齐，以完善在SKL上启动Linux
- 添加`config-Booter-Quirks-SyncRuntimePermissions`项，修复在CFL+上启动Linux
- 添加`config-Booter-Quirks-RebuildAppleMemoryMap`项，修复戴尔5490上启动macOS的问题
- 删除`config-Booter-Quirks-ShrinkMemoryMap`项，添加更高级的`config-Booter-Quirks-RebuildAppleMemoryMap`项
- 使用新系统时不用勾选`EnableWriteUnprotector`项，进过实践最好还是勾选
- 添加`Config-Misc-Debug-AppleDebug`，勾选后 boot.efi调试日志保存到OpenCore日志中，一般不勾选此参数仅适用于10.15.4及以上的版本

2020-03-30编译OpenCore-0.5.7-03-30

- 修复了10.15.4电源超时导致的内核崩溃
- 修复了OpenRuntime中4K对齐

2020-03-29编译OpenCore-0.5.7-03-29

- 优化部分代码

2020-03-24编译OpenCore-0.5.7-03-24

- 优化部分代码

2020-03-22编译OpenCore-0.5.7-03-22

- 继续更新内置固件（主要是机型）
- 优化部分代码

2020-03-20编译OpenCore-0.5.7-03-20

- 更新内置固件（主要是机型）

2020-03-18编译OpenCore-0.5.7-03-18

- 重写' readlabel '使应用程序支持' disklabel '的编码。
- 将“FwRuntimeServices”改名为“OpenRuntime”。
- 将“AppleUsbKbDxe”改名为“OpenUsbKbDxe”。

2020-03-14编译OpenCore-0.5.7-03-14，

- 用“Windows”替换“BOOTCAMP Windows”。
- 在Tools中添加OpenCoreShell提供的`OpenShell.efi` 

2020-03-12编译OpenCore-0.5.7-03-12，<font color= "#FF0000" >添加ProtectUefiServices项，用于修复Z390在DevirtualiseMmio上的问题（03-12新增）</font>

2020-03-11编译OpenCore-0.5.7-03-11，优化部分代码

2020-03-08编译OpenCore-0.5.7-03-09,添加了、修复了7个项目

2020-03-08编译OpenCore-0.5.7-03-08,优化部分代码

2020-03-03编译OpenCore-0.5.7-03-03(更新版本号)

2020-03-02官方编译OpenCore-0.5.6-03-02

2020-02-24编译OpenCore-0.5.6添加开机提示音、为10.13以上的版本在boot.efi 中增加音频支持

2020-02-23编译OpenCore-0.5.6优化2个项目

2020-02-19编译OpenCore-0.5.6更新说明文件

2020-02-16-编译OpenCore-0.5.6重大调整版

2020-02-03-编译OpenCore-0.5.6

2020-01-15-编译OpenCore-0.5.5

2019-12-24-编译OpenCore-0.5.4

2019-12-19-编译OpenCore-0.5.3

重要声明：独行秀才拥有此篇文字与图片所有版权，严禁用于任何商业用途，特别是不能在远景论坛转载，否则将追究法律责任！还可能被远景封号，谢谢合作