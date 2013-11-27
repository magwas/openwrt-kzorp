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
TARGET_LDFLAGS += -L$(STAGING_DIR)/usr/lib

include $(INCLUDE_DIR)/package.mk

define Package/zorp
	CATEGORY:=Network
	TITLE:=zorp
endef

define Package/zorp/install
	$(INSTALL_DIR) $(1)/usr/lib/
endef

$(eval $(call BuildPackage,zorp))
