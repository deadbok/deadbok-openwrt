#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
# 

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-Jinja2
PKG_VERSION:=2.7.3
PKG_RELEASE:=1

PKG_SOURCE:=Jinja2-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/J/Jinja2/
PKG_MD5SUM:=b9dffd2f3b43d673802fe857c8445b1a

PKG_BUILD_DIR:=$(BUILD_DIR)/Jinja2-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-Jinja2
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=A small template engine written in pure python.
	URL:=http://jinja.pocoo.org/
	DEPENDS:=+python3
endef

define Package/python3-Jinja2/description
	Jinja2 is a template engine written in pure Python.
	It provides a Django inspired non-XML syntax but supports
	inline expressions and an optional sandboxed environment.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix="$(PKG_INSTALL_DIR)/usr" \
	)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(STAGING_DIR)$(PYTHON_PKG_DIR)
endef

define Py3Package/python3-Jinja2/filespec
+|/usr/lib/python$(PYTHON3_VERSION)/site-packages/Jinja2-2.7.3-py3.4.egg
+|/usr/lib/python$(PYTHON3_VERSION)/site-packages/MarkupSafe-0.23-py3.4-linux2.egg
endef

#define Py3Package/python3-Jinja2/install
#	$(INSTALL_DIR) $(1)/usr/bin
#	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
#endef

$(eval $(call Py3Package,python3-Jinja2))
$(eval $(call BuildPackage,python3-Jinja2))

