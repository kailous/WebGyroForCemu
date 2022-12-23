# WebGyroForCemu

获取手机陀螺仪数据，传递给 Cemu ，实现体感控制。
手机端仅需使用 web 浏览器，无需安装任何app。

## 用法

使用手机浏览器（safair或chrome）打开https://your-pc-ip-ip.xip.lhjmmc.cn:8443（例如https://192-168-1-100.xip.lhjmmc.cn:8443 )

## 注意

### 1. iOS 12.2 中的注意事项

如果您使用的是 ios 12.2+，请启用“设置 > Safari > 运动和方向访问”并使用 HTTPS 访问。

### 2. iOS 13+注意事项

如果您使用的是ios 13+，请使用HTTPS访问，确保url为https://[you-pc-ip-ip].xip.lhjmmc.cn:8443并且证书受信任（主机名必须是* .xip.lhjmmc.cn），点击允许按钮授予页面权限。 如果未授予权限，请重新启动浏览器并重试。

### 3. iOS 13.4 中的注意事项

请升级到 IOS 13.5+。 看 [#14](https://github.com/hjmmc/WebGyroForCemuhook/issues/14)

## 测试 PadTest

从 [此页面](https://cemuhook.sshnuke.net/padudpserver.html) 下载 [PadTest_1011.zip](https://files.sshnuke.net/PadTest_1011.zip)

## 引用

> [iOSGyroForCemuhook](https://github.com/denismr/iOSGyroForCemuhook)

> [pkg](https://github.com/zeit/pkg)

> [xip.lhjmmc.cn](https://xip.lhjmmc.cn) https cert to slove latency problem. ~~Since safari's websocket does not support self-signed certificates, when using HTTPS access, socket.io will probably use XHR instead of websocket, which will increase communication latency.~~

## 设置说明
将此存储库克隆到计算机中的任何位置（由于 UAC 原因，避免使用程序文件）。

cd address 导航到包含使用命令提示符 ( app.js ) 的文件夹。  

使用以下命令下载所需的节点包（忽略警告）：
```sh
npm install
```
最后，使用以下命令运行服务器：
```sh
npm start
```
app.js 文件实现了三个服务器：

与 cemuhook 通信的 UDP 服务器（此服务器侦听端口26760)
与电话通信的 WebSocket 服务器（此服务器侦听端口1337)
为电话访问的网页提供服务的 HTTP 服务（此服务器侦听端口8080)
您可以通过将 app.js 文件中的值 （CTRL+F） 替换为所需的值来更改所需的任何端口。如果更改 WebSocket 服务器端口，还必须在文件中替换它。static.html

