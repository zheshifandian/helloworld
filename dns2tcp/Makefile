# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2022 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=dns2tcp
PKG_VERSION:=1.1.2
PKG_RELEASE:=1

PKG_ARCH:=$(PKG_NAME)@aarch64-linux-musl@generic+v8a
PKG_HASH:=01120a877019fd76b2991d552fa07268a3cef394e74ba8051500c5c08b5949ac

PKG_SOURCE:=$(PKG_NAME)-linux-arm64-v$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/zfl9/dns2tcp/releases/download/v$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE:=AGPL-3.0-only
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

include $(INCLUDE_DIR)/package.mk

define Package/dns2tcp
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=utility to convert dns query from udp to tcp
  URL:=https://github.com/zfl9/dns2tcp
  DEPENDS:=@aarch64
endef

define Build/Compile
endef

define Package/dns2tcp/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dns2tcp $(1)/usr/bin/dns2tcp
endef

$(eval $(call BuildPackage,dns2tcp))
