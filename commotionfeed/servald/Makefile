include $(TOPDIR)/rules.mk

PKG_NAME:=serval
PKG_VERSION:=2013-02-07
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/servalproject/serval-dna.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=928f9c4daedcf851909ee7cf39deb7f2cde59000
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_FIXUP:=autoreconf

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=

include $(INCLUDE_DIR)/package.mk

define Package/serval
	SECTION:=commotion
	CATEGORY:=Commotion
	TITLE:=Serval Mesh
	DEPENDS:=+libpthread +librt
endef

define Package/serval/description
  Serval Daemon
endef

define Package/serval/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/servald $(1)/usr/bin
endef

#define Package/serval/postinst
##!/bin/sh
#echo "Configuring IP addresses for mesh interfaces"
#/etc/rc.d/S39servalmesh-config
#endef

#define Package/conffiles
#	/etc/serval/servald.conf
#	/etc/rc.d/S41servald
#	/etc/rc.d/S39servalmesh-config
#endef

define Build/Configure
  $(call Build/Configure/Default,--enable-instance-path=/etc/serval)
endef

$(eval $(call BuildPackage,serval))


