#
# Copyright (C) 2009-2010 OpenWrt.org
# Copyright (C) 2009 Jakob Pfeiffer
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=c-ares
PKG_VERSION:=1.7.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://c-ares.haxx.se/download
PKG_MD5SUM:=800875fc23cd8e1924d8af9172ed33e7

PKG_FIXUP:=libtool
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libcares
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Library for asyncronous name resolves
  URL:=$(PKG_SOURCE_URL)
endef

define Package/libcares/description
  c-ares is a C library that performs DNS requests and name resolves
  asynchronously.
endef

define Package/libcares/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so.* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)
	$(CP) $(PKG_INSTALL_DIR)/* $(1)/
endef

$(eval $(call BuildPackage,libcares))

