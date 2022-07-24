SPK_NAME = synokernel-dm
SPK_VERS = 1.0
SPK_REV = 1
SPK_ICON = src/$(SPK_NAME).png

DEPENDS = 

REQUIRE_KERNEL ?= 1
REQUIRE_KERNEL_MODULE  = CONFIG_DM_MIRROR:drivers/md:dm-mirror
REQUIRE_KERNEL_MODULE += CONFIG_DM_MIRROR:drivers/md:dm-log
REQUIRE_KERNEL_MODULE += CONFIG_DM_MIRROR:drivers/md:dm-region-hash

MAINTAINER = NyaMisty
DESCRIPTION = "Provides Synology kernel DM drivers, dm-mirror.ko"
CHANGELOG = "1. Initial release"

UNSUPPORTED_ARCHS = $(PPC_ARCHS)

RELOAD_UI = no
STARTABLE = no
DISPLAY_NAME = SynoKernel DM drivers

HOMEPAGE = https://www.kernel.org/
LICENSE  = GPLv2

SPK_DEPENDS = synocli-kernel

STRIP_TARGET = nop
POST_STRIP_TARGET = synokernel-dm_extra-install

include ../../mk/spksrc.spk.mk

.PHONY: synokernel-dm_extra-install
synokernel-dm_extra-install:
	install -m 755 -d $(STAGING_DIR)/etc/
	install -m 644 src/$(SPK_NAME).cfg $(STAGING_DIR)/etc/$(SPK_NAME).cfg
