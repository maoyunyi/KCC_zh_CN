# KCC_zh_CN — 带简体中文界面的 Kindle Comic Converter

> Single-file, Chinese-localized build of Kindle Comic Converter, compiled from the official `master` branch.

基于官方 KCC **master** 分支编译的单文件中文版（非官方构建）。

官方最新发布版 `v12.0.0` 虽然把中文翻译文件 `zh_CN.qm` 打进了包，但**没有加载翻译的代码、也没有语言切换按钮**，界面永远是英文。而 master 分支早已内置简体中文翻译（`kcc_zh_CN.ts/.qm`）和「文 A」语言按钮——只是尚未发布。本构建只是把官方已有的这些中文资源完整编译进 exe，未改动任何翻译内容。

## 功能
- 单文件 `exe`，免安装，双击即用
- 完整简体中文界面（共 280 条界面文案）
- 转换能力与原版完全一致：设备配置、CBZ / EPUB / MOBI / KFX 输出、mozjpeg 压缩、KOReader 适配等

## 下载
二进制文件（92 MB）通过 **GitHub Releases** 分发，不放入仓库代码（GitHub 网页单文件上传限制为 25 MB）。前往本仓库的 **Releases** 页面下载 `KCC_zh_CN.exe`。

## 使用方法
1. 在仓库 **Releases** 页面下载 `KCC_zh_CN.exe`
2. 双击运行
3. 点击窗口右上角的 **「文 A」** 按钮 → 选择 **「中文（简体）」**，界面立即中文化
4. 语言选择记在 `QSettings`，**下次启动自动中文**

## 从源码编译

仓库已附带官方 master 的 `KCC_zh_CN.spec`（已配好单文件 / 窗口 / 无 UPX / 带图标 / 含 cffi），直接用它即可：

```bash
pip install -r requirements.txt pyinstaller
pyinstaller KCC_zh_CN.spec
```

生成 `dist/KCC_zh_CN.exe`（约 90 MB）。若想手动指定参数，等价命令为：
```bash
pyinstaller -F -w --noupx -i icons/comic2ebook.ico -n KCC_zh_CN --hidden-import=_cffi_backend kcc.py
```
（`--hidden-import=_cffi_backend` 为 mozjpeg 依赖所必需。）

## 说明
- 本仓库**非官方**，仅整合官方已有中文资源，不修改任何翻译字符串
- 源代码来自 [ciromattia/kcc](https://github.com/ciromattia/kcc)（master 分支），版权归原作者所有
- 若官方未来发布含中文的正式版，请以官方为准
- 转换画质与速度与原版相同

## 许可
遵循与原项目相同的许可协议（见上游 `LICENSE`）。
