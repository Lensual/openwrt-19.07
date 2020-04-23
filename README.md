# openwrt-19.07

自用版本

添加插件如下
* [FullCone NAT](https://github.com/LGA1150/openwrt-fullconenat)
* [luci-app-unblockmusic](https://github.com/maxlicheng/luci-app-unblockmusic)
* [luci-app-v2ray](https://github.com/kuoruan/luci-app-v2ray)

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

编译前建议挂代理，插件开启配置路径如下

FullCone NAT
>Network -> Firewall -> iptables-mod-fullconenat

luci-app-unblockmusic
>luci -> application -> luci-app-unblockmusic

luci-app-v2ray
>luci -> application -> luci-app-v2ray
