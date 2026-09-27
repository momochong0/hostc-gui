# hostc 可视化面板

基于 [akazwz/hostc](https://github.com/akazwz/hostc) 的图形化内网穿透客户端，使用 aardio 开发。一键把本地服务通过公网 HTTPS 地址分享给任何人。

![icon](res/icon.ico)

## 功能

- 配置本地端口、本地主机、服务器地址、数据通道数
- 一键启动 / 停止隧道，实时显示公网地址与连接状态
- 公网地址一键复制、二维码扫码访问
- 运行日志实时输出
- 环境诊断（Node、hostc、服务器、本地端口）
- 一键更新底层 hostc（npm 版本检测与升级）
- 未安装 Node.js 时自动检测并引导安装

## 快速使用

### 直接使用 EXE

前往 [**Releases 页面**](https://github.com/momochong0/hostc-gui/releases/latest) 下载 `hostc-panel-<版本>.exe`（或使用仓库内 `publish/hostc面板.exe`），双击运行。

- 已安装 Node.js：首次启动隧道时会自动通过 npm 安装 hostc；
- 未安装 Node.js：软件会弹窗并引导至 [Node.js 下载页](https://nodejs.org/zh-cn/download)。

### 分享本地项目

1. 先把项目在本地跑起来（如 `npm run dev`、`node app.js`）；
2. 在面板填入对应端口，点击「启动隧道」；
3. 把生成的公网地址（如 `https://t-xxxx.hostc.dev/`）发给别人，或用二维码扫码访问。

## 数据通道数

通道数指客户端与边缘服务器之间并行的 WebSocket 数据连接数（默认 2，范围 1–8），用于多路复用、提升并发吞吐，并非可访问人数限制。日常保持默认即可。

## 从源码构建

1. 安装 [aardio](https://www.aardio.com/)；
2. 用 aardio 打开 `hostc-gui.aproj`；
3. 按 F7 发布，生成 `publish/hostc面板.exe`。

## 目录结构

```
hostc-gui/
├─ main.aardio        # 主程序
├─ hostc-gui.aproj    # aardio 工程文件
├─ res/
│  ├─ icon.ico        # 应用图标（多尺寸）
│  └─ favicon.svg     # 原始图标
└─ publish/
   └─ hostc面板.exe    # 已发布的可执行文件
```

## 致谢

- [akazwz/hostc](https://github.com/akazwz/hostc) —— 基于 Cloudflare Workers 的内网穿透服务

## License

MIT
