# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=v2rayA
PKG_VERSION:=2.2.7.5
PKG_RELEASE:=1

PKG_ARCH:=v2raya_linux_arm64_$(PKG_VERSION)
PKG_HASH:=skip

PKG_SOURCE:=$(PKG_NAME)-linux-arm64-v$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/v2rayA/v2rayA/releases/download/v$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE:=AGPL-3.0-only
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

include $(INCLUDE_DIR)/package.mk

define Package/v2raya
  TITLE:=A Linux web GUI client of Project V
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  DEPENDS:=@aarch64 +ca-bundle +kmod-nft-tproxy +xray-core
  URL:=https://v2raya.org
endef

define Package/v2raya/description
  v2rayA is a V2Ray Linux client supporting global transparent proxy,
  compatible with SS, SSR, Trojan(trojan-go), PingTunnel protocols.
endef

define Package/v2raya/conffiles
/etc/v2raya/
/etc/config/v2raya
endef

define Build/Compile
endef

define Package/v2raya/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/v2rayA $(1)/usr/bin/v2raya
	$(INSTALL_DIR) $(1)/etc/config/
	$(INSTALL_CONF) $(CURDIR)/files/v2raya.config $(1)/etc/config/v2raya
	$(INSTALL_DIR) $(1)/etc/init.d/
	$(INSTALL_BIN) $(CURDIR)/files/v2raya.init $(1)/etc/init.d/v2raya
endef

$(eval $(call BuildPackage,v2raya))
