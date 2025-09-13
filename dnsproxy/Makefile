# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=dnsproxy
PKG_VERSION:=0.76.1
PKG_RELEASE:=1

PKG_LICENSE:=GPL-3.0-only
PKG_MAINTAINER:=Jack Sun <sunjiazheng321521@gmail.com>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_ARCH:=linux-arm64
PKG_HASH:=skip

include $(INCLUDE_DIR)/package.mk

TAR_OPTIONS+= --strip-components 2

define Package/dnsproxy
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=Simple DNS proxy with DoH, DoT, DoQ and DNSCrypt support
  URL:=https://github.com/AdguardTeam/dnsproxy
  DEPENDS:=@aarch64
endef

define Package/dnsproxy/description
  A simple DNS proxy server that supports all existing DNS protocols including
  DNS-over-TLS, DNS-over-HTTPS, DNSCrypt, and DNS-over-QUIC.Moreover, it can
  work as a DNS-over-HTTPS, DNS-over-TLS or DNS-over-QUIC server.
endef

BIN_FILE:=$(PKG_NAME)-$(PKG_ARCH)-v$(PKG_VERSION).tar.gz

define Download/dnsproxy
  URL:=https://github.com/AdguardTeam/dnsproxy/releases/download/v$(PKG_VERSION)/
  URL_FILE:=dnsproxy-$(PKG_ARCH)-v$(PKG_VERSION).tar.gz
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

define Package/dnsproxy/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dnsproxy $(1)/usr/bin/dnsproxy
endef

$(eval $(call Download,dnsproxy))
$(eval $(call BuildPackage,dnsproxy))
