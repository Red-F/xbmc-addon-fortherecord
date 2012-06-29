## Process this file with automake to produce Makefile.in

DATE = $(shell date +%Y%m%d)
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
	cp -r addons/pvr.fortherecord.argus .
	cat pvr.fortherecord.argus/addon.xml | sed "s/$(VERSION)/$(VERSION).$(DATE)/g" > pvr.fortherecord.argus/addon.xml.new
	mv pvr.fortherecord.argus/addon.xml.new pvr.fortherecord.argus/addon.xml
	$(STRIP) -s -x ./pvr.fortherecord.argus/$(ADDONNAME)
	zip -9 -r ./pvr.fortherecord.argus.$(VERSION).$(DATE).$(ADDONSUFFIX).zip pvr.fortherecord.argus
	rm -Rf pvr.fortherecord.argus
