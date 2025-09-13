# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2023 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=tuic-client
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_ARCH:=tuic-client-$(PKG_VERSION)-aarch64-unknown-linux-musl
PKG_HASH:=c29eaaf3bc05115acc7453ac26bacf9aff65211b1e8ca7f771b818248bec8601

PKG_SOURCE:=$(PKG_NAME)-linux-arm64-v$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tuic-protocol/tuic/releases/download/$(PKG_NAME)-$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

include $(INCLUDE_DIR)/package.mk

define Package/tuic-client
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=Delicately-TUICed 0-RTT proxy protocol
  URL:=https://github.com/EAimTY/tuic/
  DEPENDS:=@USE_MUSL @aarch64
endef

define Build/Compile
endef

define Package/tuic-client/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tuic-client $(1)/usr/bin/tuic-client
endef

$(eval $(call BuildPackage,tuic-client))
