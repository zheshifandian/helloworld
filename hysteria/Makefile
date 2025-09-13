# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=hysteria
PKG_VERSION:=2.6.3
PKG_RELEASE:=1

PKG_ARCH:=$(PKG_NAME)-linux-arm64
PKG_HASH:=f40b96c8aaf69f0c8af9f3b3aa4784e5b455b3d1280c98d5ef4842d5a7078f79

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(ARCH_PACKAGES)
PKG_SOURCE_URL:=https://github.com/apernet/hysteria/releases/download/app/v$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE:=AGPL-3.0-only
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

include $(INCLUDE_DIR)/package.mk

define Package/hysteria
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=A feature-packed network utility optimized for networks of poor quality
  URL:=https://github.com/apernet/hysteria
  DEPENDS:=@aarch64 +ca-bundle
endef

define Package/hysteria/description
  Hysteria is a feature-packed network utility optimized for networks
  of poor quality (e.g. satellite connections, congested public Wi-Fi,
  connecting from China to servers abroad) powered by a custom version
  of QUIC protocol.
endef

define Build/Compile
endef

define Package/hysteria/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hysteria $(1)/usr/bin/hysteria
endef

$(eval $(call BuildPackage,hysteria))
