include $(TOPDIR)/rules.mk

PKG_NAME:=xray-core
PKG_VERSION:=26.7.28
PKG_RELEASE:=1

PKG_ARCH:=Xray-linux-arm64-v8a.zip
PKG_HASH:=skip

PKG_SOURCE:=$(PKG_NAME)-linux-arm64-v$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://github.com/XTLS/Xray-core/releases/download/v$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=unzip $(DL_DIR)/$(PKG_SOURCE) -d $(PKG_BUILD_DIR)/

PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>
PKG_LICENSE:=MPL-2.0
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/xray-core
  TITLE:=A platform for building proxies to bypass network restrictions
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  URL:=https://xtls.github.io
  DEPENDS:=@aarch64 +ca-bundle
endef

define Package/xray-core/description
  Xray, Penetrates Everything. It helps you to build your own computer network.
  It secures your network connections and thus protects your privacy.
endef

define Build/Compile
endef

define Package/xray-core/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/xray $(1)/usr/bin/xray
endef

$(eval $(call BuildPackage,xray-core))
