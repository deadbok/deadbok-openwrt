#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
# 

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-Markdown
PKG_VERSION:=2.5.2
PKG_RELEASE:=1

PKG_SOURCE:=Markdown-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/M/Markdown/
PKG_MD5SUM:=db9e3175f4638bfd1574996bf471ea96

PKG_BUILD_DIR:=$(BUILD_DIR)/Markdown-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-Markdown
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Python implementation of Markdown.
	URL:=https://pythonhosted.org/Markdown/
	DEPENDS:=+python3
endef

define Package/python3-Markdown/description
	This is a Python implementation of John Gruber's Markdown.
	It is almost completely compliant with the reference 
	implementation, though there are a few known issues.
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

define Py3Package/python3-Markdown/filespec
+|/usr/lib/python$(PYTHON3_VERSION)/site-packages/markdown
+|/usr/lib/python$(PYTHON3_VERSION)/site-packages/Markdown-2.5.2-py3.4.egg-info
+|/usr/bin/markdown_py
endef

define Py3Package/python3-Markdown/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
endef

$(eval $(call Py3Package,python3-Markdown))
$(eval $(call BuildPackage,python3-Markdown))

