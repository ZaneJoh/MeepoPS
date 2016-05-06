# FastWS-PHP

## FastWS是Fast WebSocke的缩写，旨在提供稳定的WebService。本项目为PHP的语言实现。可以轻松构建在线实时聊天、即时游戏、视频流媒体播放等。

### 目前版本为V0.0.2. 稳定可用. (Master分支和Tagv0.0.2). 仅支持Telnet协议.

FastWS计划支持Telnet, HTTP, HTTPS, WebSocket等应用层协议.

dev分支为开发分支, 不推荐下载.

基于Telnet协议的服务端使用方法请参考demo-text-chat.php

客户端使用telnet客户端即可

如果服务端启动的是HOST是0.0.0.0, 那么客户端可以是外机,可以是本机.本机可以<br>
如果服务端启动的是HOST是127.0.0.1/localhost, 那么客户端是不能外机,只能是本机

稳定性和高效性测试一:<br>
使用Select轮训机制, 服务端和客户端同一台服务器, 服务器配置为家用HP Gen8.<br>
一个实例，单进程。对Text协议进行测试。使用PHP模拟Telnet。<br>
测试时间共76314秒。<br>
客户端两个进程,用脚本模拟，一共2个客户端。每个客户端发送100次"hello world\n"。发送完毕后断开连接。<br>
客户端重新链接，然后继续发送100次hello world。再次断开。一直循环。<br>
测试时间共76314秒。每个进程分别链接了6555971次和7218005次。QPS为18049<br>