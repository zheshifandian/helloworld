# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2020 SharerMax
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=v2ray-plugin
PKG_VERSION:=5.49.0
PKG_RELEASE:=1

PKG_LICENSE:=GPL-3.0-only
PKG_MAINTAINER:=Jack Sun <sunjiazheng321521@gmail.com>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_ARCH:=linux-arm64
PKG_HASH:=skip

include $(INCLUDE_DIR)/package.mk

TAR_OPTIONS+= --strip-components 0

define Package/v2ray-plugin
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=SIP003 plugin for shadowsocks, based on v2ray
  URL:=https://github.com/teddysun/v2ray-plugin
  DEPENDS:=@aarch64 +ca-bundle
endef

BIN_FILE:=$(PKG_NAME)-$(PKG_ARCH)-v$(PKG_VERSION).tar.gz

define Download/v2ray-plugin
  URL:=https://github.com/teddysun/v2ray-plugin/releases/download/v$(PKG_VERSION)/
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

define Package/v2ray-plugin/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/v2ray-plugin_linux_arm64 $(1)/usr/bin/v2ray-plugin
endef

$(eval $(call Download,v2ray-plugin))
$(eval $(call BuildPackage,v2ray-plugin))
