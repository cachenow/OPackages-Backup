include $(TOPDIR)/rules.mk

PKG_NAME:=dns2tcp
PKG_VERSION:=1.1.0
PKG_RELEASE:=9

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/zfl9/dns2tcp.git
PKG_SOURCE_VERSION:=558b07e4c1f9bd5be19e60892a0bce7661ed99a5
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/$(PKG_SOURCE_SUBDIR)

PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=pexcn <i@pexcn.me>

include $(INCLUDE_DIR)/package.mk

define Package/dns2tcp
	SECTION:=net
	CATEGORY:=Network
	TITLE:=Utility to convert DNS query from UDP to TCP
	URL:=https://github.com/zfl9/dns2tcp
endef

define Package/dns2tcp/description
Utility to convert DNS query from UDP to TCP.
endef

define Package/dns2tcp/conffiles
/etc/config/dns2tcp
endef

define Package/dns2tcp/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dns2tcp $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) files/dns2tcp.init $(1)/etc/init.d/dns2tcp
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) files/dns2tcp.config $(1)/etc/config/dns2tcp
endef

$(eval $(call BuildPackage,dns2tcp))
