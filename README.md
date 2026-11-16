# Alacritty for Debian 11 Bullseye ARM64

面向 Debian 11 Bullseye aarch64 / glibc 2.31 的 Alacritty 预编译包。

## 下载和安装

前往 [GitHub Releases](https://github.com/gntzh/alacritty-bullseye-arm64/releases) 下载 `.tar.gz`、`SHA256SUMS` 和检查报告；安装命令及运行依赖见发布说明。

当前发布为 `0.18.0-dev` 开发快照，固定上游提交 `aa5d942f46c40184a3f214830ff5f7989f4733a1`。它不是上游官方发行包。

## 构建

使用原生 `ubuntu-24.04-arm` runner，在 Debian Bullseye 容器内执行 `cargo build --locked --release -p alacritty`，默认启用 X11 和 Wayland。Actions 页面可手动触发并指定上游 commit/tag。

构建检查 AArch64 架构、GLIBC 符号上限 2.31、动态依赖解析及版本命令。当前发布最高 GLIBC 导入版本为 2.30。尚未验证实际 GPU 和图形窗口启动。

产物包含可执行文件、terminfo 和上游 Apache 许可证，使用目标系统的共享库。最低图形要求为 OpenGL ES 2.0。

上游源码：[alacritty/alacritty](https://github.com/alacritty/alacritty)。
