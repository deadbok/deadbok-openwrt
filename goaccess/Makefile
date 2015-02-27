#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=goaccess
PKG_VERSION:=0.8.5
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://tar.goaccess.io/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_MD5SUM:=c406940235f0e52940dbe7dbc1485885
PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_LICENCE:=GPL-2.0

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/goaccess
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Web log analyzer
	TITLE:=GoAccess
	URL:=http://goaccess.io/
	DEPENDS:= +glib2 +libncurses
	USERID:=www:www
endef

define Package/goaccess/description
	GoAccess is an open source real-time web log analyzer and 
	interactive viewer that runs in a terminal in *nix systems. 
	It provides fast and valuable HTTP statistics for system 
	administrators that require a visual server report on the fly. 
endef

define Package/goaccess/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/goaccess $(1)/usr/bin/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/goaccess.conf $(1)/etc
endef

$(eval $(call BuildPackage,goaccess))
