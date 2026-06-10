include $(TOPDIR)/rules.mk

PKG_NAME:=libjitterentropy
PKG_VERSION:=3.7.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/smuellerDD/jitterentropy-library.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MIRROR_HASH:=602cfef477d9330bf796405bb94e3ee0940fa6838384a014670cf8ca03c2c2c3

PKG_MAINTAINER:=Stephan Mueller <smueller@chronox.de>
PKG_LICENSE:=GPL-2.0-or-later BSD-3-Clause
PKG_LICENSE_FILES:=COPYING COPYING.bsd COPYING.gplv2

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/libjitterentropy
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Hardware RNG based on CPU timing jitter
  URL:=https://github.com/smuellerDD/jitterentropy-library
endef

define Package/libjitterentropy/description
  The Jitter RNG provides a noise source using the CPU execution timing jitter.
  It does not depend on any system resource other than a high-resolution time stamp.
endef

# Translate your cmake compilation flags into OpenWrt syntax
CMAKE_OPTIONS += \
	-DBUILD_SHARED_LIBS=OFF \
	-DINTERNAL_TIMER=off \

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/jitterentropy.h $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/jitterentropy-base-user.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libjitterentropy.a $(1)/usr/lib/
endef

define Package/libjitterentropy/install
endef

$(eval $(call BuildPackage,libjitterentropy))