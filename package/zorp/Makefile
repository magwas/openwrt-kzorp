	include $(TOPDIR)/rules.mk

# Name and release number of this package
PKG_NAME:=zorp
PKG_VERSION:=3.9.5
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)/zorp-$(PKG_VERSION)

PKG_REV:=d991f043f7b9841dd5a9a4f46d9064d010f2e013

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.balabit.com/downloads/files/zorp/$(PKG_VERSION)/source/
PKG_INSTALL:=1

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include/zorp
TARGET_LDFLAGS += -L$(STAGING_DIR)/usr/lib -pthread -lz

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/zorp
	CATEGORY:=Network
	TITLE:=zorp
	DEPENDS:= +glib +libopenssl +libpthread +libzorpll
endef

define Build/Compile
	sed -i 's/\-\-install\-layout\=deb//g' $(PKG_BUILD_DIR)/pylib/kznf/Makefile;
endef

define Package/zorp/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include/zorp
	$(INSTALL_DIR) $(1)/var/lib/zorp/tmp
	$(INSTALL_DIR) $(1)/var/run/zorp
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/*.so $(1)/usr/lib/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/zorp/*.h $(1)/usr/include/zorp/
endef

$(eval $(call BuildPackage,zorp,+glib,+libopenssl,+libzorpll,+libpthread))
