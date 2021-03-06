#
# Copyright (C) 2011-2013 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=gnuchess
PKG_VERSION:=6.1.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://ftp.gnu.org/pub/gnu/chess
PKG_MD5SUM:=41b0771cee225eff9563d42e7f93263c

include $(INCLUDE_DIR)/package.mk

define Package/gnuchess
	SECTION:=games
	CATEGORY:=Games
	TITLE:=GNU Chess
	DEPENDS:=+libreadline +libncurses +libstdcpp
	URL:=http://www.gnu.org/software/chess/chess.html
	MAINTAINER:=Entware team, wl500g-repo.googlecode.com
endef

define Package/gnuchess/description
 GNU Chess lets most modern computers play a full game of chess.
 It has a plain terminal interface but supports visual interfaces such as XBoard.
endef

define Package/gnuchess/conffiles
/opt/share/gnuchess/gnuchess.ini
endef

define Build/Configure
	$(call Build/Configure/Default, \
		--prefix=$(PREFIX_ZYX) \
		--exec-prefix=$(PREFIX_ZYX) \
		--datadir=$(PREFIX_ZYX)/share \
	)
endef

define Package/gnuchess/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/gnuchess $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/share/gnuchess
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/smallbook.bin $(1)/usr/share/gnuchess/
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/src/gnuchess.ini $(1)/usr/share/gnuchess
endef

$(eval $(call BuildPackage,gnuchess))
