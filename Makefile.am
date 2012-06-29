## something something
DATE = $(shell date +%Y%m%d)

SUBDIRS = \
src

DIST_SUBDIRS = \
$(SUBDIRS)

EXTRA_DIST = \
include

all:
	echo cp -r ChangeLog addons/pvr.fortherecord/changelog.txt

dist-zip: all
	echo cp -r addons/pvr.vuplus .
	echo $(STRIP) -s -x pvr.vuplus/XBMC_vuplus.pvr
	echo zip -9 -r ./pvr.vuplus-$(VERSION)-$(build_cpu).zip pvr.vuplus --exclude \*.am \*.in \*Makefile \*.gitignore
	echo rm -Rf pvr.vuplus

dist-zip-daily: all
	echo cp -r addons/pvr.vuplus .
	echo cat pvr.vuplus/addon.xml | sed "s/$(VERSION)/$(VERSION).$(DATE)/g" > pvr.vuplus/addon.xml.new
	echo mv pvr.vuplus/addon.xml.new pvr.vuplus/addon.xml
	echo $(STRIP) -s -x pvr.vuplus/XBMC_vuplus.pvr
	echo zip -9 -r ./pvr.vuplus-$(VERSION).$(DATE)-$(build_cpu).zip pvr.vuplus --exclude \*.am \*.in \*Makefile \*.gitignore
	echo rm -Rf pvr.vuplus
