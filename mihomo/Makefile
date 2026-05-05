include $(TOPDIR)/rules.mk

PKG_NAME:=mihomo
PKG_VERSION:=1.19.30
PKG_RELEASE:=1

PKG_ARCH:=$(PKG_NAME)-linux-arm64-v$(PKG_VERSION)
PKG_HASH:=skip

PKG_SOURCE:=$(PKG_NAME)-linux-arm64-v$(PKG_VERSION).gz
PKG_SOURCE_URL:=https://github.com/MetaCubeX/mihomo/releases/download/v$(PKG_VERSION)/
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/ && gzip -d $(PKG_BUILD_DIR)/$(PKG_SOURCE)

PKG_LICENSE:=GPL3.0+
PKG_MAINTAINER:=Joseph Mory <morytyann@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/mihomo
  SECTION:=Bin aarch64
  CATEGORY:=Bin aarch64
  TITLE:=A rule based proxy in Go.
  URL:=https://wiki.metacubex.one
  DEPENDS:=@aarch64 +ca-bundle
  ALTERNATIVES:=\
    300:/usr/bin/mihomo:/usr/libexec/mihomo
endef

define Package/mihomo/description
  Mihomo is a rule based proxy in Go.
endef

define Build/Compile
endef

define Package/mihomo/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_ARCH) $(1)/usr/bin/mihomo
endef

$(eval $(call BuildPackage,mihomo))
