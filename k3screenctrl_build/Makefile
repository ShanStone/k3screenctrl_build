include $(TOPDIR)/rules.mk

PKG_NAME:=k3screenctrl
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/ShanStone/k3screenctrl.git
PKG_SOURCE_VERSION:=e218269e2ac02362ca5b2f80d93f8af454e1cb30
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_SOURCE_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)

include $(INCLUDE_DIR)/package.mk

TARGET_CFLAGS+= -D_GNU_SOURCE

define Package/k3screenctrl
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=@TARGET_bcm53xx_generic_DEVICE_phicomm-k3 +@KERNEL_DEVMEM +jq +coreutils +coreutils-od +bash +curl
  TITLE:=LCD screen controller on PHICOMM K3
  URL:=https://github.com/JoeHoy233/K3screenctrl.git
endef

define Package/k3screenctrl/description
 K3 Screen Controller (k3screenctrl) is a program utilizing
the LCD screen on PHICOMM K3 to display some stats.
endef

define Package/k3screenctrl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/k3screenctrl $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/usr/share/k3screenctrl
	cp -pR $(PKG_BUILD_DIR)/lib/k3screenctrl/* $(1)/usr/share/k3screenctrl/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./root/etc/init.d/k3screenctrl.init $(1)/etc/init.d/k3screenctrl

	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./root/etc/config/k3screenctrl $(1)/etc/config/k3screenctrl
endef

$(eval $(call BuildPackage,k3screenctrl))
