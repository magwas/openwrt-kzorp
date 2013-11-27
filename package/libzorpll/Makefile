include $(TOPDIR)/rules.mk

# Name and release number of this package
PKG_NAME:=libzorpll
PKG_RELEASE:=1
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)/dist-libzorpll

ZORP_VERSION:=3.9.5
PKG_VERSION:=3.9.1.3
PKG_RELEASE:=1
PKG_REV:=b03c856f314ecea498098b7a895842fdeee1db08

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.balabit.com/downloads/files/zorp/$(ZORP_VERSION)/source/
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:= +libopenssl +libiconv-full

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/libzorpll
	CATEGORY:=Libraries
	TITLE:=libzorpll
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/
	mkdir -p $(1)/usr/include/zorp
	$(CP) $(PKG_INSTALL_DIR)/usr/include/zorp/*.h $(1)/usr/include/zorp/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libzorpll))
