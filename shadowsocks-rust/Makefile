# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2017-2020 Yousong Zhou <yszhou4tech@gmail.com>
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=shadowsocks-rust
PKG_VERSION:=1.23.5
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://github.com/shadowsocks/shadowsocks-rust/releases/download/v$(PKG_VERSION)/
PKG_SOURCE:=shadowsocks-v$(PKG_VERSION).aarch64-unknown-linux-musl.tar.xz
PKG_HASH:=42ec15a594dd61b5eae9feb6d7819405e7bd261b8c4cceeda0b6bc7f8b05395f

PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

TAR_CMD:=$(HOST_TAR) -C $(PKG_BUILD_DIR) $(TAR_OPTIONS)

define Build/Compile
endef

define Package/shadowsocks-rust/Default
  define Package/shadowsocks-rust-$(1)
    SECTION:=Bin aarch64
    CATEGORY:=Bin aarch64
    TITLE:=shadowsocks-rust $(1)
    URL:=https://github.com/shadowsocks/shadowsocks-rust
    DEPENDS:=@USE_MUSL @aarch64
  endef

  define Package/shadowsocks-rust-$(1)/install
	$$(INSTALL_DIR) $$(1)/usr/bin
	$$(INSTALL_BIN) $$(PKG_BUILD_DIR)/$(1) $$(1)/usr/bin
  endef
endef

SHADOWSOCKS_COMPONENTS:=sslocal ssmanager ssserver ssurl ssservice
define shadowsocks-rust/templates
  $(foreach component,$(SHADOWSOCKS_COMPONENTS),
    $(call Package/shadowsocks-rust/Default,$(component))
  )
endef
$(eval $(call shadowsocks-rust/templates))

$(foreach component,$(SHADOWSOCKS_COMPONENTS), \
  $(eval $(call BuildPackage,shadowsocks-rust-$(component))) \
)
