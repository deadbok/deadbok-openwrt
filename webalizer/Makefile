#
# Copyright (C) 2007-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=webalizer
PKG_VERSION:=2.23-08
PKG_RELEASE:=1

PKG_SOURCE_URL:=ftp://ftp.mrunix.net/pub/webalizer/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-src.tgz
PKG_MD5SUM:=00f1f18bd5ed462ea43bf98d867e7966
PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_LICENCE:=GPL-2.0

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/webalizer
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Web Servers/Proxies
	TITLE:=The Webalizer
	URL:=/http://www.webalizer.org/
	DEPENDS:= +libgd +libpng +libdb47
	USERID:=www:www
endef

define Package/webalizer/description
	The Webalizer is a fast, free web server log file analysis program.
	It produces highly detailed, easily configurable usage reports in
	HTML format, for viewing with a standard web browser. 
endef

define Package/webalizer/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/{webalizer,webazolver,wcmgr} $(1)/usr/bin/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/webalizer.conf.sample $(1)/etc
endef

$(eval $(call BuildPackage,webalizer))
