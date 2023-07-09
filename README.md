# restls-examples
restls 配置实例

服务端
--------
1.安装PM2（类似systemd 24h守护程序）

2.https://github.com/3andne/restls/releases
```
wget https://github.com/3andne/restls/releases/download/v0.1.0-pre5/restls-x86_64-unknown-linux-musl

mv restls-x86_64-unknown-linux-musl restls

chmod +x restls

pm2 start /绝对路径/restls -n res -- -s "lovelive-as-global.com" -l "127.0.0.1:10000" -p 密码 -f "127.0.0.1:20000" --script "200?100,400?100,1200?200<1,1100~300,1000~100<1,2500~500,1300~50,1300~50,100~1200"

//127.0.0.1:20000（在singbox开的shadowsocks地址） lovelive-as-global.com（握手地址）

pm2 startup
pm2 save
```
客户端
--------
然后用1.clash-meta  2.[restls-client-go](https://github.com/3andne/restls-client-go)
