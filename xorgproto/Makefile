include $(TOPDIR)/rules.mk

PKG_NAME:=xorgproto
PKG_VERSION:=2024.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://xorg.freedesktop.org/releases/individual/proto
PKG_HASH:=372225fd40815b8423547f5d890c5debc72e88b91088fbfb13158c20495ccb59

PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)

PYTHON3_PKG_BUILD:=0
PKG_INSTALL:=1

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=BSD-2-Clause AND MIT AND X11
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DEPENDS:=util-macros libxslt/host python3/host

include $(INCLUDE_DIR)/package.mk
include ../../lang/python/python3-package.mk

define Package/xorgproto
	SECTION:=xorg
	CATEGORY:=Xorg
	SUBMENU:=Protocol
	TITLE:=X.Org X11 Protocol headers
	URL:=http://xorg.freedesktop.org/
endef

define Package/xorgproto/description
	combined X.Org X11 Protocol headers
endef

CONFIGURE_VARS += \
	PYTHON="$(STAGING_DIR_HOSTPKG)/bin/$(PYTHON3)"

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/GL $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/X11 $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/share
	$(CP) $(PKG_INSTALL_DIR)/usr/share/pkgconfig $(1)/usr/share/
endef

$(eval $(call BuildPackage,xorgproto))
