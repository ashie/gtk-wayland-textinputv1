# -*- Mode: Makefile; tab-width: 8; indent-tabs-mode: t; -*-

AM_CPPFLAGS = \
	-Wall

protocol_built_sources = \
	wayland-text-input-unstable-v1-protocol.c \
	wayland-text-input-unstable-v1-client-protocol.h

BUILT_SOURCES = $(protocol_built_sources)
EXTRA_DIST = $(protocol_built_sources)

if HAVE_GTK3
im_wltextinputv1_LTLIBRARIES = im-wltextinputv1.la
endif

im_wltextinputv1dir = $(GTK3_IM_MODULEDIR)

im_wltextinputv1_la_CFLAGS = \
	$(GTK3_CFLAGS)
im_wltextinputv1_la_LDFLAGS = \
	-rpath $(im_wltextinputv1dir) -avoid-version -module $(no_undefined)
im_wltextinputv1_la_LIBADD = $(GTK3_LIBS)
im_wltextinputv1_la_SOURCES = \
	$(protocol_built_sources) \
	gtkimcontextwayland.c gtkimcontextwayland.h \
	im-wltextinputv1.c

wayland-text-input-unstable-v1-protocol.c : $(WAYLAND_PROTOCOLS_DATADIR)/unstable/text-input/text-input-unstable-v1.xml
	$(AM_V_GEN)$(WAYLAND_SCANNER) code < $< > $@
	$(AM_V_GEN)$(SED) -i -e 's/WL_EXPORT //' $@
wayland-text-input-unstable-v1-client-protocol.h : $(WAYLAND_PROTOCOLS_DATADIR)/unstable/text-input/text-input-unstable-v1.xml
	$(AM_V_GEN)$(WAYLAND_SCANNER) client-header < $< > $@
