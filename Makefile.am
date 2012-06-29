## Process this file with automake to produce Makefile.in

ADDONSUFFIX = @addon_suffix@
ADDONNAME = XBMC_ForTheRecord_@addon_suffix@.pvr

SUBDIRS = \
src

DIST_SUBDIRS = \
$(SUBDIRS)

EXTRA_DIST = \
include

all:
	cp -r ChangeLog addons/pvr.fortherecord.argus/changelog.txt

dist-zip: all
	cp -r addons/pvr.fortherecord.argus .
	$(STRIP) -s -x ./pvr.fortherecord.argus/$(ADDONNAME)
	zip -9 -r ./pvr.fortherecord.argus.$(VERSION).$(ADDONSUFFIX).zip pvr.fortherecord.argus
	rm -Rf pvr.fortherecord.argus

dist-zip-daily: all
	echo cp -r addons/pvr.vuplus .
	echo cat pvr.vuplus/addon.xml | sed "s/$(VERSION)/$(VERSION).$(DATE)/g" > pvr.vuplus/addon.xml.new
	echo mv pvr.vuplus/addon.xml.new pvr.vuplus/addon.xml
	echo $(STRIP) -s -x pvr.vuplus/XBMC_vuplus.pvr
	echo zip -9 -r ./pvr.vuplus-$(VERSION).$(DATE)-$(build_cpu).zip pvr.vuplus --exclude \*.am \*.in \*Makefile \*.gitignore
	echo rm -Rf pvr.vuplus
