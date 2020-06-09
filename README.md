# openwrt-19.07

自用版本

添加插件如下
* [FullCone NAT](https://github.com/LGA1150/openwrt-fullconenat)
* [luci-app-unblockmusic](https://github.com/maxlicheng/luci-app-unblockmusic)
* [luci-app-v2ray](https://github.com/kuoruan/luci-app-v2ray)
* [openwrt-v2ray](https://github.com/kuoruan/openwrt-v2ray)

# Build



```
$ git clone https://github.com/Lensual/openwrt-19.07/new/openwrt-19.07
$ cd openwrt-19.07
$ ./scripts/feeds update -a
$ ./scripts/feeds install -a
$ make defconfig #可直接使用已配置好的x86_64平台 mv .config-x86_64 .config
$ make menuconfig
$ make -j8 V=s
```

编译前建议挂代理，同时`export GOPROXY=https://goproxy.io`
插件开启配置路径如下

FullCone NAT
>Network -> Firewall -> iptables-mod-fullconenat

openwrt-v2ray
>Network -> Project V -> v2ray-core

LuCI
* luci-app-v2ray
* luci-app-unblockmusic
* luci-app-vlmcsd
* luci-app-pppoe-relay
* luci-app-ssrserver-python
* luci-proto-bonding
* luci-app-ramfree

# 20200609
源码更新至19.07.3

修复添加fullcone对luci-app-firewall的patch

修改zlib编译配置为速度优化

添加luci语言zh-cn

移除mwan3，之前没有移除干净

添加luci主题material

opkg默认为清华https镜像源

添加软件包
* openvpn-openssl
* openvpn-easy-rsa

# 20200503

从上游分支pull更新
镜像大小修改至512MB

移除软件包
* luci-app-mwan3 #1

新增软件包
* curl
* luci-app-vlmcsd

新增软件包 by [coolsnowwolf](https://github.com/coolsnowwolf/lede)
* luci-app-pppoe-relay
* luci-app-ssrserver-python
* luci-proto-bonding
* luci-app-ramfree

# 20200424

重新配置了编译参数

## x86_64

对原版的修改
* 添加iptables-mod-fullconenat和luci菜单补丁
* 添加luci-app-v2ray
* 添加luci-app-unblockmusic

内建luci模块（不包括默认值）
* luci-ssl
* luci-app-acme
* luci-app-adblock
* luci-app-aria2
* luci-app-ddns
* luci-app-dnscrypt-proxy
* luci-app-firewall
* luci-app-hd-idle
* luci-app-https-dns-proxy
* luci-app-ksmbd
* luci-app-minidlna
* luci-app-mwan3
* luci-app-nft-qos
* luci-app-ocserv
* luci-app-openvpn
* luci-app-opkg
* luci-app-privoxy
* luci-app-shadowsocks-libev
* luci-app-shairplay
* luci-app-transmission
* luci-app-udpxy
* luci-app-uhttpd
* luci-app-unblockmusic
* luci-app-upnp
* luci-app-v2ray
* luci-app-vnstat
* luci-app-wireguard
* luci-app-wol
* luci-proto-ipip
* luci-proto-openconnect
* luci-proto-pppossh
* luci-proto-relay
* luci-proto-vpnc

工具
* dnsmasq-full代替dnsmasq
* tar 
* atop
* htop
* sysstat
* tree
* swap-utils
* tune2fs
* resize2fs
* gpgv
* vim(tyny)
* nano
* fdisk
* gdisk
* hdparm
* lsblk
* gzip
* unrar
* unzip
* screen
* tmux
* rsync
* acme-dnsapi
* ifstst
* iftop
* iperf
* iperf3-ssl
* pppoe-discovery
* socat(ssl)
* speedtest-netperf
* tcpdump

Other
* intel-microcode
* qemu-ga
* open-vm-tools


构建镜像
* 构建VMDK和IMG镜像
* RootFS调整到512MB
* 不构建ext4的RootFS
