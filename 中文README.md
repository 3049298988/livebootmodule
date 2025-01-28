## LiveBoot Magisk & KernelSU & APatch 模块

[English README](README.md)

## 描述

- 一个适用于 Android 设备的 Magisk、KernelSU 和 APatch 模块，可启用类 Unix 风格（详细）的启动动画
- 来自 [Chainfire](https://github.com/Chainfire) 的 [LiveBoot](https://github.com/Chainfire/liveboot) 应用的 Magisk、KernelSU 和 APatch 模块，无需任何应用程序或 UI

预览: [![YouTube视频](https://img.youtube.com/vi/N0tqzVWxpJk/0.jpg)](https://www.youtube.com/watch?v=N0tqzVWxpJk)

## 支持的设备和 ROM

它已在许多基于 Android 14、13 和 12 的 ROM 上成功测试过。应该适用于所有通过 Magisk、KernelSU 和 APatch root的设备。

## 下载

[Releases](https://github.com/3049298988/livebootmodule/releases/)

## 更新日志

[CHANGELOG.md](CHANGELOG.md)

## LiveBoot 自定义指南

### 通过应用程序界面设置

1. 如果尚未安装，请安装 [DerGoogler](https://github.com/DerGoogler) 的 [MMRL](https://github.com/DerGoogler/MMRL/releases)。
2. 打开应用程序，导航到“已安装”部分，搜索 **LiveBoot** 模块，然后单击“配置”。（需要使用[旧版MMRL](https://github.com/MMRLApp/MMRL/releases/download/v3.24.32/app-default-arm64-v8a-release-3.24.32-32432.apk)）

### 手动设置

> [!note]
> `0000liveboot` 存储在三个目录中，分别是 `/data/adb/service.d`, `/data/adb/post-fs-data.d` 和 `/data/adb/livebootmagisk`。建议每个目录中的文件内容都相同。

1. 使用文本编辑器打开上面列出的三个目录中的 `0000bootlive` 文件。
2. 根据您的要求修改设置 (如下所列)。**⚠️警告：请勿编辑文件中的任何其他内容！⚠️**
3. 保存文件并重新启动设备以应用更改。

#### 手动自定义选项

- 背景颜色: ` ` (无字符，它是 LiveBoot 默认的灰色背景色), `dark`, `transparent`
- Logcat 日志级别: `V` (Verbose 详细), `D` (Debug 调试), `I` (Info 信息), `W` (Warning 警告), `E` (Error 错误), `F` (Fatal 严重错误), `S` (Silent 静默)
- Logcat 缓冲区: `M` (Main 主缓冲区), `S` (System 系统缓冲区), `R` (Radio 无线缓冲区), `E` (Events 事件缓冲区), `C` (Crash 崩溃缓冲区)
- Logcat 格式: `brief` (简要格式), `process` (进程格式), `tag` (标签格式), `thread` (线程格式), `time` (时间格式), `threadtime` (线程时间格式)
- Logcat 颜色: `colors` (彩色), `logcatnocolors` (无色)
- DMESG: `0--1` (关闭), `0-99` (开启)
- 行数: 任何您想要的数值（`1-99999`）
- 自动换行: `wordwrap`, ` ` (无字符)
- 保存日志: `save` (将日志保存在 `/data/cache` 中，就像在应用程序中一样), ` ` (无字符)
- 备用宽度和备用高度: 通常是您的设备屏幕分辨率，但您可以设置其他值来模拟其他屏幕尺寸

#### 示例配置

```

transparent logcatlevels=VDIWEFS logcatbuffers=MSREC logcatformat=threadtime colors dmesg=0-99 lines=80 wordwrap save fallbackwidth=1080 fallbackheight=2340
```

## 许可证

- 0000bootlive (原始文件为 0000liveboot)、liveboot(.apk)、libdaemonize.so 文件根据 [Jorrit "Chainfire" Jongma](https://github.com/Chainfire) 的 [GPLv3](https://github.com/Chainfire/liveboot/blob/master/LICENSE) 许可证进行许可。
- 有关详细许可证，请参见: [COPYING](https://github.com/Chainfire/liveboot/blob/master/COPYING), [LICENSE](https://github.com/Chainfire/liveboot/blob/master/LICENSE)
- 本项目的其他部分也遵循 [GPLv3](https://github.com/symbuzzer/livebootmagisk/blob/main/LICENSE)
