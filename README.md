# Serv00一键三协议脚本

1. 支持一键三协议：vless-reality、vmess-ws(argo)、hysteria2
2. 生成`Proxyip`、`反代IP`，支持`Argo临时隧道`、`Argo固定隧道`、`CDN回源`

# 部署前须设置

1. 网页登陆[vps panel](https://panel14.serv00.com/)，如你的是S16服务器，请将网址中的 panel14 改`panel16`
2. 启用运行软件权限：`Additional services`→`Run your own applications`→`Status Enabled`
3. 设置3个端口：`Port reservation`→`Add port`，设置2个`tcp`、1个`udp`
4. 注意：端口以你设置的为准，这里的端口仅是示例：即`tcp1`=`vless-reality`=`8675`、`tcp2`=`vmess-ws`=`8674`、`udp`=`hysteria2`=`8673`

# Cloudflare的设置（须有个人域名）

1. 网页登陆[Cloudflarel](https://dash.cloudflare.com/login)，并解析了你的个人域名
2. CDN回源IP：点`个人域名`→`DNS`→`添加记录`，增加一个`A类型`=二级域名`cdn`，指向到你的Serv00分配给你的IP，如`188.68.240.161`，关闭小橙云`代理状态`，将获得完整的二级域名，如`cdn.chek.us.kg`
3. CDN回源端口：点`规则`→`概述`→`更改端口` `Origin Rules`→`创建规则`，字段=`主机名`、运算符=`等于`、值=`完整的二级域名`，如`cdn.chek.us.kg`；`目标端口`重写到`tcp2`，如`8674`。IP与端口都设置好后，将获得`CDN回源域名`=`cdn.chek.us.kg`
4. Argo固定隧道：在仪表首页，点`Zero Trust`→`Tunnels`→`添加隧道`→`选择 Cloudflare`，创建隧道，保存好`固定隧道密钥`，即是子域=二级域名`tm`、域=一级域名`chek.us.kg`，类型=`HTTP`，URL=`localhost:tcp2`，如`localhost:8674`或`127.0.0.1:8674`，设置完后将获得`argo固定隧道域名`=`tm.chek.us.kg`
5. 注意，上面是以`chek.us.kg`为例，请按自己的个人域名为准，其中的`cdn`、`tm`并不是固定值，你可以随意命名，符合网址标准即可

# 本地SSH脚本部署[视频教程](https://youtu.be/22dRx8uf91k)

```
bash <(curl -Ls https://raw.githubusercontent.com/yonggekkk/sing-box-yg/main/serv00.sh)
```
    
# Serv00多账号github线上部署+保活[视频教程](https://youtu.be/22dRx8uf91k)

1. 登陆[github](https://github.com/login)账号，创建`Private`私有仓库，点`Actions`→`set up a workflow yourself `，将`main.yml`文件里的代码拷贝过来，把你Serv00服务器的信息填上去，点`Commit changes`保存。
2. 点`Actions`→`Keep Servers Alive`→`Run workflow`手动运行一次
   
# github自动部署变量规则

1. RES：`n`表示每次不重置部署，`y`表示每次重置部署
2. SSH_USER：表示用户名，如：`SosaYe`
3. SSH_PASS：表示serv00的登陆密码，如：`abc123`
4. REALITY：表示reality域名，如：`www.speedtest.net`、`www.wto.org`、`time.is`，`用户名.serv00.net`
5. SUUID：表示`uuid`，[在线生成](https://1024tools.com/uuid)
6. TCP1_PORT：表示vless的`tcp1`端口，即第1次输入的端口，如：`8675`
7. TCP2_PORT：表示vmess的`tcp2`端口，即第2次输入的端口，如：`8674`
8. UDP_PORT：表示hy2的`udp`端口，即第3次输入的端口，如：`8673`
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
   
# 特别感谢

[yonggekkk](https://github.com/yonggekkk/)
