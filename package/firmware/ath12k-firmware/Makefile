#
# Copyright (C) 2024 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ath12k-firmware
PKG_SOURCE_DATE:=2024-09-26
PKG_SOURCE_VERSION:=5058d3bdfd9ffcbdfbd4572684cc7435316736cb
PKG_MIRROR_HASH:=f10561110d151bbeb5d7de97fa16e95391666c7e7eae37efaad04967d8da5f1d
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://git.codelinaro.org/clo/ath-firmware/ath12k-firmware.git
PKG_LICENSE_FILES:=LICENSE.qca_firmware

PKG_MAINTAINER:=Robert Marko <robimarko@gmail.com>

include $(INCLUDE_DIR)/package.mk

RSTRIP:=:
STRIP:=:

define Package/ath12k-firmware-default
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=$(PKG_SOURCE_URL)
  DEPENDS:=
endef

define Package/ath12k-firmware-qcn9274
$(Package/ath12k-firmware-default)
  TITLE:=QCN9274 ath12k firmware
endef

define Build/Compile

endef

define Package/ath12k-firmware-qcn9274/install
	$(INSTALL_DIR) $(1)/lib/firmware/ath12k/QCN9274/hw2.0
	$(INSTALL_DATA) \
		$(PKG_BUILD_DIR)/QCN9274/hw2.0/1.3.1/WLAN.WBE.1.3.1-00162-QCAHKSWPL_SILICONZ-1/* \
		$(1)/lib/firmware/ath12k/QCN9274/hw2.0/
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/QCN9274/hw2.0/board-2.bin $(1)/lib/firmware/ath12k/QCN9274/hw2.0/board-2.bin
endef

$(eval $(call BuildPackage,ath12k-firmware-qcn9274))
