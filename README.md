# iOS-style Immersive Gesture Bar

这是一个基于上游开源项目 fork 的 Magisk/LSPosed 模块，为 ColorOS SystemUI 提供 iOS 风格的沉浸式手势横条。

本仓库是个人维护的修改版。请通过 GitHub 的 **fork network** 查看上游仓库、原作者和原始许可证；上游许可证和版权声明应继续保留。

## 本版本的修改

- 版本：`0.4.2`
- 将横条底部偏移从固定的 `14dp` 改为运行时读取 ColorOS 原生尺寸资源。
- 横条位置跟随系统原生导航横条高度，避免在不同 ColorOS 版本或设备上抬得过高。
- 保留 iOS 风格外观：宽度约 `180dp`，高度约 `6.4dp`，圆角为高度的一半。
- 更新安装脚本：安装新签名的 hook APK 前先卸载旧的 `com.iosbar.navhook` 用户包。
- 未替换 framework 或系统导航模式 overlay；主要作用范围为 `com.android.systemui`。

## 文件结构

```text
.
├─ META-INF/                 # Magisk 刷机脚本
├─ runtime/
│  └─ iosbar-navhook.apk     # SystemUI hook APK（二进制发布文件）
├─ customize.sh              # 模块安装与兼容性处理
├─ uninstall.sh              # 卸载清理脚本
├─ module.prop               # Magisk 模块元数据
├─ README.md
├─ CHANGELOG.md
└─ .gitignore
```

## 安装

1. 将本仓库下载为 ZIP，或使用仓库页面的 **Download ZIP**。
2. 在 Magisk 中选择“从本地安装”并刷入 ZIP。
3. 在 LSPosed 中启用对应 hook 应用/模块。
4. 将作用域设置为 `com.android.systemui`。
5. 重启设备。

如果刷入后没有生效，请确认 LSPosed 已加载 `com.iosbar.navhook`，并检查设备 ROM 是否提供相应的 ColorOS 导航栏资源。

## 卸载

在 Magisk 中移除模块后重启。模块的 `uninstall.sh` 会清理 hook APK 以及旧版本遗留的相关包记录。

## 兼容性与风险

- 主要面向 ColorOS 16 及使用相同 SystemUI 导航栏资源的系统。
- 这是对 SystemUI 的运行时修改，可能与其他导航栏、手势条或 SystemUI 定制模块冲突。
- 刷入前请保留 Magisk 救援方式，并自行承担设备风险。

## 许可证与致谢

本项目是上游开源项目的 fork。请以仓库 fork 关系中的上游许可证和版权声明为准，不要移除原作者的声明。

本版本的分析、二进制修改和打包过程使用了 AI 辅助工具完成；项目维护者为本仓库所有者。AI 工具不因此成为项目作者或版权所有者。
