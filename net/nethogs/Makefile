include $(TOPDIR)/rules.mk

PKG_NAME:=nethogs
PKG_VERSION:=0.8.8
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/raboof/nethogs/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=111ade20cc545e8dfd7ce4e293bd6b31cd1678a989b6a730bd2fa2acc6254818

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Net top tool grouping bandwidth per process
  URL:=https://github.com/raboof/nethogs
  DEPENDS:=+libncurses +libpcap +libstdcpp
endef

define Package/nethogs/description
  NetHogs is a small 'net top' tool. Instead of breaking the traffic down per
  protocol or per subnet, like most tools do, it groups bandwidth by process.
  NetHogs does not rely on a special kernel module to be loaded.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/local/sbin/nethogs $(1)/usr/sbin/nethogs
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
