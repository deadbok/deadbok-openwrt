#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
# 

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-markupsafe
PKG_VERSION:=0.23
PKG_RELEASE:=1

PKG_SOURCE:=MarkupSafe-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/M/MarkupSafe/
PKG_MD5SUM:=f5ab3deee4c37cd6a922fb81e730da6e

PKG_BUILD_DIR:=$(BUILD_DIR)/MarkupSafe-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-markupsafe
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Implements a XML/HTML/XHTML Markup safe string for Python.
	URL:=http://github.com/mitsuhiko/markupsafe
	DEPENDS:=+python3
endef

define Package/python3-markupsafe/description
	Implements a unicode subclass that supports HTML strings.
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

define Py3Package/python3-markupsafe/filespec
+|/usr/lib/python$(PYTHON3_VERSION)/site-packages/MarkupSafe-0.23-py3.4-linux2.egg
endef

$(eval $(call Py3Package,python3-markupsafe))
$(eval $(call BuildPackage,python3-markupsafe))

