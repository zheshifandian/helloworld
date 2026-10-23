# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2022 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=xray-plugin
PKG_VERSION:=1.8.24
PKG_RELEASE:=1

PKG_LICENSE:=GPL-3.0-only
PKG_MAINTAINER:=Jack Sun <sunjiazheng321521@gmail.com>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_ARCH:=linux-arm64
PKG_HASH:=skip

include $(INCLUDE_DIR)/package.mk

TAR_OPTIONS+= --strip-components 0

define Package/xray-plugin
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=SIP003 plugin for Shadowsocks, based on Xray
  URL:=https://github.com/teddysun/xray-plugin
  DEPENDS:=@aarch64 +ca-bundle
endef

BIN_FILE:=$(PKG_NAME)-$(PKG_ARCH)-v$(PKG_VERSION).tar.gz

define Download/xray-plugin
  URL:=https://github.com/teddysun/xray-plugin/releases/download/v$(PKG_VERSION)/
  URL_FILE:=$(PKG_NAME)-$(PKG_ARCH)-v$(PKG_VERSION).tar.gz
  FILE:=$(BIN_FILE)
  HASH:=$(PKG_HASH)
endef

define Build/Prepare
	rm -rf $(BUILD_DIR)/$(PKG_NAME)
	mkdir -p $(PKG_BUILD_DIR)
	gzip -dc $(DL_DIR)/$(BIN_FILE) | $(HOST_TAR) -C $(PKG_BUILD_DIR)/ $(TAR_OPTIONS)
endef

define Build/Compile
endef

define Package/xray-plugin/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/xray-plugin_linux_arm64 $(1)/usr/bin/xray-plugin
endef

$(eval $(call Download,xray-plugin))
$(eval $(call BuildPackage,xray-plugin))
