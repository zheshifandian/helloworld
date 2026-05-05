# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=tuic-client
PKG_VERSION:=1.7.2
PKG_RELEASE:=1

PKG_ARCH:=$(PKG_NAME)-aarch64-linux
PKG_HASH:=skip

PKG_SOURCE:=$(PKG_ARCH)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/Itsusinn/tuic/releases/download/v$(PKG_VERSION)
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE:=AGPL-3.0-only
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

include $(INCLUDE_DIR)/package.mk

define Package/tuic-client
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=TUIC proxy protocol client
  URL:=https://github.com/EAimTY/tuic
  DEPENDS:=@aarch64
endef

define Package/tuic-client/description
  Delicately-TUICed 0-RTT proxy protocol client.
endef

define Build/Compile
endef

define Package/tuic-client/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tuic-client $(1)/usr/bin/tuic-client
endef

$(eval $(call BuildPackage,tuic-client))
