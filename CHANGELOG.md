# Changelog

## 0.4.2

- 将横条底部偏移由硬编码 `14dp` 改为读取 ColorOS 原生 bottom dimen 资源。
- 保留横条的 iOS 风格宽度、高度和圆角设置。
- 重新签名 `runtime/iosbar-navhook.apk`。
- 安装时先卸载旧的 `com.iosbar.navhook` 用户包，避免签名不兼容。
- 清理旧版本可能遗留的 overlay、脚本和包记录。

## 上游版本

本仓库是上游开源项目的 fork。上游版本和历史变更请查看 GitHub 仓库的 fork network。
