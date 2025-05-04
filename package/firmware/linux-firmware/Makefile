#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=linux-firmware
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2025-05-02
PKG_SOURCE_VERSION:=43dfb5fb64bb2707ba4fce1bc0fe835ad644b797
PKG_MIRROR_HASH:=PKG_HASH:=2ae6aab2d8930fd54bf30ae15498f1625721bc3630b894644db5d21fad5a20f9

PKG_MAINTAINER:=Felix Fietkau <nbd@nbd.name>

SCAN_DEPS = *.mk

include $(INCLUDE_DIR)/package.mk

RSTRIP:=:
STRIP:=:

define Package/firmware-default
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=http://git.kernel.org/cgit/linux/kernel/git/firmware/linux-firmware.git
  TITLE:=$(1)
  DEPENDS:=$(2)
  LICENSE_FILES:=$(3)
  LICENSE:=$(4)
endef

define Build/Compile

endef

include $(wildcard ./*.mk)
#$(eval $(call BuildPackage,linux-firmware))
