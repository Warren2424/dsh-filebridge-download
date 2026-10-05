# DSH 文件助手 · 安装包

给手机上的 **DeepSeek Harness** 用的本机文件桥（24KB，纯 Java，无依赖、无广告、不联网）。

- **下载**：[DshFileBridge.apk](https://github.com/Warren2424/dsh-filebridge-download/raw/main/DshFileBridge.apk)
- **CDN 加速**：<https://cdn.jsdelivr.net/gh/Warren2424/dsh-filebridge-download@main/DshFileBridge.apk>

## 它是干什么的

DSH 的界面跑在安卓 WebView 里，网页没有权限做这三件事，所以需要这个小 App 帮它：

| 能力 | 说明 |
|---|---|
| 保存到系统相册 | 走 Android `MediaStore`，系统相册里能直接看到 |
| 系统分享 | `ACTION_SEND`，发给微信 / QQ / 别的 App |
| 用其他应用打开、跳到文件夹 | `ACTION_VIEW` / `DocumentsUI` |

它只监听 `127.0.0.1:3188`（回环地址，外网连不上），**只处理 DSH 现传的字节，不读取你的任何文件**。

## 装完要做的

1. 打开 App，点「启动 / 重启服务」（会常驻一个低优先级通知）；
2. 点「① 授予『显示在其他应用上层』」——Android 10+ 从后台调起分享面板必须靠它；
3. MIUI 上再点「② 打开本应用详情」，允许 **后台弹出界面 / 自启动**。

## 卸载

不影响 DSH：插件检测不到它时会自动退回「只保存到相册/下载」的模式。

> 源码仓库是私有的；这个仓库只放编译好的安装包。
