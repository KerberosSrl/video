include $(TOPDIR)/rules.mk
 
PKG_NAME:=ProtoGen
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/billvaglienti/ProtoGen.git
PKG_SOURCE_DATE:=2025-01-20
PKG_SOURCE_VERSION:=c79bf4a9fa81a8885c76b2e30d98eb063ddf0b17
PKG_MIRROR_HASH:=703b98ce533164d2e04dfc150d15ab4e7da77699c4573241d3d543cd3aedd30f

PKG_HOST_ONLY:=1
PKG_BUILD_PARALLEL:=1
HOST_BUILD_PARALLEL:=1
PKG_INSTALL:=1
HOST_BUILD_DEPENDS:=qt5base/host

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/nls.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

define Package/ProtoGen
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=ProtoGen
  URL:=https://github.com/billvaglienti/ProtoGen
  DEPENDS:=+qt5base-core
  BUILDONLY:=1
endef

define Host/Install
	$(call Host/Install/Default)

	$(INSTALL_DIR) $(STAGING_DIR_HOST)/bin
	$(CP) $(HOST_BUILD_DIR)/ProtoGen $(STAGING_DIR_HOST)/bin/
	ln -sf $(STAGING_DIR_HOST)/bin/ProtoGen $(STAGING_DIR)/host/bin/
endef

$(eval $(call BuildPackage,ProtoGen))
$(eval $(call HostBuild))
