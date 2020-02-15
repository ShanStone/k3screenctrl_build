# Copyright (C) 2018 XiaoShan mivm.cn

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-k3screenctrl
PKG_VERSION:=1.1.0
PKG_RELEASE:=1

PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Build/Configure
endef

define Build/Compile
endef

define Package/$(PKG_NAME)
	SECTION:=luci
	CATEGORY:=LuCI
	SUBMENU:=3. Applications
	TITLE:=LuCI Support for k3screenctrl
	DEPENDS:=+k3screenctrl
endef

define Package/$(PKG_NAME)/description
	LuCI Support for k3screenctrl.
endef

define Build/Prepare
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci
	cp -pR ./luasrc/* $(1)/usr/lib/lua/luci/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	po2lmo ./po/zh_Hans/k3screenctrl.zh-cn.po $(1)/usr/lib/lua/luci/i18n/k3screenctrl.zh-cn.lmo

endef

$(eval $(call BuildPackage,$(PKG_NAME)))
