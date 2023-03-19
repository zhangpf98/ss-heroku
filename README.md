# 一键Shadowsocks+V2Ray-plugin快速部署到Heroku

**推荐使用最新的：<https://github.com/ygcaicn/Xray-heroku>**

点击下面按钮部署,好用的话记得点个Star：

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)
- - -

原生V2Ray部署： <https://github.com/ygcaicn/v2ray-heroku>

- - -

## 0. 注意

部署需要注册heroku帐号，注册heroku帐号时需要梯子（否则验证码刷不出来），需要一个能正常接收验证码的邮箱（@qq.com，@163.com都不行），有条件gmail
最好，没条件这里推荐outlook <https://login.live.com/>。

## 1. 验证

服务端部署后，点 open app,能正常显示网页，地址补上path后(例如：<https://test.herokuapp.com/static>)访问显示404页面，表示部署成功。

## 2. 客户端配置

二维码地址： https://zhangpf98.herokuapp.com/qr_img/v2.png
(test改成自己的app名称，如果更改了QR_Path，同时也要将对应的qr_img改成修改后的)

使用客户端扫描二维码即可。

**或者**

配置文件地址：https://test.herokuapp.com/qr_img

打开后复制，在客户端导入即可。

**或者**

手动配置：

```sh
Server: zhangpf98.herokuapp.com （test换为你的app名称）
Port: 443
Password: ma19861218
Encry Method： RC4-MD5 （或者你填写的其它方式）
Plugin: v2ray
Plugin Transport mode: websocket-tls
Hostname: zhangpf98.herokuapp.com
Path： zhangpf98.ss-heroku
```

没有客户端的也可以从这里下载(Android)：

[shadowsocks](https://github.com/shadowsocks/shadowsocks-android/releases/download/v5.0.5/shadowsocks--universal-5.0.5.apk)

[v2ray-plugin](https://github.com/shadowsocks/v2ray-plugin-android/releases/download/v1.3.1/v2ray-arm64-v8a-1.3.1.apk)

windows:

<https://github.com/shadowsocks/shadowsocks-windows/wiki/Shadowsocks-Windows-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E>

## 3. 更新

更新 v2ray-plugin 版本，访问 <https://dashboard.heroku.com/apps> 选择部署好的app，如果VER变量为 latest。直接选择More --> Restart all dynos, 程序自动重启，可通过view Logs确认进度。（更新指定版本： Settings --> Reveal Config Varsapp -->VER，修改成需要的版本号，例如 1.2）

2020/03/01当前版本使用正常：

+ shadowsocks-libev: 3.3.4+ds-2(debian apt)

+ v2ray-plugin: v1.3.0

# 参考

https://github.com/xiangrui120/v2ray-heroku-undone

https://hub.docker.com/r/shadowsocks/shadowsocks-libev

https://github.com/shadowsocks/v2ray-plugin
