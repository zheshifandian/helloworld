# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2017-2024 Zxlhhyccc <zxlhhyccc@gmail.com>
# Copyright (C) 2021-2024 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=dns2socks-rust
PKG_VERSION:=0.2.3
PKG_RELEASE:=1

PKG_ARCH:=dns2socks-aarch64-unknown-linux-gnu.zip
PKG_HASH:=skip

PKG_SOURCE:=dns2socks-rust-v$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://github.com/tun2proxy/dns2socks/releases/download/v$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=unzip $(DL_DIR)/$(PKG_SOURCE) -d $(PKG_BUILD_DIR)/

PKG_MAINTAINER:=Zxlhhyccc <zxlhhyccc@gmail.com>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/dns2socks-rust
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=DNS forwards to SOCKS5 server
  URL:=https://github.com/tun2proxy/dns2socks.git
  DEPENDS:=@aarch64
endef

define Package/dns2socks-rust/description
  This is a DNS server that forwards DNS requests to a SOCKS5 server.
endef

define Build/Compile
endef

define Package/dns2socks-rust/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dns2socks $(1)/usr/bin/dns2socks-rust
endef

$(eval $(call BuildPackage,dns2socks-rust))
