#
# Copyright (C) 2006-2016 OpenWrt.org
# Copyright (C) 2016 lede-project.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=epson-inkjet-printer-filter
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/rsnzh/epson-inkjet-printer-201601w/raw/master
PKG_MD5SUM:=0421c9effd98245c0ac4995f64ac7db1

include $(INCLUDE_DIR)/package.mk

define Package/epson-inkjet-printer-filter/Default
  URL:=https://github.com/rsnzh/
  SUBMENU:=Printing
endef

define Package/epson-inkjet-printer-filter
$(call Package/epson-inkjet-printer-filter/Default)
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libcups +libcupsmime +libjpeg +libstdcpp
  TITLE:=epson-inkjet-printer
endef

define Package/epson-inkjet-printer-filter/description
	epson-inkjet-printer
	L380 L382 Series - Epson Inkjet Printer Driver
endef
 

define Build/Configure
	$(call Build/Configure/Default, \
		UNAME="Linux" \
	)
endef

define Package/epson-inkjet-printer-filter/install
	rm -rf $(1)/etc/epson-filter
	$(INSTALL_DIR) $(1)/etc/epson-filter
	$(CP) $(PKG_INSTALL_DIR)/* $(1)/etc/epson-filter/
endef

$(eval $(call BuildPackage,epson-inkjet-printer-filter))