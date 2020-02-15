## 简介

个人使用,做了一些修改，汉化基本完成，屏幕固件的版本K3_V21.6.8.46，过高的版本可能导致第三屏wan无显示

luci源码来自 [lwz322](https://github.com/lwz322/luci-app-k3screenctrl)

在官方源码上使用 [OpenWrt](https://github.com/openwrt)， 官方openwrt的源码已经将@TARGET_bcm53xx_DEVICE_phicomm-k3更改为@TARGET_bcm53xx_generic_DEVICE_phicomm-k3，需要在lean源码上编译的自己修改makefile的DEPENDS

## 屏幕界面

第一屏：升级界面

第二屏：型号，温度，MAC，软件版本

第三屏：接口

第四屏：网速以及2.4G和5G WiFi的接入客户端数量

第五屏：天气，时间

第六屏：WiFi信息：SSID和密码（可选隐藏）

第七屏：已接入终端和网速（IPv4转发）

## Screen Interface

1. Update
2. Model, Version, CPU Temp, MAC
3. Port
4. Speed, WiFi (2.4G/5G client) Assicated
5. Weather, Date and Time
6. WiFi Info:SSID & Password (suppressible)
7. Client speed (IPv4 Forward only)
