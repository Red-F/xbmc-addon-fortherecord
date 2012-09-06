## Process this file with automake to produce Makefile.in

LIBS   = -ldl -lcurl
LIBDIR = @abs_top_srcdir@/addons/pvr.fortherecord.argus
LIB    = @abs_top_srcdir@/addons/pvr.fortherecord.argus/XBMC_ForTheRecord_@addon_suffix@.pvr

lib_LTLIBRARIES = libfortherecord.la

libfortherecord_la_SOURCES = \
	utils.cpp \
	activerecording.cpp \
	channel.cpp \
	epg.cpp \
	recording.cpp \
	recordingsummary.cpp \
	recordinggroup.cpp \
	tools.cpp \
	upcomingrecording.cpp \
	uri.cpp \
	KeepAliveThread.cpp \
	fortherecordrpc.cpp \
	pvrclient-fortherecord.cpp \
	client.cpp \
	lib/jsoncpp/src/lib_json/json_reader.cpp \
	lib/jsoncpp/src/lib_json/json_writer.cpp \
	lib/jsoncpp/src/lib_json/json_value.cpp \
	lib/tsreader/FileReader.cpp \
	lib/tsreader/MultiFileReader.cpp \
	lib/tsreader/TSReader.cpp \
	lib/filesystem/FileSMB.cpp \
	lib/filesystem/DirectorySMB.cpp

AM_CPPFLAGS = $(ARCH_DEFINES) -DTSREADER -fPIC -DPIC -D_REENTRANT -D_LARGEFILE64_SOURCE -D_FILE_OFFSET_BITS=64 -DNDEBUG=1 -O2

INCLUDES = -I$(abs_top_srcdir)/xbmc -I$(abs_top_srcdir)/include -I$(abs_top_srcdir)/include/linux -I$(srcdir)/lib/jsoncpp/include/ -I$(srcdir)/lib/filesystem/

XBMC_fortherecord.pvr: libfortherecord.la
	cp -f .libs/libfortherecord.so XBMC_fortherecord.pvr
	$(STRIP) -x XBMC_fortherecord.pvr

$(LIB): XBMC_fortherecord.pvr
	cp -f XBMC_fortherecord.pvr $(LIB)

all: $(LIB)

clean-local:
	-rm -f $(LIB) XBMC_fortherecord.pvr

install:
