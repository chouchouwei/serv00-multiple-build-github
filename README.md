# serv00变量规则
1. RES：`n`表示每次不重置部署，`y`表示每次重置部署
2. SSH_USER：表示用户名，如：`SosaYe`
3. SSH_PASS：表示serv00的登陆密码，如：`abc123`
4. REALITY：表示reality域名，如：`www.speedtest.net`、`www.wto.org`、`time.is`，`用户名.serv00.net`
5. SUUID：表示`uuid`，[在线生成](https://1024tools.com/uuid)
6. TCP1_PORT：表示vless的tcp端口，即第一次输入的端口，如：`8675`
7. TCP2_PORT：表示vmess的tcp端口，即第二次输入的端口，如：`8674`
8. UDP_PORT：表示hy2的udp端口，即第三次输入的端口，如：`8673`
9. HOST：表示登录服务器域名，如`s14.serv00.com`
10. ARGO_DOMAIN：argo固定域名，如`tm.chok.us.kg`；argo临时域名,如`""`
11. ARGO_AUTH：argo固定域名token，如：`eyJhIjoiOTM3YzFj...dVeCJ9`；argo临时域名token，如：`""`
12. 每行一个`serv00服务器`，末尾用`,`间隔，最后一个服务器不用`,`
# Cloudflare优选域名
1. 见`CF优选域名.csv`文件，后期不定期更新
2. 80系端口：`80`、`8080`、`8880`、`2052`、`2082`、`2086`、`2095`
3. 443系端口：`443`、`8443`、`2053`、`2083`、`2087`、`2096`
# Serv00的IP
1. 见`serv00的IP.csv`文件，后期不定期更新
# Serv00本地SSH部署脚本
```
bash <(curl -Ls https://raw.githubusercontent.com/yonggekkk/sing-box-yg/main/serv00.sh)
```
